# CM V1

#### **metaplex.cmv1**

The table contains the parsed instructions data for Candy Machine V2. Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                | Column Type    | Description                                                                                              |
| ------------------------------------------ | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                | date           | Event date                                                                                               |
| block\_time                                | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                       | string         | Solana program address                                                                                   |
| inner\_instruction\_index                  | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](cm-v1.md#input_accounts) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                         | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                          | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                     | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                     | string         | The first signature in the transaction                                                                   |
| [args](cm-v1.md#args)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input\_accounts

<table><thead><tr><th width="433.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>authority</td><td>string</td></tr><tr><td>candyMachine</td><td>string</td></tr><tr><td>clock</td><td>string</td></tr><tr><td>config</td><td>string</td></tr><tr><td>masterEdition</td><td>string</td></tr><tr><td>metadata</td><td>string</td></tr><tr><td>mint</td><td>string</td></tr><tr><td>mintAuthority</td><td>string</td></tr><tr><td>payer</td><td>string</td></tr><tr><td>rent</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>tokenMetadataProgram</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>updateAuthority</td><td>string</td></tr><tr><td>wallet</td><td>string</td></tr></tbody></table>

#### args

| Field                               | Data Type      |
| ----------------------------------- | -------------- |
| bump                                | int            |
| [configLines](cm-v1.md#configlines) | array\<STRUCT> |
| [data](cm-v1.md#data)               | \<STRUCT>      |

#### configLines

| Field | Data Type |
| ----- | --------- |
| name  | string    |
| uri   | string    |

#### data

| Field                         | Data Type      |
| ----------------------------- | -------------- |
| [creators](cm-v1.md#creators) | array\<STRUCT> |
| itemsAvailable                | int            |
| maxNumberOfLines              | int            |
| maxSupply                     | boolean        |
| price                         | bigint         |
| retainAuthority               | boolean        |
| sellerFeeBasisPoints          | int            |
| symbol                        | string         |
| uuid                          | string         |

#### creators

| Field    | Data Type |
| -------- | --------- |
| address  | string    |
| share    | int       |
| verified | boolean   |
