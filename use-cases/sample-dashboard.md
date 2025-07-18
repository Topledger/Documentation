---
description: >-
  This page will help you understand and create a dashboard using the Top Ledger
  platform.
---

# 📊 Sample Dashboard

## Introduction

Top Ledger allows Web3 growth, analytics & data science teams to create powerful dashboards from decoded solana program data. Our backend infra pulls in raw data from the Solana blockchain and labels and indexes them into different tables on a daily basis.&#x20;

Let’s take an example of a project called ‘Project X’. Project X is a major DeFi project on Solana. We will calculate some important metrics for Project X and add them in a dashboard.

## Sample SQL Query

```sql
with cte_markets as (
    select 
        pd.input_accounts.market, 
        pd.input_accounts.baseMint,
        pd.input_accounts.quoteMint, 
        ts_base.symbol as baseMintName,
        ts_quote.symbol as quoteMintName,
        ts_quote.decimals
    from phoenix.parsed pd
    join token.solana_token ts_base on ts_base.address = pd.input_accounts.baseMint
    join token.solana_token ts_quote on ts_quote.address = pd.input_accounts.quoteMint
    where 1=1
    and pd.instruction_type = 'InitializeMarket'
)
, 
market_names as (
    select 
        market,
        baseMint,
        quoteMint,
        baseMintName || ' - ' || quoteMintName as marketName,
        decimals
    from cte_markets
)

select block_date,market, marketName, trades, sum(trades) over(order by block_date) as cum_trades
from 
(
select block_date,market, marketName,  count(distinct tx_id) as trades
from phoenix.parsed as p 
cross join unnest(args.market_events) as market_event
join market_names as m on p.args.header_fields.header.market = m.market
where 1=1
and instruction_type = 'Log'
and market_event = 'FillSummary'
and p.args.header_fields.header.market = '{{market}}'
and market_event.fields.total_quote_lots_filled > 0
group by 1,2,3
) as a 
order by 1 desc


```

## Trades

We will start with calculating number of trades on daily basis and weekly top five pools based on number of trades. The below widget shows total number of trades for project X.

<figure><img src="../.gitbook/assets/Screenshot 2024-02-24 at 5.40.10 PM.png" alt=""><figcaption><p>Total Number of Trades for Project X</p></figcaption></figure>

Also, in the widgets shown below you can see Trade trends along with weekly top 5 pools based on the number of trades for the project. On 11th Dec there was a spike in user activity which could be related to some internal or external event.&#x20;

It also shows all time top 5 pools based on number of trades.

<figure><img src="../.gitbook/assets/Screenshot 2024-02-24 at 5.44.55 PM.png" alt=""><figcaption><p>Number of Trades and Top Pools for Project X.</p></figcaption></figure>

Let's go through the SQL code for the widgets you have seen so far. The query runs on parsed table available in the TL platform.

```sql
with cte_markets as (
    select 
        pd.input_accounts.market, 
        pd.input_accounts.baseMint,
        pd.input_accounts.quoteMint, 
        ts_base.symbol as baseMintName,
        ts_quote.symbol as quoteMintName,
        ts_quote.decimals
    from phoenix.parsed pd
    join token.solana_token ts_base on ts_base.address = pd.input_accounts.baseMint
    join token.solana_token ts_quote on ts_quote.address = pd.input_accounts.quoteMint
    where 1=1
    and pd.instruction_type = 'InitializeMarket'
)
,


market_names as (
    select 
        market,
        baseMint,
        quoteMint,
        baseMintName || ' - ' || quoteMintName as marketName,
        decimals
    from cte_markets
)
, 

daily_volumes_fees as (
    select  
        p.partition_0,
        p.args.header_fields.header.market as market,
        mn.marketName,
        mn.baseMint,
        mn.quoteMint,
        count(tx_id) as trades,
        sum(market_event.fields.total_quote_lots_filled / pow(10, mn.decimals)) as daily_volume,
        sum(market_event.fields.total_fee_in_quote_lots / pow(10, mn.decimals)) as daily_fees
    from phoenix.parsed as p
    cross join unnest(p.args.market_events) as market_event
    join market_names mn on mn.market = p.args.header_fields.header.market
    where 1=1
    and instruction_type =  'Log' 
    and market_event = 'FillSummary'
    and market_event.fields.total_quote_lots_filled > 0
    group by 1, 2, 3, 4,5
), 
volume_fees_in_usd as (
    select 
        date(dv.partition_0) as block_date,
        dv.market,
        dv.marketName,
        dv.baseMint,
        dv.quoteMint,
        trades,
        dv.daily_volume,
        dv.daily_fees,
        case 
            when dv.quoteMint in ('EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v', 'Es9vMFrzaCERmJfrF4H2FYD4KCoNkY11McCe8BenwNYB') then dv.daily_volume
            else dv.daily_volume * tp.price_in_usd
        end as daily_volume_usd,
        case 
            when dv.quoteMint in ('EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v', 'Es9vMFrzaCERmJfrF4H2FYD4KCoNkY11McCe8BenwNYB') then dv.daily_fees
            else dv.daily_fees * tp.price_in_usd
        end as daily_fees_usd
    from daily_volumes_fees dv
    left join tl_solana.prices tp on dv.quoteMint = tp.mint and date(dv.partition_0) = tp.block_date
), 

weekly as 
(
select date_trunc('week', block_date) as week,
       market, marketName,
       sum(trades) as weekly_trades,
       sum(daily_volume_usd) as weekly_volume_usd,
       sum(daily_fees_usd) as weekly_fees_usd
from volume_fees_in_usd
group by 1,2,3
)
,
ranked_markets as 
(
    select *,
        rank() over (partition by week order by weekly_volume_usd desc) as rank
    from weekly
)

select * 
from ranked_markets
where rank <= 5
order by week desc, weekly_volume_usd desc


```

We need to begin with extracting and organizing market details, such as base and quote tokens. Subsequently, it concatenates token names for clarity. Then we calculates daily trading volumes and fees for each market, considering the associated token decimals. These daily metrics are further converted into USD values based on token prices.&#x20;

The data is then aggregated on a weekly basis, summing up trades, volume, and fees. Finally, the markets are ranked weekly by trading volume in USD, and the top 5 markets are selected and displayed. This comprehensive analysis offers a snapshot of the most active markets on Solana, providing valuable insights into their weekly performance.

## Trade Volume and Fees

Now let’s calculate how much trade volume Project X is making. We will check the total volume and fees for trades per day and cumulative amount of the two metrics.  We can infer a lot of insights by relating this metric with real world events and can measure the impact.

<figure><img src="../.gitbook/assets/Screenshot 2024-02-24 at 5.56.01 PM.png" alt=""><figcaption><p>Trade volume and Fees for ProjectX</p></figcaption></figure>

Here, we see 6 widgets. 1) Total trade volume, 2) daily trade volume, 3) cumulative trade volume,  4) total trade fees, 5) daily fees for trades, and 6)cumulative fees for trades. We can infer that the volume of fees is quite high and which in a way is a sign of good health and profits for the liquidity provider and for the projectX.

```sql
with cte_markets as (
    select 
        pd.input_accounts.market, 
        pd.input_accounts.baseMint,
        pd.input_accounts.quoteMint, 
        ts_base.symbol as baseMintName,
        ts_quote.symbol as quoteMintName,
        ts_quote.decimals
    from phoenix.parsed pd
    join token.solana_token ts_base on ts_base.address = pd.input_accounts.baseMint
    join token.solana_token ts_quote on ts_quote.address = pd.input_accounts.quoteMint
    where 1=1
    and pd.instruction_type = 'InitializeMarket'
)
, 
market_names as (
    select 
        market,
        baseMint,
        quoteMint,
        baseMintName || ' - ' || quoteMintName as marketName,
        decimals
    from cte_markets
), 

volumes_fees as (
    select  
        p.partition_0,
        quoteMint,
        count(tx_id) as trades,
        sum(market_event.fields.total_quote_lots_filled / pow(10, mn.decimals)) as daily_volume,
        sum(market_event.fields.total_fee_in_quote_lots / pow(10, mn.decimals)) as daily_fees
    from phoenix.parsed p
    cross join unnest(p.args.market_events) as market_event
    join market_names mn on mn.market = p.args.header_fields.header.market
    where 1=1
    and p.instruction_type = 'Log'
    and market_event = 'FillSummary'
    group by 1,2
), 
volume_fees_in_usd as (
    select 
        dv.partition_0,
        trades,
        dv.daily_volume,
        dv.daily_fees,
        case 
            when dv.quoteMint in ('EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v', 'Es9vMFrzaCERmJfrF4H2FYD4KCoNkY11McCe8BenwNYB') then dv.daily_volume
            else dv.daily_volume * tp.price_in_usd
        end as daily_volume_usd,
        case 
            when dv.quoteMint in ('EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v', 'Es9vMFrzaCERmJfrF4H2FYD4KCoNkY11McCe8BenwNYB') then dv.daily_fees
            else dv.daily_fees * tp.price_in_usd
        end as daily_fees_usd
    from volumes_fees dv
    left join tl_solana.prices tp on dv.quoteMint = tp.mint and date(dv.partition_0) = tp.block_date
)
,
daily_volume_fee_usd as 
(
select partition_0, 
      sum(trades) as trades,
      sum(daily_volume_usd) as daily_volume_usd,
      sum(daily_fees_usd) as daily_fees_usd
from volume_fees_in_usd
group by 1 
)



    select 
        partition_0,
        trades,
        daily_volume_usd,
        daily_fees_usd,
        sum(trades) over(order by partition_0) as cumulative_trades,
        sum(daily_volume_usd) over (order by partition_0) as cumulative_volume_usd,
        sum(daily_fees_usd) over (order by partition_0) as cumulative_fees_usd
    from daily_volume_fee_usd
    order by 1 desc
    
    

```

Here we starts with extracting and processing data related to ProjectX  markets. It involves several common table expressions (CTEs) to organize and aggregate the information. Then it calculates daily trade metrics, including the number of trades, daily volume, and daily fees in both native and USD denominations. Additionally, it computes cumulative metrics over time, providing a comprehensive view of market activity. The query draws data from various tables, such as phoenix.parsed, token.solana\_token, and tl\_solana.prices, utilizing their relationships to derive meaningful insights into ProjectX market performance.

## Market Analysis

As many platforms wants, here we will add some key metrics regarding specific markets provided to users by the ProjectX. This includes total number of trades, trade volume, fees generated, users participated in a particular market. As shown in the widget below are the numbers for SOL-USDC market on the ProjectX.

<figure><img src="../.gitbook/assets/Screenshot 2024-02-24 at 6.13.49 PM.png" alt=""><figcaption><p>Various Numbers for SOL-USDC market on ProjectX</p></figcaption></figure>

Let’s go through the SQL code for how to calculate volume for Project X.

```sql
WITH
  buys AS (
        SELECT
        id,
        block_date,
        pre_balances,
        post_balances, 
        account_keys[1] as unique_wallet
        FROM "tl-solana-merged-data"."transactions"
            CROSS JOIN UNNEST(instructions) AS instruction
        WHERE 1=1
            AND success = True
            AND block_date >= date_trunc('day', now() - interval '30' day) 
            AND ( 
                    instruction.executing_account = 'JUP4Fb2cqiRUcaTHdrPC8h2gNsA2ETXiPDD33WcGuJB' -- program address of project X
        
                    --check in inner_instructions
                    OR  contains(transform(CAST(instruction.inner_instructions AS array<JSON>), x -> json_extract_scalar(x, '$.executing_account')), 'JUP4Fb2cqiRUcaTHdrPC8h2gNsA2ETXiPDD33WcGuJB') 
            )
        GROUP BY 1,2,3,4,5
    ),
buys_summed AS (
    SELECT
        id,
        block_date,
        SUM(IF(
            post_balances[i] - pre_balances[i] > 0,
            post_balances[i] - pre_balances[i],
            0
        )) * 1.0 / 1e9 AS sol_approx, -- 1 SOL = 10^9 lamports
        unique_wallet
    FROM buys
        CROSS JOIN UNNEST(pre_balances) WITH ORDINALITY AS b (pre_balance, i)
    GROUP BY id, block_date, unique_wallet
    ), vol_raw AS (
                    SELECT
                      date_trunc('day', block_date)  AS day,
                      SUM(sol_approx) AS sol,
                      COUNT(distinct unique_wallet) as unique_wallets
                    FROM buys_summed 
                    GROUP BY 1
        )
SELECT day
     , sol
     , unique_wallets
     , SUM(sol) over (order by day asc rows between unbounded preceding and current row) 
       AS cumulative_sol
FROM vol_raw
ORDER BY 1 DESC
```

Once again we will start with extracting and processing data related to ProjectX markets. It begins by identifying markets and their associated details, including base and quote tokens. Subsequently, it calculates daily trading volumes and fees for each market, converting them into USD based on token prices. The final result provides a comprehensive summary of daily and cumulative trading metrics for the specified markets, offering insights into market activity over time.

Here is the link to the detailed dashboard for your reference -

{% embed url="https://analytics.topledger.xyz/tl/public/dashboards/knoPmkT1W0deT8txVQYw1daqqepjITZRZbvz1oft" %}
