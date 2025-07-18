---
description: >-
  Switchboard allows builders to unlock the power of Solana by creating high
  performance data feeds from any API.
---

# Switchboard V2

#### switchboar&#x64;**.txns**

This table has similar schema as of Solana [transactions](../solana-data/transactions.md) table

#### switchboar&#x64;**.parsed**

The table contains the parsed instructions data for [Switchboard](https://docs.switchboard.xyz/solana/program/mainnet). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name               | Column Type    | Description                                                                                              |
| ------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date               | date           | Event date                                                                                               |
| block\_time               | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot               | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                      | string         | Solana program address                                                                                   |
| inner\_instruction\_index | int            | The order of inner instruction of an instruction in a txns                                               |
| input\_accounts           | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index        | int            | The order of the instruction in a txns                                                                   |
| instruction\_type         | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction    | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                    | string         | The first signature in the transaction                                                                   |
| args                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### **input accounts**

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>aggregator</td><td>string</td></tr><tr><td>authority</td><td>string</td></tr><tr><td>callbackPid</td><td>string</td></tr><tr><td>crank</td><td>string</td></tr><tr><td>crankDataBuffer</td><td>string</td></tr><tr><td>dataBuffer</td><td>string</td></tr><tr><td>escrow</td><td>string</td></tr><tr><td>feedPermission</td><td>string</td></tr><tr><td>funder</td><td>string</td></tr><tr><td>gcOracle</td><td>string</td></tr><tr><td>historyBuffer</td><td>string</td></tr><tr><td>instructionsSysvar</td><td>string</td></tr><tr><td>lease</td><td>string</td></tr><tr><td>mint</td><td>string</td></tr><tr><td>oracle</td><td>string</td></tr><tr><td>oracleAuthority</td><td>string</td></tr><tr><td>oraclePermission</td><td>string</td></tr><tr><td>oracleQueue</td><td>string</td></tr><tr><td>oracleWallet</td><td>string</td></tr><tr><td>owner</td><td>string</td></tr><tr><td>payerAuthority</td><td>string</td></tr><tr><td>payerWallet</td><td>string</td></tr><tr><td>payoutWallet</td><td>string</td></tr><tr><td>permission</td><td>string</td></tr><tr><td>programState</td><td>string</td></tr><tr><td>queue</td><td>string</td></tr><tr><td>queueAuthority</td><td>string</td></tr><tr><td>queueDataBuffer</td><td>string</td></tr><tr><td>recentBlockhashes</td><td>string</td></tr><tr><td>tokenAccount</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>vrf</td><td>string</td></tr></tbody></table>

#### args

| Field                     | Data Type |
| ------------------------- | --------- |
| counter                   | int       |
| failOpenOnAccountMismatch | bool      |
| leaseBump                 | int       |
| leaseBumps                | string    |
| loadAmount                | float     |
| mantissa                  | float     |
| nonce                     | int       |
| permissionBump            | int       |
| permissionBumps           | string    |
| proofEncoded              | string    |
| scale                     | int       |
| stateBump                 | int       |



#### switchboar&#x64;**.events**

This table has all the switchboard v2 historically parsed events.

| Field                            | Column Type | Description                                  |
| -------------------------------- | ----------- | -------------------------------------------- |
| block\_date                      | date        | Event date                                   |
| block\_time                      | timestamp   | The (estimated) time this block was produced |
| block\_slot                      | bigint      | This block’s slot index in the ledger        |
| tx\_id                           | string      | The first signature in the transaction       |
| dapp                             | string      | Solana program address                       |
| event\_type                      |             | The name of the event emitted                |
| [args](switchboard-v2.md#args-1) | \<STRUCT>   | The arguments of the respective event        |



#### args

| Field                                          | Data Type      |
| ---------------------------------------------- | -------------- |
| alpha                                          | string         |
| amount                                         | bigint         |
| authorityPubkey                                | string         |
| counter                                        | bigint         |
| existingAmount                                 | bigint         |
| feedPubkey                                     | string         |
| funder                                         | string         |
| jobPubkeys                                     | array\<string> |
| leasePubkey                                    | string         |
| loadAmount                                     | bigint         |
| oraclePubkey                                   | string         |
| oraclePubkeys                                  | array\<string> |
| [oracleValues](switchboard-v2.md#oraclevalues) | array\<STRUCT> |
| queueAuthority                                 | string         |
| queuePubkey                                    | string         |
| remainingFunds                                 | bigint         |
| roundSlot                                      | bigint         |
| slot                                           | bigint         |
| timestamp                                      | timestamp      |
| [val](switchboard-v2.md#val)                   | \<STRUCT>      |
| vrfPubkey                                      | string         |
| walletPubkey                                   | string         |

#### oracleValues

| Field    | Data Type |
| -------- | --------- |
| mantissa | double    |
| scale    | int       |



#### val

| Field    | Data Type |
| -------- | --------- |
| mantissa | double    |
| scale    | int       |
