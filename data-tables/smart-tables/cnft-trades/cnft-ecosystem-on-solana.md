---
description: >-
  This guide will assist you in creating a dashboard on the Top Ledger platform,
  which displays a variety of key metrics for the cNFT secondary ecosystem on
  Solana.
---

# 📊 cNFT ecosystem on Solana

Let’s calculate some important metrics for the compressed NFT secondary ecosystem and add them in a dashboard.

## Trade Volume

We will start by calculating the daily cNFT trade volume. The chart below shows the daily trade volume for the cNFT ecosystem.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-01-17 at 3.38.51 PM.png" alt=""><figcaption><p>compressed NFT trade volume</p></figcaption></figure>

Additionally, the charts displayed below illustrate the total number of cNFTs traded within the ecosystem, as well as the daily trend in cNFT trading.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-01-17 at 3.39.44 PM.png" alt=""><figcaption><p>cNFT trades</p></figcaption></figure>

Next, we'll review the SQL code behind the charts you've observed. This query operates on the cnft\_trades table, which is accessible on the Top Ledger platform.



```sql
select A.block_date
        , trades, SUM(trades) over(order by A.block_date) as cumulative_trades
        , trade_volume, SUM(trade_volume) over(order by A.block_date) as cumulative_trade_volume
        , trade_volume*price_in_usd as trade_volume_in_USD
        , SUM(trade_volume*price_in_usd) over(order by A.block_date) as cumulative_trade_volume_in_USD
        , royalty, SUM(royalty) over(order by A.block_date) as cumulative_royalty
        , royalty*price_in_usd as royalty_in_USD, SUM(royalty*price_in_usd) over(order by A.block_date) as cumulative_royalty_in_USD
from
(
select date(block_time) as block_date
        , count(distinct tx_id) as trades
        , SUM(amount)/1e9 as trade_volume
        , SUM(taker_fee)/1e9 as taker_fee
        , SUM(maker_fee)/1e9 as maker_fee
        , SUM(amm_fee)/1e9 as amm_fee
        , SUM(royalty)/1e9 as royalty
from tl_solana.cnft_trades
where 1=1
and date(partition_0) >= current_date - interval '90' day
    )
group by 1 
) A 
join (select block_date, price_in_usd
                    from tl_solana.prices
                    where mint = 'So11111111111111111111111111111111111111112') as s  on a.block_date = s.block_date 
order by 1 desc
```

To begin with, since the cnft\_trades table records the amount of SOL (in lamports) used for each cNFT purchase, our first step is to calculate the total SOL amount on a daily basis. Following this, the second part of the query involves converting the SOL volume into USD volume. This is done using our price table (tl\_solana.prices), allowing us to determine the daily USD trade volume.

Subsequently, we can aggregate this data over the entire period to ascertain the cumulative trade volume in both SOL and USD. In a similar manner, we can track the daily trend in the number of trades and the total number of trades that have occurred to date.

To calculate the number of cNFT trades, we simply count the unique tx\_id entries in the cnft\_trades table. This count can then be cumulatively aggregated over time to yield the total number of trades.

## Royalties

Now, let's determine the total royalties paid to creators from cNFT trades within the ecosystem. This can be done in the same query used for trade volume calculation, but instead, we'll focus on a different column, specifically 'royalty'.

We will then present this data using charts as shown below:

<figure><img src="../../../.gitbook/assets/Screenshot 2024-01-17 at 3.42.47 PM.png" alt=""><figcaption><p>royalty paid</p></figcaption></figure>

In this process, we initially aggregate the royalty data on a daily basis, then convert the SOL volume into USD. Following this, we aggregate these daily amounts over the entire period to determine the cumulative royalty in both USD and SOL for the creators.\


