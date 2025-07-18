---
description: >-
  Auction House is a protocol for marketplaces to implement a decentralized
  sales contract. It is simple, fast and very cheap. Auction House is a Solana
  program available on Mainnet Beta and Devnet.
---

# Auction House

#### **metaplex.ah**

The table contains the parsed instructions data for [Auction House](https://docs.metaplex.com/programs/auction-house/overview). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                        | Column Type    | Description                                                                                              |
| -------------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                        | date           | Event date                                                                                               |
| block\_time                                        | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                        | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                               | string         | Solana program address                                                                                   |
| inner\_instruction\_index                          | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](auction-house.md#input_accounts) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                                 | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                                  | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                             | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                             | string         | The first signature in the transaction                                                                   |
| [args](auction-house.md#args)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input\_accounts

<table><thead><tr><th width="433.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>ataProgram</td><td>string</td></tr><tr><td>auctionHouse</td><td>string</td></tr><tr><td>auctionHouseFeeAccount</td><td>string</td></tr><tr><td>authority</td><td>string</td></tr><tr><td>buyer</td><td>string</td></tr><tr><td>escrowPaymentAccount</td><td>string</td></tr><tr><td>freeSellerTradeState</td><td>string</td></tr><tr><td>metadata</td><td>string</td></tr><tr><td>programAsSigner</td><td>string</td></tr><tr><td>receiptAccount</td><td>string</td></tr><tr><td>rent</td><td>string</td></tr><tr><td>seller</td><td>string</td></tr><tr><td>sellerTradeState</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>tokenAccount</td><td>string</td></tr><tr><td>tokenMint</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>tradeState</td><td>string</td></tr><tr><td>treasuryMint</td><td>string</td></tr><tr><td>wallet</td><td>string</td></tr><tr><td>auctionHouseTreasury</td><td>string</td></tr><tr><td>buyerReceiptTokenAccount</td><td>string</td></tr><tr><td>buyerTradeState</td><td>string</td></tr><tr><td>freeTradeState</td><td>string</td></tr><tr><td>paymentAccount</td><td>string</td></tr><tr><td>sellerPaymentReceiptAccount</td><td>string</td></tr><tr><td>transferAuthority</td><td>string</td></tr><tr><td>feeWithdrawalDestination</td><td>string</td></tr><tr><td>newAuthority</td><td>string</td></tr><tr><td>payer</td><td>string</td></tr><tr><td>treasuryWithdrawalDestination</td><td>string</td></tr><tr><td>treasuryWithdrawalDestinationOwner</td><td>string</td></tr><tr><td>bookkeeper</td><td>string</td></tr><tr><td>instruction</td><td>string</td></tr><tr><td>receipt</td><td>string</td></tr><tr><td>bidReceipt</td><td>string</td></tr><tr><td>listingReceipt</td><td>string</td></tr><tr><td>purchaseReceipt</td><td>string</td></tr><tr><td>ahAuctioneerPda</td><td>string</td></tr><tr><td>auctioneerAuthority</td><td>string</td></tr></tbody></table>

#### args

| Field                | Data Type |
| -------------------- | --------- |
| buyerPrice           | bigint    |
| escrowPaymentBump    | bigint    |
| freeTradeStateBump   | bigint    |
| programAsSignerBump  | bigint    |
| tokenSize            | bigint    |
| tradeStateBump       | bigint    |
| amount               | bigint    |
| canChangeSalePrice   | bigint    |
| requiresSignOff      | bigint    |
| sellerFeeBasisPoints | bigint    |
| bump                 | bigint    |
| feePayerBump         | bigint    |
| treasuryBump         | bigint    |
| receiptBump          | bigint    |
| purchaseReceiptBump  | bigint    |
