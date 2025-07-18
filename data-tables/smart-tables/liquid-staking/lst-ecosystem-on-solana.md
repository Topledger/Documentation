---
description: >-
  This guide will assist you in creating a dashboard on the Top Ledger platform,
  which displays a variety of key metrics for the LST ecosystem on Solana.
---

# 📊 LST ecosystem on Solana

Let’s calculate some important metrics for the LST ecosystem and add them in a dashboard.

## Deposits & Withdraws

We will start by calculating deposits and withdrawals for various platforms in the LST ecosystem. The chart below shows the weekly volumes.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-01-17 at 2.48.24 PM.png" alt=""><figcaption><p>Weekly deposts &#x26; withdraws</p></figcaption></figure>

Now, let's go through the SQL code for the above chart. The query runs on the liquid\_staking table available in the Top Ledger platform.

The SQL code start first with staking multiple types of LS txns and  volume associated with them on a daily level. Then it union them in a nested expression to gather all the txns and volume associated with staking and un-staking events in the ecosystem.  Finally, the code groups by the data for various platforms and then cluster the it over weekly interval.

```sql
with 
cte_reward
as
    (
    select date(block_time) as block_date,stake_pool,signer,tx_id,(staking_reward/1e9 )as amount
    from tl_solana.liquid_staking
    where instruction_type in ('UpdateDeactivated','UpdateActive')
   
    )
,
cte_deposit
as
    (
    select  date(block_time) as block_date,stake_pool,signer,tx_id,
    case when instruction_type in ('Deposit','DepositSol','DepositStake')  then amount/1e9 else -amount/1e9 end as amount
    from tl_solana.liquid_staking
    where instruction_type in ('Claim','LiquidUnstake','Deposit','WithdrawStake','WithdrawSol','DepositSol','DepositStake')
   

    )
,
cte_deposit_stake
as (
    select a.block_date,stake_pool,signer,tx_id,amount*sol as amount
    from 
        (
        select date(block_time) as block_date,signer,stake_pool,tx_id,mint_amount/1e9 as amount
        from tl_solana.liquid_staking
        where instruction_type in ('DepositStakeAccount')
        )a
    join 
    (
       select a.block_date,b.price_in_usd /a.price_in_usd as sol
       from
       (
            select *
            from tl_solana.prices
            where mint='mSoLzYCxHdYgdzU16g5QSh3i5K3z3KZK7ytfqcJm7So'
        )a
        join 
        (
            select *
            from tl_solana.prices
            where mint='So11111111111111111111111111111111111111112'
        )b on  a.block_date=b.block_date
        )b
        on a.block_date=b.block_date
    ) 
    
    
select month, stake_pool,amount
from(
        select date_trunc('week',block_date) as month, case when stake_pool='8szGkuLTAux9XMgZ2vtY39jVSowEcpBfFfD8hXSEqdGC' then 'msol'
                                    when stake_pool='stk9ApL5HeVAwPLr3TLhDXdZS8ptVu7zp6ov8HFDuMi' then 'bsol'
                                    when stake_pool='Jito4APyf642JPZPx3hGc6WWJ8zPKtRbRs4P815Awbb' then 'jitosol'
                                    when stake_pool='CtMyWsrUtAwXWiGr9WjHT5fC3p3fgV8cyGpLTo2LJzG1' then 'jpool'
                                    --when stake_pool='7ge2xKsZXmqPxa3YmXxXmzCp9Hc2ezrTxh6PECaxCwrL' then 'daosol'
                                    when stake_pool='CgntPoLka5pD5fesJYhGmUCF8KU1QS1ZmZiuAuMZr2az' then 'cgntso'
                                    when stake_pool='2qyEeSAWKfU18AFthrF7JA8z8ZCi1yt76Tqs917vwQTV' then 'laineSOL'
                                    when stake_pool='DqhH94PjkZsjAqEze2BEkWhFQJ6EyU6MdtMphMgnXqeK' then 'mrgnLST'
                                    else null end as stake_pool,
                                    sum(amount) as amount
    from
            (
                select *
                from cte_deposit
                union all
                select *
                from cte_reward
                union all
                select *
                from cte_deposit_stake
        )

group by 1,2
    
    )
where stake_pool is not null
 order by 1 desc
```

And the widget displays the deposits as positive while withdraws as negative, providing a fine sense of how much of net amount is getting staked every day.

## TVL

Total Value Locked or TVL is the amount which is stacked or locked as LST in a pool at any moment. So TVL represents the most crucial metric for LST platforms. It tells us about the health and hence the confidence people has in some LST platform.  So let's visualize the TVL of various platforms with the help of some charts



<figure><img src="../../../.gitbook/assets/Screenshot 2024-01-17 at 3.11.18 PM.png" alt=""><figcaption><p>Project X TV</p></figcaption></figure>



Since TVL is nothing but accumulation of net deposits over time, the query below, like the previous one,  starts with computing deposits and withdraws and the subtract the withdraws from deposits to get daily net deposits. And then in the next step accumulate them over the time to get not only the TVL at present but also TVL for past days.

```sql
with 
cte_reward
as
    (
    select date(block_time) as block_date,stake_pool,tx_id,signer,(staking_reward/1e9 )as amount
    from tl_solana.liquid_staking
    where instruction_type in ('UpdateDeactivated','UpdateActive')
   
    )
,
cte_deposit
as
    (
    select  date(block_time) as block_date,stake_pool,tx_id,signer,
    case when instruction_type in ('Deposit','DepositSol','DepositStake')  then amount/1e9 else -amount/1e9 end as amount
    from tl_solana.liquid_staking
    where instruction_type in ('Claim','LiquidUnstake','Deposit','WithdrawStake','WithdrawSol','DepositSol','DepositStake')
   

    )
,
cte_deposit_stake
as (
    select a.block_date,stake_pool,tx_id,signer,amount*sol as amount
    from 
        (
        select date(block_time) as block_date,stake_pool,tx_id,signer,mint_amount/1e9 as amount
        from tl_solana.liquid_staking
        where instruction_type in ('DepositStakeAccount')
        )a
    join 
    (
       select a.block_date,b.price_in_usd /a.price_in_usd as sol
       from
       (
            select *
            from tl_solana.prices
            where mint='mSoLzYCxHdYgdzU16g5QSh3i5K3z3KZK7ytfqcJm7So'
        )a
        join 
        (
            select *
            from tl_solana.prices
            where mint='So11111111111111111111111111111111111111112'
        )b on  a.block_date=b.block_date
        )b
        on a.block_date=b.block_date
    ) 
    
    
select block_date, stake_pool,amount,transfer,wallet,unique_wallet,
sum(amount)over(partition by stake_pool order by block_date) as tvl,
sum(unique_wallet)over( order by block_date) as cumulative_wallets,
sum(unique_wallet)over(partition by stake_pool order by block_date) as cumulative_wallets_by_pool,
sum(transfer)over(partition by stake_pool order by block_date) as cumulative_transfer_pool,
sum(transfer)over( order by block_date) as cumulative_transfer


from(
    select block_date,  case   when stake_pool='8szGkuLTAux9XMgZ2vtY39jVSowEcpBfFfD8hXSEqdGC' then 'Marinade'
                            when stake_pool='stk9ApL5HeVAwPLr3TLhDXdZS8ptVu7zp6ov8HFDuMi' then 'Sol blaze'
                            when stake_pool='Jito4APyf642JPZPx3hGc6WWJ8zPKtRbRs4P815Awbb' then 'Jito'
                            when stake_pool='CtMyWsrUtAwXWiGr9WjHT5fC3p3fgV8cyGpLTo2LJzG1' then 'Jpool'
                            --when stake_pool='7ge2xKsZXmqPxa3YmXxXmzCp9Hc2ezrTxh6PECaxCwrL' then 'Daosol'
                            when stake_pool='CgntPoLka5pD5fesJYhGmUCF8KU1QS1ZmZiuAuMZr2az' then 'Cogent crypto'
                            when stake_pool='2qyEeSAWKfU18AFthrF7JA8z8ZCi1yt76Tqs917vwQTV' then 'LaineSOL'
                            when stake_pool='DqhH94PjkZsjAqEze2BEkWhFQJ6EyU6MdtMphMgnXqeK' then 'Marginfi'
                            else null end as stake_pool,
                                    count(distinct tx_id) as transfer,
                                    count(signer) as wallet,
                                    count(case when rn=1 then signer end) as unique_wallet,
                                     sum(amount) as amount
   from
           ( 
           select *,row_number()over(partition by signer order by block_date) as rn                           
            from
                    (
                        select *
                        from cte_deposit
                        union all
                        select *
                        from cte_reward
                        union all
                        select *
                        from cte_deposit_stake
                )
        )
group by 1,2
    
    )
where stake_pool is not null
 order by 1 desc
```

With that we can analyse trends of TVL over time and can also judge the health of any pool or platform &#x20;

Here is the link to the detailed dashboard for your reference -\


[https://analytics.topledger.xyz/tl/public/dashboards/1f5RBu3NSjEQFqOp7wcifeIYd432Uv1pG4Kk17aj](https://analytics.topledger.xyz/tl/public/dashboards/1f5RBu3NSjEQFqOp7wcifeIYd432Uv1pG4Kk17aj)

