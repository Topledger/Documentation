---
description: >-
  A full suite DeFi platform to trade crypto, derivatives, NFTs, and single
  sided liquidity pools with yield farming.
---

# GooseFX

#### goose.parsed

The table contains the parsed instructions data for [goosefx](https://www.goosefx.io/). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

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

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>accounts</td><td>array&#x3C;string></td></tr><tr><td>controller</td><td>string</td></tr><tr><td>feeCollector</td><td>string</td></tr><tr><td>feeCollectorAta</td><td>string</td></tr><tr><td>liabilityVaultIn</td><td>string</td></tr><tr><td>liabilityVaultOut</td><td>string</td></tr><tr><td>liquidityAccount</td><td>string</td></tr><tr><td>pair</td><td>string</td></tr><tr><td>rent</td><td>string</td></tr><tr><td>rtVault</td><td>string</td></tr><tr><td>ssl</td><td>string</td></tr><tr><td>sslIn</td><td>string</td></tr><tr><td>sslOut</td><td>string</td></tr><tr><td>swappedLiabilityVaultIn</td><td>string</td></tr><tr><td>swappedLiabilityVaultOut</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>userInAta</td><td>string</td></tr><tr><td>userOutAta</td><td>string</td></tr><tr><td>userRtAta</td><td>string</td></tr><tr><td>userWallet</td><td>string</td></tr></tbody></table>

#### args

| Field           | Data Type |
| --------------- | --------- |
| amount          | bigint    |
| amountIn        | bigint    |
| minOut          | bigint    |
| withdrawPercent | bigint    |

