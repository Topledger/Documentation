# CM V2

#### **metaplex.cmv2**

The table contains the parsed instructions data for Candy Machine V2. Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                | Column Type    | Description                                                                                              |
| ------------------------------------------ | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                | date           | Event date                                                                                               |
| block\_time                                | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                       | string         | Solana program address                                                                                   |
| inner\_instruction\_index                  | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](cm-v2.md#input_accounts) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                         | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                          | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                     | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                     | string         | The first signature in the transaction                                                                   |
| [args](cm-v2.md#args)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input\_accounts

<table><thead><tr><th width="433.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>authority</td><td>string</td></tr><tr><td>candyMachine</td><td>string</td></tr><tr><td>candyMachineCreator</td><td>string</td></tr><tr><td>clock</td><td>string</td></tr><tr><td>instructionSysvarAccount</td><td>string</td></tr><tr><td>masterEdition</td><td>string</td></tr><tr><td>metadata</td><td>string</td></tr><tr><td>mint</td><td>string</td></tr><tr><td>mintAuthority</td><td>string</td></tr><tr><td>payer</td><td>string</td></tr><tr><td>recentBlockhashes</td><td>string</td></tr><tr><td>rent</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>tokenMetadataProgram</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>updateAuthority</td><td>string</td></tr><tr><td>wallet</td><td>string</td></tr><tr><td>collectionPda</td><td>string</td></tr><tr><td>collectionAuthorityRecord</td><td>string</td></tr><tr><td>edition</td><td>string</td></tr><tr><td>collectionMasterEdition</td><td>string</td></tr><tr><td>collectionMetadata</td><td>string</td></tr><tr><td>collectionMint</td><td>string</td></tr><tr><td>instructions</td><td>string</td></tr><tr><td>freezePda</td><td>string</td></tr><tr><td>owner</td><td>string</td></tr><tr><td>tokenAccount</td><td>string</td></tr></tbody></table>

#### args

| Field                                                   | Data Type      |
| ------------------------------------------------------- | -------------- |
| [configLines](cm-v2.md#configlines)                     | array\<STRUCT> |
| creatorBump                                             | bigint         |
| [creators](cm-v2.md#creators)                           | array\<STRUCT> |
| [endSettings](cm-v2.md#endsettings)                     | \<STRUCT>      |
| goLiveDate                                              | string         |
| index                                                   | bigint         |
| isMutable                                               | bigint         |
| itemsAvailable                                          | bigint         |
| price                                                   | bigint         |
| retainAuthority                                         | bigint         |
| sellerFeeBasisPoints                                    | bigint         |
| symbol                                                  | string         |
| uuid                                                    | string         |
| [whitelistMintSettings](cm-v2.md#whitelistmintsettings) | \<STRUCT>      |
| [hiddenSettings](cm-v2.md#hiddensettings)               | \<STRUCT>      |
| newAuthority                                            | string         |
| maxSupply                                               | bigint         |
| setFreeze                                               | bigint         |

#### configLines

| Field | Data Type |
| ----- | --------- |
| name  | string    |
| uri   | string    |

#### creators

| Field    | Data Type |
| -------- | --------- |
| address  | string    |
| share    | bigint    |
| verified | boolean   |

#### endSettings

| Field          | Data Type |
| -------------- | --------- |
| endSettingType | string    |
| number         | bigint    |

#### whitelistMintSettings

| Field         | Data Type |
| ------------- | --------- |
| discountPrice | bigint    |
| mint          | string    |
| mode          | string    |
| presale       | boolean   |

#### hiddenSettings

| Field | Data Type |
| ----- | --------- |
| hash  | bigint\[] |
| name  | string    |
| uri   | string    |
