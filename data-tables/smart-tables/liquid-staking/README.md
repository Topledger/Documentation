---
description: All liquid staking protocols decoded transactions.
---

# Liquid Staking

#### How we are indexing our cnft\_trades table?&#x20;

We have written a Substreams to index this data. Substreams is a powerful blockchain indexing technology developed by [StreamingFast](https://www.streamingfast.io/).

You can take a look at our indexing code [here](https://github.com/Topledger/solana-programs/tree/main/liquid-staking). The table below contains the project names and their respective program addresses that we have included in our liquid\_staking table.

<table><thead><tr><th width="160">Platform Name</th><th width="245">DAPP</th><th>Instructions</th></tr></thead><tbody><tr><td>SPL Stake Pool</td><td><a href="https://solscan.io/account/SPoo1Ku8WFXoNDMHPsrGSTSG1Y47rzgn41SLUNakuHy">SPoo1Ku8WFXoNDMHPsrGSTSG1Y47rzgn41SLUNakuHy</a></td><td>DepositSol, DepositStake, WithdrawSol, WithdrawStake</td></tr><tr><td>Marinade</td><td><a href="https://solscan.io/account/MarBmsSgKXdrN1egZf5sqe1TMai9K1rChYNDJgjq7aD">MarBmsSgKXdrN1egZf5sqe1TMai9K1rChYNDJgjq7aD</a></td><td>Deposit, DepositStakeAccount, Claim, OrderUnstake,  UpdateDeactivated, UpdateActive, LiquidUnstake</td></tr></tbody></table>

#### liquid\_staking

The table below contains all the cnft\_trades table columns , such as signer, stake\_pool, reserve\_stake, withdraw\_authority, pool\_mint, etc.

| Column Name               | Column Type | Description                                                                                                |
| ------------------------- | ----------- | ---------------------------------------------------------------------------------------------------------- |
| block\_time               | timestamp   | The (estimated) time this block was produced                                                               |
| block\_slot               | bigint      | This block’s slot index in the ledger                                                                      |
| tx\_id                    | string      | The first signature in the transaction                                                                     |
| signer                    | string      | The initial value from the account\_keys array that initiates the transaction and pays the transaction fee |
| amount                    | double      | The amount of token that is to be staked                                                                   |
| category                  | string      | various categories trade such as buy, sell, etc.                                                           |
| stake\_pool               | string      | The LST pool in which the token is staked                                                                  |
| withdraw\_authority       | string      | The authority assigned by the platform to approve any un-staking                                           |
| reserve\_stake            | string      | the reserve account of the stake pool                                                                      |
| validator\_stake          | string      | The authority assigned by the platform to validate staking                                                 |
| pool\_mint                | string      | The token mint of the reserve account                                                                      |
| fee\_account              | string      | The fee account of the stake pool                                                                          |
| mint\_amount              | double      | The amount of LST token minted in return of deposit of token                                               |
| burn\_amount              | double      | Amount of LST token that is getting burnt upon de-staking                                                  |
| staking\_reward           | double      | The reward of staking as accrued by the stacker                                                            |
| liq\_pool\_sol\_leg       | string      |                                                                                                            |
| fee\_amount               | double      | The amount of fee paid to fee account of stake pool                                                        |
| is\_inner\_instruction    | boolean     | Tells whether there is any inner instruction in the transaction or not                                     |
| instruction\_index        | bigint      | Index of various instructions in a transaction                                                             |
| instruction\_type         | string      | Name of the function of a Solana program invoked via an instruction                                        |
| inner\_instruction\_index | bigint      | Index of various inner instructions in a instruction                                                       |
| outer\_program            | string      | The main program of an instruction                                                                         |
| inner\_program            | string      | The inner programs under the main/outer program                                                            |
| txn\_fee                  | big\_int    | Fee this transaction was charged, as paid by first account                                                 |
| platform                  | string      | Name of the platform on which trade is happening                                                           |
| partition\_0              | string      | The date on which the block was produced                                                                   |



####
