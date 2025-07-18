---
description: >-
  Token Metadata program is one of the most important programs when dealing with
  NFTs on the Solana blockchain. Its main goal is to attach additional data to
  Fungible or Non-Fungible Tokens on Solana.
---

# Token Metadata

#### **metaplex.tm**

The table contains the parsed instructions data for [Token Metadata](https://docs.metaplex.com/programs/token-metadata/overview). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                         | Column Type    | Description                                                                                              |
| --------------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                         | date           | Event date                                                                                               |
| block\_time                                         | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                         | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                                | string         | Solana program address                                                                                   |
| inner\_instruction\_index                           | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](token-metadata.md#input_accounts) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                                  | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                                   | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                              | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                              | string         | The first signature in the transaction                                                                   |
| [args](token-metadata.md#args)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input\_accounts

<table><thead><tr><th width="433.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>creator</td><td>string</td></tr><tr><td>adminFeeBAccount</td><td>string</td></tr><tr><td>edition</td><td>string</td></tr><tr><td>editionMarkPda</td><td>string</td></tr><tr><td>masterEdition</td><td>string</td></tr><tr><td>metadata</td><td>string</td></tr><tr><td>mint</td><td>string</td></tr><tr><td>mintAuthority</td><td>string</td></tr><tr><td>newEdition</td><td>string</td></tr><tr><td>newMetadata</td><td>string</td></tr><tr><td>newMetadataUpdateAuthority</td><td>string</td></tr><tr><td>newMint</td><td>string</td></tr><tr><td>newMintAuthority</td><td>string</td></tr><tr><td>owner</td><td>string</td></tr><tr><td>payer</td><td>string</td></tr><tr><td>rent</td><td>string</td></tr><tr><td>safetyDepositBox</td><td>string</td></tr><tr><td>safetyDepositStore</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>token</td><td>string</td></tr><tr><td>tokenAccount</td><td>string</td></tr><tr><td>tokenAccountOwner</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>tokenVaultProgram</td><td>string</td></tr><tr><td>updateAuthority</td><td>string</td></tr><tr><td>vault</td><td>string</td></tr><tr><td>vaultAuthority</td><td>string</td></tr><tr><td>delegate</td><td>string</td></tr><tr><td>collection</td><td>string</td></tr><tr><td>collectionAuthority</td><td>string</td></tr><tr><td>collectionAuthorityRecord</td><td>string</td></tr><tr><td>collectionMasterEditionAccount</td><td>string</td></tr><tr><td>collectionMint</td><td>string</td></tr><tr><td>newCollectionAuthority</td><td>string</td></tr><tr><td>oneTimeAuth</td><td>string</td></tr><tr><td>printingMint</td><td>string</td></tr><tr><td>delegateAuthority</td><td>string</td></tr><tr><td>revokeAuthority</td><td>string</td></tr><tr><td>masterEditionAccount</td><td>string</td></tr><tr><td>splTokenProgram</td><td>string</td></tr><tr><td>collectionMetadata</td><td>string</td></tr><tr><td>ataProgram</td><td>string</td></tr><tr><td>useAuthority</td><td>string</td></tr><tr><td>burner</td><td>string</td></tr><tr><td>ownerTokenAccount</td><td>string</td></tr><tr><td>useAuthorityRecord</td><td>string</td></tr><tr><td>user</td><td>string</td></tr><tr><td>editionMarkerAccount</td><td>string</td></tr><tr><td>masterEditionMint</td><td>string</td></tr><tr><td>masterEditionTokenAccount</td><td>string</td></tr><tr><td>printEditionAccount</td><td>string</td></tr><tr><td>printEditionMint</td><td>string</td></tr><tr><td>printEditionTokenAccount</td><td>string</td></tr></tbody></table>

#### args

| Field                                                    | Data Type |
| -------------------------------------------------------- | --------- |
| [data](token-metadata.md#data)                           | \<STRUCT> |
| edition                                                  | bigint    |
| isMutable                                                | boolean   |
| maxSupply                                                | bigint    |
| primarySaleHappened                                      | boolean   |
| updateAuthority                                          | string    |
| size                                                     | bigint    |
| [collectionDetails](token-metadata.md#collectiondetails) | \<STRUCT> |
| numberOfUses                                             | bigint    |

#### data

| Field                                      | Data Type      |
| ------------------------------------------ | -------------- |
| [creators](token-metadata.md#creators)     | array\<STRUCT> |
| name                                       | string         |
| sellerFeeBasisPoints                       | bigint         |
| symbol                                     | string         |
| uri                                        | string         |
| [collection](token-metadata.md#collection) | \<STRUCT>      |
| [uses](token-metadata.md#uses)             | \<STRUCT>      |

#### collectionDetails

| Field | Data Type |
| ----- | --------- |
| name  | string    |
| size  | bigint    |

#### creators

| Field    | Data Type |
| -------- | --------- |
| address  | string    |
| share    | bigint    |
| verified | boolean   |

#### collection

| Field    | Data Type |
| -------- | --------- |
| key      | string    |
| verified | boolean   |

#### uses

| Field     | Data Type |
| --------- | --------- |
| remaining | bigint    |
| total     | bigint    |
| useMethod | string    |
