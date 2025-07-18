---
description: Borrow and lend against your NFTs Instantly.
---

# Sharky

#### sharkyfi.txns

This table has similar schema as of Solana [transactions](../solana-data/transactions.md) table

#### sharkyfi.parsed

The table contains the parsed instructions data for [sharky](https://sharky.fi/). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                 | Column Type    | Description                                                                                              |
| ------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                 | date           | Event date                                                                                               |
| block\_time                                 | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                 | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                        | string         | Solana program address                                                                                   |
| inner\_instruction\_index                   | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](sharky.md#input-accounts) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                          | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                           | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                      | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                      | string         | The first signature in the transaction                                                                   |
| [args](sharky.md#args)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### **input accounts**

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>associatedTokenProgram</td><td>string</td></tr><tr><td>authority</td><td>string</td></tr><tr><td>borrower</td><td>string</td></tr><tr><td>borrowerCollateralAccount</td><td>string</td></tr><tr><td>collateralMint</td><td>string</td></tr><tr><td>collector</td><td>string</td></tr><tr><td>escrow</td><td>string</td></tr><tr><td>escrowCollateralTokenAccount</td><td>string</td></tr><tr><td>escrowTokenAccount</td><td>string</td></tr><tr><td>feeAuthority</td><td>string</td></tr><tr><td>instructionSysvarAccount</td><td>string</td></tr><tr><td>issuer</td><td>string</td></tr><tr><td>issuerCollateralTokenAccount</td><td>string</td></tr><tr><td>lender</td><td>string</td></tr><tr><td>lenderCollateralAccount</td><td>string</td></tr><tr><td>lenderValueTokenAccount</td><td>string</td></tr><tr><td>loan</td><td>string</td></tr><tr><td>metadata</td><td>string</td></tr><tr><td>mintCounter</td><td>string</td></tr><tr><td>mplTokenMetadataProgram</td><td>string</td></tr><tr><td>newEscrow</td><td>string</td></tr><tr><td>newEscrowCollateralTokenAccount</td><td>string</td></tr><tr><td>newLender</td><td>string</td></tr><tr><td>newLoan</td><td>string</td></tr><tr><td>nftList</td><td>string</td></tr><tr><td>orderBook</td><td>string</td></tr><tr><td>payer</td><td>string</td></tr><tr><td>programVersion</td><td>string</td></tr><tr><td>rent</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>tokenManager</td><td>string</td></tr><tr><td>tokenManagerProgram</td><td>string</td></tr><tr><td>tokenManagerTokenAccount</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>valueMint</td><td>string</td></tr></tbody></table>

#### args

| Field                                    | Data Type |
| ---------------------------------------- | --------- |
| [orderBookType](sharky.md#orderbooktype) | \<STRUCT> |
| [apy](sharky.md#apy)                     | \<STRUCT> |
| [loanTerms](sharky.md#loanterms)         | \<STRUCT> |
| feePermillicentage                       | int       |
| feeAuthority                             | string    |
| escrowBump                               | int       |
| principalLamports                        | int       |
| [termsChoice](sharky.md#termschoice)     | \<STRUCT> |
| expectedLoan                             | string    |
| nftListIndex                             | int       |
| editionNumber                            | int       |
| isProgrammable                           | bool      |
| isCollateralFrozen                       | bool      |
| collectionName                           | string    |
| [mints](sharky.md#mints)                 | \<STRUCT> |
| version                                  | int       |

#### **orderBookType**&#x20;

| Field                      | Data Type |
| -------------------------- | --------- |
| name                       | string    |
| [fields](sharky.md#fields) | \<STRUCT> |

#### **fields**

| Field           | Data Type |
| --------------- | --------- |
| collection\_key | string    |
| list\_account   | \<STRUCT> |

#### **apy**

| Field                      | Data Type |
| -------------------------- | --------- |
| name                       | string    |
| [fields](sharky.md#fields) | \<STRUCT> |

#### **fields**

| Field | Data Type |
| ----- | --------- |
| apy   | int       |

#### **loanTerms**

| Field                      | Data Type |
| -------------------------- | --------- |
| name                       | string    |
| [fields](sharky.md#fields) | \<STRUCT> |

#### **fields**

| Field                    | Data Type |
| ------------------------ | --------- |
| [terms](sharky.md#terms) | \<STRUCT> |

#### **terms**

| Field                      | Data Type |
| -------------------------- | --------- |
| name                       | string    |
| [fields](sharky.md#fields) | \<STRUCT> |

#### fields

| Field    | Data Type |
| -------- | --------- |
| duration | string    |



#### **termsChoice**

| Field                      | Data Type |
| -------------------------- | --------- |
| name                       | string    |
| [fields](sharky.md#fields) | \<STRUCT> |

#### fields

| Field    | Data Type |
| -------- | --------- |
| duration | string    |

#### mints

| Field | Data Type |
| ----- | --------- |
| index | int       |
| mint  | string    |
