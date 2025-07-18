---
description: A composable standard for splitting on-chain income on Solana.
---

# Sol Splits

#### splits.txns&#x20;

This table has similar schema as of Solana [transactions](../solana-data/transactions.md) table

#### splits.parsed

The table contains the parsed instructions data for [Sol Splits](https://solsplits.xyz/). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                     | Column Type    | Description                                                                                              |
| ----------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                     | date           | Event date                                                                                               |
| block\_time                                     | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                     | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                            | string         | Solana program address                                                                                   |
| inner\_instruction\_index                       | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](sol-splits.md#input-accounts) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                              | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                               | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                          | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                          | string         | The first signature in the transaction                                                                   |
| [args](sol-splits.md#args)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### **input accounts**

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>receiver8WalletTokenAccount</td><td>string</td></tr><tr><td>authority</td><td>string</td></tr><tr><td>receiver5</td><td>string</td></tr><tr><td>receiver1WalletTokenAccount</td><td>string</td></tr><tr><td>receiver9WalletTokenAccount</td><td>string</td></tr><tr><td>logWrapper</td><td>string</td></tr><tr><td>receiver6WalletTokenAccount</td><td>string</td></tr><tr><td>bubblegumProgram</td><td>string</td></tr><tr><td>receiver4WalletTokenAccount</td><td>string</td></tr><tr><td>feeTokenAccount</td><td>string</td></tr><tr><td>receiver5WalletTokenAccount</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>receiver8</td><td>string</td></tr><tr><td>receiver0</td><td>string</td></tr><tr><td>receiver4Wallet</td><td>string</td></tr><tr><td>receiver9Wallet</td><td>string</td></tr><tr><td>config</td><td>string</td></tr><tr><td>receiver3Wallet</td><td>string</td></tr><tr><td>receiver2</td><td>string</td></tr><tr><td>compressionProgram</td><td>string</td></tr><tr><td>receiver7</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>receiver0WalletTokenAccount</td><td>string</td></tr><tr><td>receiver6Wallet</td><td>string</td></tr><tr><td>receiver3</td><td>string</td></tr><tr><td>receiver7WalletTokenAccount</td><td>string</td></tr><tr><td>referral</td><td>string</td></tr><tr><td>associatedTokenProgram</td><td>string</td></tr><tr><td>receiverWallet</td><td>string</td></tr><tr><td>split</td><td>string</td></tr><tr><td>receiver0Wallet</td><td>string</td></tr><tr><td>receiver1</td><td>string</td></tr><tr><td>splitWallet</td><td>string</td></tr><tr><td>mint</td><td>string</td></tr><tr><td>receiver1Wallet</td><td>string</td></tr><tr><td>receiver8Wallet</td><td>string</td></tr><tr><td>leafDelegate</td><td>string</td></tr><tr><td>treeAuthority</td><td>string</td></tr><tr><td>treasury</td><td>string</td></tr><tr><td>receiver2Wallet</td><td>string</td></tr><tr><td>receiver</td><td>string</td></tr><tr><td>receiver3WalletTokenAccount</td><td>string</td></tr><tr><td>receiver9</td><td>string</td></tr><tr><td>merkleTree</td><td>string</td></tr><tr><td>receiver2WalletTokenAccount</td><td>string</td></tr><tr><td>receiver7Wallet</td><td> string</td></tr><tr><td>receiver4</td><td>string</td></tr><tr><td>receiver5Wallet</td><td>string</td></tr><tr><td>feeWallet</td><td>string</td></tr><tr><td>newLeafOwner</td><td>string</td></tr><tr><td>receiver6</td><td>string</td></tr><tr><td>splitTokenAccount</td><td>string</td></tr></tbody></table>

#### args

| Field                 | Data Type   |
| --------------------- | ----------- |
| public                | boolean     |
| individualSplitAmount | bigint      |
| amount                | bigint      |
| lamports              | boolean     |
| feePayer              | string      |
| unmint\_amount        | bigint      |
| kind                  | string      |
| feeFlat               | bigint      |
| feePercentage         | bigint      |
| owner                 | string      |
| root                  | array\<int> |
| dataHash              | array\<int> |
| creatorHash           | array\<int> |
| nonce                 | bigint      |
| index                 | bigint      |

