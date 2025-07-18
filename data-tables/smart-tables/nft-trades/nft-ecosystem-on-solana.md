---
description: >-
  This guide will assist you in creating a dashboard on the Top Ledger platform,
  which displays a variety of key metrics for the NFT secondary ecosystem on
  Solana.
---

# 📊 NFT ecosystem on Solana

Let’s calculate some important metrics for the NFT secondary ecosystem and add them in a dashboard.

## Trade Volume

We will begin by calculating the daily NFT secondary trade volume. The chart below shows the daily trade volume for the entire Solana ecosystem.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-01-16 at 8.02.32 PM.png" alt=""><figcaption><p>Daily secondary trade volume since Jan 2023</p></figcaption></figure>

Additionally, from the charts shown below, you can deduce the total number of NFTs traded within the ecosystem, as well as observe the daily trend in NFT sales.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-01-16 at 8.06.31 PM.png" alt=""><figcaption><p>NFT trades on Solana since Jan 2023</p></figcaption></figure>

Now, let's go through the SQL code used to create these metrics. The query runs on the dex\_trades table available in the Top Ledger platform.

```sql
select block_date, amount_sol, sum(amount_sol) over(order by block_date) as cum_amount_sol,
       amount_usd, sum(amount_usd) over(order by block_date) as cum_amount_usd
from 
(
select a.block_date, amount_sol, amount_sol * price_in_usd as amount_usd
from 
(
    select date(block_time) as block_date, sum( abs(amount/1e9)) as amount_sol
    from "tl_solana"."nft_trades"
    where 1 = 1
    group by 1 
) as a left join (select block_date, price_in_usd
                    from tl_solana.prices
                    where mint = 'So11111111111111111111111111111111111111112') as s  on a.block_date = s.block_date 
  
) as a
order by 1 desc
```

Since the nft\_trades table contains the 'amount' column, which represents the amount of SOL (in lamports) paid to buy an NFT in each trade, we first need to add the total SOL amount on a daily basis. In the second part of the query, we will convert the SOL volume into USD volume using our price table (tl\_solana.prices) to obtain the daily USD volume of all sales.&#x20;

Finally, we can aggregate this data over the entire period to calculate the cumulative volume in both SOL and USD. Similarly, we can track the daily trend for the number of trades and the total number of trades that have occurred so far.

## Royalties

Now, let's embark on the task of calculating the total royalty payments made to creators within the Solana ecosystem since January 2023. Our objective is to compute both the daily and cumulative royalty amounts, expressed in both SOL and USD. This endeavor will provide valuable insights into the earnings accrued by creators from their NFTs, shedding light on their financial success within the ecosystem.

Here are the charts:

<figure><img src="../../../.gitbook/assets/Screenshot 2024-01-17 at 12.08.48 PM.png" alt=""><figcaption><p>Royalties paid since Jan 2023</p></figcaption></figure>

Here, we see 4 widgets: 1) total royalties in SOL, 2) daily royalties in SOL, 3) total royalties in USD, and 4) daily royalties in USD. Here, again, we had to first aggregate the royalty at the daily level, then convert the SOL volume into USD, and finally, once again aggregate the daily amount over the whole period to get the cumulative royalty in USD and in SOL for creators.

```sql
select block_date, amount_sol, sum(amount_sol) over(order by block_date) as cum_amount_sol,
       amount_usd, sum(amount_usd) over(order by block_date) as cum_amount_usd
from 
(
select a.block_date, amount_sol, amount_sol * price_in_usd as amount_usd
from 
(
    select date(block_time) as block_date, sum( abs(royalty/1e9)) as amount_sol
    from "tl_solana"."nft_trades"
    group by 1 
) as a left join tl_solana.prices as s  on a.block_date = s.block_date 
  where mint = 'So11111111111111111111111111111111111111112'
) as a
order by 1 desc
```

## Buyers

The number of buyers plays a pivotal role in determining the success of any NFT marketplace within the web3 ecosystem. It serves as a fundamental metric that directly influences the dynamics of the platform. When there is a higher count of buyers, it leads to an increased demand for NFTs within that marketplace. This heightened demand, in turn, contributes to the overall viability and sustainability of the platform specializing in NFT trading.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-01-17 at 12.23.02 PM.png" alt=""><figcaption><p>Buyers by different platforms</p></figcaption></figure>

In the charts above, we can see that Magic Eden has had the most buyers since January 2023 among the NFT marketplaces, and we can also observe that Tensor is making deep inroads in the NFT trading sector.

Let’s go through the SQL code for how to calculate the number of buyers.

```sql
select date(block_time) as block_date, platform,  count(distinct buyer) as buyer
from "tl_solana"."nft_trades"
group by 1,2 
order by 1 desc
```

Calculations here are simple, as we simply need to aggregate the distinct buyers at the daily level, grouped by the different platforms available.

[Here](https://analytics.topledger.xyz/delphi/public/dashboards/4j3ipTL1F69bgqa7V0BTPZANoulZbkLj0TXaVxQ4) is the detailed dashboard for your reference.\


