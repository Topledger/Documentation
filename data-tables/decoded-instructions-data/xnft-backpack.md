---
description: The multisig standard you were looking for on Solana.
---

# xNFT Backpack

#### squads.txns

This table has similar schema as of Solana [transactions](../solana-data/transactions.md) table

#### squads.parsed

The table contains the parsed instructions data for [squads](https://squads.so/). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

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

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>creator</td><td>string</td></tr><tr><td>instruction</td><td>string</td></tr><tr><td>member</td><td>string</td></tr><tr><td>multisig</td><td>string</td></tr><tr><td>multisigAuth</td><td>string</td></tr><tr><td>rent</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>transaction</td><td>string</td></tr></tbody></table>

#### args

| Field                                                       | Data Type      |
| ----------------------------------------------------------- | -------------- |
| accountList                                                 | double         |
| authorityIndex                                              | int            |
| createKey                                                   | string         |
| [incomingInstruction](xnft-backpack.md#incominginstruction) | \<STRUCT>      |
| members                                                     | array\<string> |
| meta                                                        | string         |
| newMember                                                   | string         |
| oldMember                                                   | string         |
| threshold                                                   | int            |

#### incomingInstruction

| Field                         | Data Type |
| ----------------------------- | --------- |
| [keys](xnft-backpack.md#keys) | \<STRUCT> |
| programId                     | string    |
|                               |           |

#### keys

| Field      | Data Type |
| ---------- | --------- |
| isSigner   | bool      |
| isWritable | bool      |
| pubkey     | string    |
