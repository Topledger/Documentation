---
description: >-
  This guide will assist you in creating a dashboard on the Top Ledger platform,
  which displays a variety of key metrics for the DEX ecosystem on Solana.
---

# 📊 DEX ecosystem on Solana

Let’s calculate some important metrics for the DEX ecosystem and add them in a dashboard.

## Swap Transaction

We will start with calculating daily swap transactions on Solana. The chart below shows the daily swap transactions for entire DEX ecosystem.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-01-17 at 1.17.15 PM.png" alt=""><figcaption><p>Swap Transactions since Jan 2023</p></figcaption></figure>

Now, let's go through the SQL code used to create these metrics. The query runs on the dex\_trades table available in the Top Ledger platform.

```sql
select block_date, swaps, SUM(swaps) over(order by block_date) as cumulative_swaps
        , swap_transactions, SUM(swap_transactions) over(order by block_date) as cumulative_swap_transactions
        , traders, SUM(new_traders) over(order by block_date) as cumulative_traders
from
(
select block_date, count(tx_id) as swaps, count(distinct tx_id) as swap_transactions, count(distinct signer) as traders
        , count(distinct case when rn1 = 1 then signer end) as new_traders
from
(
select date(partition_0) as block_date, tx_id, d.signer
        , row_number() over(partition by d.signer order by date(partition_0)) as rn1
from tl_solana.dex_trades d 
where date(partition_0) >= date'2023-01-01'
) A 
group by 1
) A 
order by 1 desc
```

Since the dex\_trades table contains all the swap transactions that have happened in the DEX ecosystem, we just need to count the number of transactions on a daily basis. Then, in the second part of the query, we need to aggregate the daily transactions over the entire period to get the cumulative number of transactions since 2023.

## Swap Volume

Now, let's consider the example of swap volume, i.e., how we are going to compute it. The charts below show the daily swap volume for various DEX programs and the cumulative swap volume.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-01-17 at 1.32.11 PM.png" alt=""><figcaption><p>Swap volume by DEX since Jan 2023</p></figcaption></figure>

The SQL code below begins by assigning various program addresses to their respective names and selecting other fields such as block\_date, base\_amount, quote\_amount, base\_mint, quote\_mint, etc. It then calculate the swap amounts on a daily basis, grouped by the program through which the swap happened.

```sql
with cte_raw as 
(
select date_trunc('day', block_time) as block_date
          , tx_id
          , case when outer_program = 'whirLbMiicVdio4qvUfM5KAg6Ct8VwpYzGff3uctyCc' then 'Orca Liquidity Pools'
                 when inner_program = 'whirLbMiicVdio4qvUfM5KAg6Ct8VwpYzGff3uctyCc' then 'Orca Liquidity Pools'
                 when outer_program = '9W959DqEETiGZocYWCQPaJ6sBmUzgfxXfqGeTEdp3aQP' then 'Orca v2'
                 when inner_program = '9W959DqEETiGZocYWCQPaJ6sBmUzgfxXfqGeTEdp3aQP' then 'Orca v2'
                 when outer_program = '675kPX9MHTjS2zt1qfr1NYHuzeLXfQM9H24wFSUt1Mp8' then 'Raydium v4'
                 when inner_program = '675kPX9MHTjS2zt1qfr1NYHuzeLXfQM9H24wFSUt1Mp8' then 'Raydium v4'
                 when outer_program = 'CAMMCzo5YL8w4VFF8KVHrK22GGUsp5VTaW7grrKgrWqK' then 'Raydium CLMM'
                 when inner_program = 'CAMMCzo5YL8w4VFF8KVHrK22GGUsp5VTaW7grrKgrWqK' then 'Raydium CLMM'
                 when outer_program = 'EewxydAPCCVuNEyrVN68PuSYdQ7wKn27V9Gjeoi8dy3S' then 'Lifinity v1'
                 when inner_program = 'EewxydAPCCVuNEyrVN68PuSYdQ7wKn27V9Gjeoi8dy3S' then 'Lifinity v1'
                 when outer_program = '2wT8Yq49kHgDzXuPxZSaeLaH1qbmGXtEyPy64bL7aD3c' then 'Lifinity v2'
                 when inner_program = '2wT8Yq49kHgDzXuPxZSaeLaH1qbmGXtEyPy64bL7aD3c' then 'Lifinity v2'
                 when outer_program = 'PhoeNiXZ8ByJGLkxNfZRnkUfjvmuYqLR89jjFHGqdXY' then 'Phoenix'
                 when inner_program = 'PhoeNiXZ8ByJGLkxNfZRnkUfjvmuYqLR89jjFHGqdXY' then 'Phoenix'
                 when outer_program = 'Eo7WjKq67rjJQSZxS6z3YkapzY3eMj6Xy8X5EQVn5UaB' then 'Meteora'
                 when inner_program = 'Eo7WjKq67rjJQSZxS6z3YkapzY3eMj6Xy8X5EQVn5UaB' then 'Meteora'
                 when outer_program = 'SSwpkEEcbUqx4vtoEByFjSkhKdCT862DNVb52nZg1UZ' then 'Saber'
                 when inner_program = 'SSwpkEEcbUqx4vtoEByFjSkhKdCT862DNVb52nZg1UZ' then 'Saber'
                 when outer_program = 'HyaB3W9q6XdA5xwpU4XnSZV94htfmbmqJXZcEbRaJutt' then 'Invariant'
                 when inner_program = 'HyaB3W9q6XdA5xwpU4XnSZV94htfmbmqJXZcEbRaJutt' then 'Invariant'
                 when outer_program = 'FLUXubRmkEi2q6K3Y9kBPg9248ggaZVsoSFhtJHSrm1X' then 'FluxBeam'
                 when inner_program = 'FLUXubRmkEi2q6K3Y9kBPg9248ggaZVsoSFhtJHSrm1X' then 'FluxBeam'
                 when outer_program = 'BSwp6bEBihVLdqJRKGgzjcGLHkcTuzmSo1TQkHepzH8p' then 'BonkSwap'
                 when inner_program = 'BSwp6bEBihVLdqJRKGgzjcGLHkcTuzmSo1TQkHepzH8p' then 'BonkSwap'
                 when outer_program = 'CLMM9tUoggJu2wagPkkqs9eFG4BWhVBZWkP1qv3Sp7tR' then 'Crema'
                 when inner_program = 'CLMM9tUoggJu2wagPkkqs9eFG4BWhVBZWkP1qv3Sp7tR' then 'Crema' end as program
          , base_mint
          , quote_mint
          , base_amount
          , quote_amount
          , d.signer
from tl_solana.dex_trades d 
where date(partition_0) >= date'2023-01-01'
group by 1,2,3,4,5,6,7,8
),

cte_price as 
(
SELECT block_date, mint, coalesce(price_in_usd,0) as price
FROM tl_solana.prices
where block_date >= date'2023-01-01'
and coalesce(price_in_usd,0) > 0
and mint not in ('BLZEEuZUBVqFhj8adcCFPJvPVCiCyVmh3hkJMrU8KuJA'
                    , '9vMJfxuKxXBoEa7rM12mYLMwTacLMLDJqHozw96WQL8i'
                    , 'ZScHuTtqZukUrtZS43teTKGs2VqkKL8k4QCouR2n6Uo')
group by 1,2,3
)

select *
from
(
select month, program, SUM(volume) as volume, SUM(traders) as traders
        , SUM(trades) as trades
from
(
select date_trunc('month', cr.block_date) as month
        , program
        , SUM(case when base_mint in ('Es9vMFrzaCERmJfrF4H2FYD4KCoNkY11McCe8BenwNYB',
                                  'EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v',
                                  'EjmyN6qEC1Tf1JxiG1ae7UTJhUxSwk1TCWNWqxWV4J6o',
                                  '9iLH8T7zoWhY7sBmj1WK9ENbWdS1nL8n9wAxaeRitTa6',
                                  '7kbnvuGBxxj8AG9qp8Scn56muWGaRaFqxg1FsRp3PaFT'
                                 ) then base_amount
               when quote_mint in ('Es9vMFrzaCERmJfrF4H2FYD4KCoNkY11McCe8BenwNYB',
                                  'EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v',
                                  'EjmyN6qEC1Tf1JxiG1ae7UTJhUxSwk1TCWNWqxWV4J6o',
                                  '9iLH8T7zoWhY7sBmj1WK9ENbWdS1nL8n9wAxaeRitTa6',
                                  '7kbnvuGBxxj8AG9qp8Scn56muWGaRaFqxg1FsRp3PaFT'
                                 ) then quote_amount
               when base_mint in ('So11111111111111111111111111111111111111112'
                                    , 'mSoLzYCxHdYgdzU16g5QSh3i5K3z3KZK7ytfqcJm7So'
                                    , 'bSo13r4TkiE4KumL71LsHTPpL2euBYLFx6h9HP3piy1')
               then cr.base_amount*cp.price
               when quote_mint in ('So11111111111111111111111111111111111111112'
                                    , 'mSoLzYCxHdYgdzU16g5QSh3i5K3z3KZK7ytfqcJm7So'
                                    , 'bSo13r4TkiE4KumL71LsHTPpL2euBYLFx6h9HP3piy1')
               then cr.quote_amount*cp1.price
               when cp.price is not null then cr.base_amount*cp.price
               when cp1.price is not null then cr.quote_amount*cp1.price
               else 0 end) as volume
            , count(distinct signer) as traders
            , count(distinct tx_id) as trades
from cte_raw cr 
left join cte_price cp on cr.block_date = cp.block_date and cr.base_mint = cp.mint
left join cte_price cp1 on cr.block_date = cp1.block_date and cr.quote_mint = cp1.mint
where program is not null
group by 1,2
) A 
group by 1,2
) A 
order by 1 desc, 3 desc
```

Then, the daily swap amount in multiple tokens needs to be converted to USD, which is accomplished using the price table (tl\_solana.prices). Once that is done, we need to sum the amounts in USD over the specified period to calculate the cumulative swap amount in USD.

## Active Wallets

Active wallets are a crucial metric for any dApp in Web3. More wallets imply higher usage of the dApp by users, which also means more revenue opportunities for the dApp in terms of fees and other charges, making any dApp more viable and profitable.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-01-17 at 1.46.32 PM.png" alt=""><figcaption><p>Active wallets across DEXs since Jan 2023</p></figcaption></figure>

Let's go through the SQL code to learn how to calculate active wallets for the DEX ecosystem.

```sql
select block_date, swaps, SUM(swaps) over(order by block_date) as cumulative_swaps
        , swap_transactions, SUM(swap_transactions) over(order by block_date) as cumulative_swap_transactions
        , traders, SUM(new_traders) over(order by block_date) as cumulative_traders
from
(
select block_date, count(tx_id) as swaps, count(distinct tx_id) as swap_transactions, count(distinct signer) as traders
        , count(distinct case when rn1 = 1 then signer end) as new_traders
from
(
select date(partition_0) as block_date, tx_id, d.signer
        , row_number() over(partition by d.signer order by date(partition_0)) as rn1
from tl_solana.dex_trades d 
where date(partition_0) >= date'2023-01-01'
) A 
group by 1
) A 
order by 1 desc
```

To count active wallets over time, we can use the [Rank](https://trino.io/docs/current/functions/window.html) function to count a wallet only once for the entire period, regardless of the number of swaps performed using the same wallet. Thereafter, we need to sum all the unique wallets that have ever performed a trade. And that's it; we have the total number of active wallets.

[Here](https://analytics.topledger.xyz/tl/public/dashboards/K6um5NyEC1tGik3QkQacRzyKXdGrPyN5pMdnvvLo) is the detailed dashboard for your reference.\


