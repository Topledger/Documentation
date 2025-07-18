---
description: >-
  Saber is an automated market maker and liquidity pool on Solana designed for
  extremely efficient trading between similarly priced (pegged) assets, without
  an opportunity cost.
---

# Saber

#### **saber.parsed**

The table contains the parsed instructions data for [`Saber`](https://docs.saber.so/). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

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

#### input\_accounts

<table><thead><tr><th width="433.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>adminFeeAAccount</td><td>string</td></tr><tr><td>adminFeeBAccount</td><td>string</td></tr><tr><td>authority</td><td>string</td></tr><tr><td>poolAccountDeposit</td><td>string</td></tr><tr><td>poolMintAccount</td><td>string</td></tr><tr><td>sourcePoolAccount</td><td>string</td></tr><tr><td>stableSwap</td><td>string</td></tr><tr><td>tokenAAuthority</td><td>string</td></tr><tr><td>tokenABAdminFeeAccount</td><td>string</td></tr><tr><td>tokenABBaseAccountSwapFrom</td><td>string</td></tr><tr><td>tokenABBaseAccountSwapInto</td><td>string</td></tr><tr><td>tokenABBaseSwapAccountWithdrawFrom</td><td>string</td></tr><tr><td>tokenABBaseUserAccountCredit</td><td>string</td></tr><tr><td>tokenABDestinationAccount</td><td>string</td></tr><tr><td>tokenABQuoteSwapAccountExchange</td><td>string</td></tr><tr><td>tokenABSourceAccount</td><td>string</td></tr><tr><td>tokenABaseAccountDepositInto</td><td>string</td></tr><tr><td>tokenASwapAccountWithdrawFrom</td><td>string</td></tr><tr><td>tokenAUserAccount</td><td>string</td></tr><tr><td>tokenBAuthority</td><td>string</td></tr><tr><td>tokenBBaseAccountDepositInto</td><td>string</td></tr><tr><td>tokenBSwapAccountWithdrawFrom</td><td>string</td></tr><tr><td>tokenBUserAccount</td><td>string</td></tr><tr><td>tokenProgramId</td><td>string</td></tr><tr><td>userAuthority</td><td>string</td></tr></tbody></table>

#### args

| Field                     | Data Type |
| ------------------------- | --------- |
| amount\_in                | bigint    |
| min\_mint\_amount         | bigint    |
| minimum\_amount\_out      | bigint    |
| minimum\_token\_a\_amount | bigint    |
| minimum\_token\_amount    | bigint    |
| minimum\_token\_b\_amount | bigint    |
| pool\_token\_amount       | bigint    |
| token\_a\_amount          | bigint    |
| token\_b\_amount          | bigint    |

