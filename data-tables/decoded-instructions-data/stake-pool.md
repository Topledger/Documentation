---
description: A program for pooling together SOL to be staked by an off-chain agent
---

# Stake Pool

#### stake\_pool.txns&#x20;

This table has similar schema as of Solana [transactions](../solana-data/transactions.md) table

#### stake\_pool.parsed

The table contains the parsed instructions data for [Stake Pools](https://spl.solana.com/stake-pool). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                     | Column Type    | Description                                                                                              |
| ----------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                     | date           | Event date                                                                                               |
| block\_time                                     | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                     | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                            | string         | Solana program address                                                                                   |
| inner\_instruction\_index                       | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](stake-pool.md#input-accounts) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                              | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                               | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                          | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                          | string         | The first signature in the transaction                                                                   |
| [args](stake-pool.md#args)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### **input accounts**

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>pool_mint</td><td>string</td></tr><tr><td>metadata_program_id</td><td>string</td></tr><tr><td>stake_config_sysvar</td><td>string</td></tr><tr><td>validator_stake</td><td>string</td></tr><tr><td>destination_stake</td><td>string</td></tr><tr><td>stake_history_sysvar</td><td>string</td></tr><tr><td>accounts</td><td>array&#x3C;string></td></tr><tr><td>source_pool_account</td><td>string</td></tr><tr><td>clock_sysvar</td><td>string</td></tr><tr><td>token_metadata</td><td>string</td></tr><tr><td>token_program_id</td><td>string</td></tr><tr><td>manager_fee_account</td><td>string</td></tr><tr><td>rent_sysvar</td><td>string</td></tr><tr><td>validator</td><td>string</td></tr><tr><td>destination_transient_stake</td><td>string</td></tr><tr><td>payer</td><td>string</td></tr><tr><td>funding_account</td><td>string</td></tr><tr><td>system_program_id</td><td>string</td></tr><tr><td>reserve_stake</td><td>string</td></tr><tr><td>source_transfer_authority</td><td>string</td></tr><tr><td>source_validator_stake</td><td>string</td></tr><tr><td>withdraw_authority</td><td>string</td></tr><tr><td>staker</td><td>string</td></tr><tr><td>deposit_stake</td><td>string</td></tr><tr><td>manager</td><td>string</td></tr><tr><td>deposit_authority</td><td>string</td></tr><tr><td>withdrawauthority</td><td>string</td></tr><tr><td>stake_pool</td><td>string</td></tr><tr><td>source_transient_stake</td><td>string</td></tr><tr><td>referral_pool_account</td><td>string</td></tr><tr><td>manager_pool_account</td><td>string</td></tr><tr><td>sol_withdraw_authority</td><td>string</td></tr><tr><td>ephemeral_stake</td><td>string</td></tr><tr><td>destination_pool_account</td><td>string</td></tr><tr><td>destination_validator_stake</td><td>string</td></tr><tr><td>destination_system_account</td><td>string</td></tr><tr><td>validator_list</td><td>string</td></tr><tr><td>stake_program_id</td><td>string</td></tr><tr><td>destination_stake_authority</td><td>string</td></tr><tr><td>validator_vote</td><td>string</td></tr><tr><td>validator_and_transient_stake_pairs</td><td>array&#x3C;string></td></tr><tr><td>transient_stake</td><td>string</td></tr></tbody></table>

#### args

| Field                                           | Data Type |
| ----------------------------------------------- | --------- |
| [fee](stake-pool.md#fee)                        | \<STRUCT> |
| [withdrawal\_fee](stake-pool.md#withdrawal_fee) | \<STRUCT> |
| [deposit\_fee](stake-pool.md#deposit_fee)       | \<STRUCT> |
| referral\_fee                                   | int16     |
| max\_validators                                 | int32     |
| seed                                            | int32     |
| lamports                                        | bigint    |
| transient\_stake\_seed                          | bigint    |
| validator\_type                                 | string    |
| validator\_vote\_address                        | string    |
| start\_index                                    | int32     |
| no\_merge                                       | boolean   |
| pool\_tokens\_in                                | bigint    |
| lamports\_in                                    | bigint    |
| funding\_type                                   | string    |
| name                                            | string    |
| symbol                                          | string    |
| uri                                             | string    |
| ephemeral\_stake\_seed                          | bigint    |
| source\_transient\_stake\_seed                  | bigint    |
| destination\_transient\_stake\_seed             | bigint    |
| minimum\_pool\_tokens\_out                      | bigint    |
| minimum\_lamports\_out                          | bigint    |

#### fee

<table><thead><tr><th width="379">Field</th><th>Data Type</th></tr></thead><tbody><tr><td>denominator</td><td>bigint</td></tr><tr><td>numerator</td><td>bigint</td></tr><tr><td>name</td><td>string</td></tr><tr><td>fields</td><td>string</td></tr></tbody></table>

#### withdrawal\_fee

| Field       | Data Type |
| ----------- | --------- |
| denominator | bigint    |
| numerator   | bigint    |

#### deposit\_fee

| Field       | Data Type |
| ----------- | --------- |
| denominator | bigint    |
| numerator   | bigint    |
