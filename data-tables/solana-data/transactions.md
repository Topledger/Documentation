---
description: >-
  A transaction is one or more instructions signed by a client using one or more
  key-pairs and executed atomically with only two possible outcomes: success or
  failure.
---

# Transactions

**tl-solana-merged-data.transactions**

The table contains the transaction data for Solana blockchain. Data related to account, program, program activity, token balance, etc. is available here.

<table><thead><tr><th width="258.3333333333333">Column Name</th><th>Column Type</th><th>Description</th></tr></thead><tbody><tr><td>block_slot</td><td>bigint</td><td>This block’s slot index in the ledger</td></tr><tr><td>block_time</td><td>timestamp</td><td>The (estimated) time this block was produced</td></tr><tr><td>block_date</td><td>date</td><td>Event date</td></tr><tr><td>index</td><td>bigint</td><td>Index into the block’s transactions</td></tr><tr><td>fee</td><td>bigint</td><td>Fee this transaction was charged, as paid by first account</td></tr><tr><td>block_hash</td><td>string</td><td>The hash of this block, base-58 encoded</td></tr><tr><td>error</td><td>STRUCT</td><td>Only if success is true</td></tr><tr><td>required_signatures</td><td>bigint</td><td>The total number of signatures required to make the transaction valid</td></tr><tr><td>readonly_signed_accounts </td><td>bigint</td><td>The number of read-only signed accounts</td></tr><tr><td>readonly_unsigned_account</td><td>bigint</td><td>The number of read-only unsigned accounts</td></tr><tr><td>id</td><td>string</td><td>The first signature in the transaction</td></tr><tr><td>success</td><td>boolean</td><td>The transaction was valid and thus committed.</td></tr><tr><td>recent_block_hash</td><td>string</td><td>The hash of a recent block in the ledger, used to prevent transaction duplication and to give transactions lifetimes</td></tr><tr><td>instructions</td><td>array&#x3C;STRUCT instructions></td><td>Instructions to execute (in order)</td></tr><tr><td>account_keys</td><td>array&#x3C;string></td><td>The account keys used in the transaction</td></tr><tr><td>log_messages</td><td>array&#x3C;string></td><td>The log messages emitted by the transaction</td></tr><tr><td>pre_balances</td><td>array&#x3C;bigint></td><td>Array of account balances before the transaction was processed. The i-th balance is the balance of the i-th account key in account_keys</td></tr><tr><td>post_balances</td><td>array&#x3C;bigint></td><td>Array of account balances after the transaction was processed. The i-th balance is the balance of the i-th account key in account_keys</td></tr><tr><td>pre_token_balances</td><td>array&#x3C;STRUCT token_balance></td><td>List of token balances from before the transaction was processed or omitted if token balance recording was not yet enabled during this transaction</td></tr><tr><td>post_token_balances</td><td>array&#x3C;STRUCT token_balance></td><td>List of token balances from after the transaction was processed or omitted if token balance recording was not yet enabled during this transaction</td></tr><tr><td>signatures</td><td>array&#x3C;string></td><td>A list of base-58 encoded signatures applied to the transaction. Always of length numRequiredSignatures</td></tr><tr><td>signer</td><td>string</td><td>The initial value from the account_keys array that initiates the transaction and pays the transaction fee</td></tr></tbody></table>

### Struct Definitions

Some columns in the transactions table has the data type STRUCT. It allows for representing nested hierarchical data and has key-value pairs. Let's go into what each one of them contains.

#### token\_balances (pre/post)

| Field   | Data type | Description                                                                                                                                                                 |
| ------- | --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| account | string    | The account key of the account that the token balance is provided for                                                                                                       |
| mint    | string    | Public key of the token’s mint. This is an account that stores metadata about the token: The supply, number of decimals, and various authorities with control over the mint |
| amount  | double    | Derived from the token balance's raw amount. (ui\_token\_amount.amount) by (ui\_token\_amount.decimals)                                                                     |

#### instructions

| Field               | Data type                          | Description                                                   |
| ------------------- | ---------------------------------- | ------------------------------------------------------------- |
| account\_arguments  | array\<string>                     | Ordered list of accounts to pass to the program               |
| data                | string                             | Program input data in a base-58 string                        |
| executing\_account  | string                             | The account key of the program that executed this instruction |
| inner\_instructions | array\<STRUCT inner\_instructions> | The instructions invoked by this instruction                  |

#### inner\_instructions

| Field              | Data type      | Description                                                   |
| ------------------ | -------------- | ------------------------------------------------------------- |
| account\_arguments | array\<string> | Ordered list of accounts to pass to the program               |
| data               | string         | Program input data in a base-58 string                        |
| executing\_account | string         | The account key of the program that executed this instruction |

#### error

| Field              | Data type | Description                        |
| ------------------ | --------- | ---------------------------------- |
| instruction\_index | bigint    | The instruction number that failed |
| message            | string    | The error message                  |
