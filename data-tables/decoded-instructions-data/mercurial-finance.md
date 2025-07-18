---
description: >-
  Mercurial is building new liquidity systems to maximise the utility and yield
  of stable assets on Solana.
---

# Mercurial Finance

#### mercuria&#x6C;**.parsed**

The table contains the parsed instructions data for [Mercurial Finance](https://www.mercurial.finance/about). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

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

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>authority</td><td>string</td></tr><tr><td>destinationTokenAccount</td><td>string</td></tr><tr><td>poolTokenMint</td><td>string</td></tr><tr><td>sourceTokenAccount</td><td>string</td></tr><tr><td>sourceTokenAccounts</td><td>array&#x3C;string></td></tr><tr><td>swapInfo</td><td>string</td></tr><tr><td>tokenAccounts</td><td>array&#x3C;string></td></tr><tr><td>tokenProgramId</td><td>string</td></tr><tr><td>userLpTokenAccount</td><td>string</td></tr><tr><td>userTransferAuthority</td><td>string</td></tr><tr><td>adminTokenMint</td><td>string</td></tr><tr><td>tokenMints</td><td>array&#x3C;string></td></tr></tbody></table>

#### args

| Field                      | Data Type      |
| -------------------------- | -------------- |
| deposit\_amounts           | array\<bigint> |
| in\_amount                 | bigint         |
| min\_mint\_amount          | bigint         |
| minimum\_amounts           | array\<bigint> |
| minimum\_out\_amount       | bigint         |
| unmint\_amount             | bigint         |
| admin\_settings            | \<STRUCT>      |
| amplification\_coefficient | bigint         |
| fee\_numerator             | bigint         |
| n\_coins                   | bigint         |
| nonce                      | bigint         |

#### admin\_settings

| Field                   | Data Type |
| ----------------------- | --------- |
| add\_liquidity\_enabled | boolean   |
| swap\_enabled           | boolean   |

