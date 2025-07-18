---
description: >-
  The Decentralized Protocol for Your Web3 ID Create and Collect Domains With
  Ease!
---

# AllDomains

#### alldomain&#x73;**.txns**

This table has similar schema as of Solana [transactions](../solana-data/transactions.md) table

#### alldomain&#x73;**.**&#x6E;ame\_house

The table contains the parsed instructions data for AllDomains name house program. Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                     | Column Type    | Description                                                                                              |
| ----------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                     | date           | Event date                                                                                               |
| block\_time                                     | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                     | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                            | string         | Solana program address                                                                                   |
| inner\_instruction\_index                       | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](alldomains.md#input-accounts) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                              | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                               | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                          | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                          | string         | The first signature in the transaction                                                                   |
| [args](alldomains.md#args)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### **input accounts**

<table><thead><tr><th width="374.3333333333333">Field</th><th>Data Type</th></tr></thead><tbody><tr><td>nameParentAccount</td><td>string</td></tr><tr><td>collectionMint</td><td>string</td></tr><tr><td>mintAtaAccount</td><td>string</td></tr><tr><td>reverseNameAccount</td><td>string</td></tr><tr><td>nftOwner</td><td>string</td></tr><tr><td>owner</td><td>string</td></tr><tr><td>nameClassAccount</td><td>string</td></tr><tr><td>authority</td><td>string</td></tr><tr><td>nameClass</td><td>string</td></tr><tr><td>tokenDestination</td><td>string</td></tr><tr><td>nameOwner</td><td>string</td></tr><tr><td>tokenSource</td><td>string</td></tr><tr><td>nameHouseNftAta</td><td>string</td></tr><tr><td>ataAccount</td><td>string</td></tr><tr><td>tokenMetadataProgram</td><td>string</td></tr><tr><td>rent</td><td>string</td></tr><tr><td>nftRecord</td><td>string</td></tr><tr><td>metadataAccount</td><td>string</td></tr><tr><td>instructionSysvarAccount</td><td>string</td></tr><tr><td>tldHouse</td><td>string</td></tr><tr><td>nameHouse</td><td>string</td></tr><tr><td>tldState</td><td>string</td></tr><tr><td>collectionMetadata</td><td>string</td></tr><tr><td>altNameServiceProgram</td><td>string</td></tr><tr><td>splTokenProgram</td><td>string</td></tr><tr><td>mintAccount</td><td>string</td></tr><tr><td>edition</td><td>string</td></tr><tr><td>collectionMasterEditionAccount</td><td>string</td></tr><tr><td>nameParent</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>ataProgram</td><td>string</td></tr><tr><td>editionAccount</td><td>string</td></tr><tr><td>feePayer</td><td>string</td></tr><tr><td>nameAccount</td><td>string</td></tr></tbody></table>

#### args

| Field                              | Data Type      |
| ---------------------------------- | -------------- |
| collectionName                     | string         |
| tld                                | string         |
| collectionUri                      | string         |
| collectionMintBump                 | int            |
| nameHouseBump                      | int            |
| [creators](alldomains.md#creators) | array\<STRUCT> |
| sfbp                               | int            |
| tsBump                             | int            |
| thBump                             | int            |
| shdwAccount                        | string         |
| mintBump                           | int            |
| hashedName                         | array\<int>    |
| nameAccountBump                    | int            |
| nftRecordBump                      | int            |
| offset                             | int            |
| data                               | array\<int>    |



#### creators

| Field           |         |
| --------------- | ------- |
| address         | string  |
| verified        | boolean |
| percentageShare | int     |



#### alldomains.name\_service

The table contains the parsed instructions data for AllDomains name service program. Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Field                                             | Column Type    | Description                                                                                             |
| ------------------------------------------------- | -------------- | ------------------------------------------------------------------------------------------------------- |
| block\_date                                       | date           | Event date                                                                                              |
| block\_time                                       | timestamp      | The (estimated) time this block was produced                                                            |
| block\_slot                                       | bigint         | This block’s slot index in the ledger                                                                   |
| dapp                                              | string         | Solana program address                                                                                  |
| inner\_instruction\_index                         | int            | The order of inner instruction of an instruction in a txns                                              |
| [input\_accounts](alldomains.md#input-accounts-1) | array\<string> | Ordered list of accounts to pass to the program                                                         |
| instruction\_index                                | int            | The order of the instruction in a txns                                                                  |
| instruction\_type                                 | string         | Name of the function of a Solana program invoked via an instruction                                     |
| is\_inner\_instruction                            | boolean        | Whether the respective instruction of a txns has an inner instruction                                   |
| tx\_id                                            | string         | The first signature in the transaction                                                                  |
| [args](alldomains.md#args)                        | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter  |

#### input accounts

|                   |        |
| ----------------- | ------ |
| refundTarget      | string |
| nameOwner         | string |
| parentNameAccount | string |
| nameAccount       | string |
| payerAccount      | string |
| systemProgram     | string |
| owner             | string |
| parentNameOwner   | string |
| nameClassAccount  | string |

#### args

| Field           | Data Type   |
| --------------- | ----------- |
| hashedName      | array\<int> |
| space           | int         |
| expiresAt       | int         |
| offset          | int         |
| data            | array\<int> |
| nameAccountBump | int         |
| newOwner        | string      |
| newSize         | int         |



#### alldomains.tld\_house

The table contains the parsed instructions data for AllDomains tld house program. Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                       | Column Type    | Description                                                                                              |
| ------------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                       | date           | Event date                                                                                               |
| block\_time                                       | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                       | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                              | string         | Solana program address                                                                                   |
| inner\_instruction\_index                         | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](alldomains.md#input-accounts-2) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                                | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                                 | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                            | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                            | string         | The first signature in the transaction                                                                   |
| [args](alldomains.md#args-1)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input accounts

| Field                    | Data Type |
| ------------------------ | --------- |
| payer                    | string    |
| treasuryManager          | string    |
| ataProgram               | string    |
| allValidationProgram     | string    |
| refundTarget             | string    |
| nameClass                | string    |
| systemProgram            | string    |
| reverseNameAccount       | string    |
| nameOwner                | string    |
| authority                | string    |
| splTokenProgram          | string    |
| nameServiceProgram       | string    |
| tokenMint                | string    |
| mainDomain               | string    |
| feePayer                 | string    |
| tldHouse                 | string    |
| instructionSysvarAccount | string    |
| newAuthority             | string    |
| nameParent               | string    |
| fundsPubkey              | string    |
| tldState                 | string    |
| nameAccount              | string    |

#### args

| Field                              | Data Type   |
| ---------------------------------- | ----------- |
| bump                               | int         |
| price                              | int         |
| tokenPrice                         | int         |
| tldOrigin                          | string      |
| tld                                | string      |
| thBump                             | int         |
| tsBump                             | int         |
| hashedName                         | array\<int> |
| [settings](alldomains.md#settings) | struct      |
| name                               | string      |
| space                              | int         |
| reverseAccHashedName               | array\<int> |
| tmBump                             | int         |
| rnaBump                            | int         |
| nameParentBump                     | int         |
| nameAccountBump                    | int         |
| tokenMint                          | string      |
| buyingPaused                       | boolean     |
| initPaused                         | boolean     |
| psLen                              | int         |
| zeroResize                         | boolean     |
| pricingSchemes                     | \<STRUCT>   |
| version                            | string      |
| renewableConfigs                   | \<STRUCT>   |
| durationRate                       | int         |
| treasuryManager                    | string      |
| tldRegistryPubkey                  | string      |

&#x20;

**settings**



| Field                              | Data Type   |
| ---------------------------------- | ----------- |
| isWeb2                             | boolean     |
| reserved                           | array\<int> |
| purchaseBasis                      | string      |
| collectionMint                     | string      |
| isRenewable                        | boolean     |
| [creators](alldomains.md#creators) | \<STRUCT>   |
| isNonTransferable                  | boolean     |



**creators**

<table><thead><tr><th width="374">Field </th><th>Data Type</th></tr></thead><tbody><tr><td>address</td><td>string</td></tr><tr><td>share</td><td>int</td></tr></tbody></table>

####

**pricingSchemes**

| Field   | Data Type   |
| ------- | ----------- |
| mint    | string      |
| pricing | array\<int> |



**renewableConfigs**

|             |     |
| ----------- | --- |
| minDuration | int |
| maxDuration | int |

#### alldomains.tld\_manager

The table contains the parsed instructions data for AllDomains tld manager program. Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                       | Column Type    | Description                                                                                              |
| ------------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                       | date           | Event date                                                                                               |
| block\_time                                       | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                       | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                              | string         | Solana program address                                                                                   |
| inner\_instruction\_index                         | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](alldomains.md#input-accounts-3) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                                | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                                 | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                            | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                            | string         | The first signature in the transaction                                                                   |
| [args](alldomains.md#args-2)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input accounts

| Field                          | Data Type |
| ------------------------------ | --------- |
| newAuthority                   | string    |
| nameHouse                      | string    |
| nameHouseNftAta                | string    |
| tldManagerState                | string    |
| tldHouseProgram                | string    |
| mintAccount                    | string    |
| collectionMetadata             | string    |
| editionAccount                 | string    |
| tldManagerConfig               | string    |
| tokenMint                      | string    |
| nftOwner                       | string    |
| rent                           | string    |
| tldState                       | string    |
| splTokenProgram                | string    |
| instructionSysvarAccount       | string    |
| restrictedTld                  | string    |
| metadataAccount                | string    |
| mintAtaAccount                 | string    |
| nameAccount                    | string    |
| nameServiceProgram             | string    |
| systemProgram                  | string    |
| allMintAta                     | string    |
| collectionAta                  | string    |
| fundsPubkey                    | string    |
| nameClass                      | string    |
| allMintAccount                 | string    |
| collectionMint                 | string    |
| treasuryManager                | string    |
| edition                        | string    |
| nameHouseProgram               | string    |
| ataProgram                     | string    |
| collectionMasterEditionAccount | string    |
| tldPool                        | string    |
| authority                      | string    |
| tokenMetadataProgram           | string    |
| nameParent                     | string    |
| tldHouse                       | string    |
| payer                          | string    |

#### args

| Field              | Data Type      |
| ------------------ | -------------- |
| collectionUri      | string         |
| tld                | string         |
| tlds               | array\<string> |
| nftCreators        | \<STRUCT>      |
| pricingPlans       | array\<STRUCT> |
| initIsPaused       | boolean        |
| mintingIsPaused    | boolean        |
| fundsPubkey        | string         |
| nftShdwStorage     | string         |
| uri                | string         |
| ncLen              | int            |
| ppLen              | int            |
| zeroResize         | boolean        |
| newAuthority       | string         |
| pricingPlan        | \<STRUCT>      |
| urlPrefix          | string         |
| tsBump             | int            |
| thBump             | int            |
| hashedName         | array\<int>    |
| settings           | \<STRUCT>      |
| collectionName     | string         |
| collectionMintBump | int            |
| nameHouseBump      | int            |
| creators           | \<STRUCT>      |
| sfbp               | int            |
| shdwAccount        | string         |



**nftCreators**

| Field           | Data Type |
| --------------- | --------- |
| address         | string    |
| percentageShare | double    |

**pricingPlans**

|              |           |
| ------------ | --------- |
| mintingPrice | int       |
| tokenMint    | string    |
| planType     | \<STRUCT> |

**planType**

|        |           |
| ------ | --------- |
| name   | string    |
| fields | \<STRUCT> |

#### fields

|                     |     |
| ------------------- | --- |
| platform\_share     | int |
| tld\_creator\_share | int |

**pricingPlan**

|              |            |
| ------------ | ---------- |
| mintingPrice | int        |
| tokenMint    | string     |
| planType     | \<STRUCT>  |

**planType**

|        |           |
| ------ | --------- |
| name   | string    |
| fields | \<STRUCT> |

#### fields

|                     |     |
| ------------------- | --- |
| platform\_share     | int |
| tld\_creator\_share | int |

**settings**

|                   |           |
| ----------------- | --------- |
| fixedFee          | int       |
| purchaseBasis     | string    |
| verifiedCreator   | string    |
| collectionMint    | string    |
| isRenewable       | boolean   |
| creators          | \<STRUCT> |
| isNonTransferable | boolean   |

**creators**

|         |        |
| ------- | ------ |
| address | string |
| share   | int    |

#### alldomain&#x73;**.tld\_pool**

The table contains the info data for AllDomains tld pool program. Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                     | Column Type    | Description                                                                                              |
| ----------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                     | date           | Event date                                                                                               |
| block\_time                                     | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                     | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                            | string         | Solana program address                                                                                   |
| inner\_instruction\_index                       | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](alldomains.md#input-accounts) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                              | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                               | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                          | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                          | string         | The first signature in the transaction                                                                   |
| [args](alldomains.md#args)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### **input accounts**

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>tldManagerState</td><td>string</td></tr><tr><td>allMintAta</td><td>string</td></tr><tr><td>tldHouse</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>authority</td><td>string</td></tr><tr><td>allMintAccount</td><td>string</td></tr><tr><td>platformTreasury</td><td>string</td></tr><tr><td>tokenMetadataProgram</td><td>string</td></tr><tr><td>tldManagerProgram</td><td>string</td></tr><tr><td>metadataAccount</td><td>string</td></tr><tr><td> restrictedTld</td><td>string</td></tr><tr><td>nameClass</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>splTokenProgram</td><td>string</td></tr><tr><td>signer</td><td>string</td></tr><tr><td>allBuyBackAccount</td><td>string</td></tr><tr><td>collectionMetadata</td><td>string</td></tr><tr><td>collectionMasterEditionAccount</td><td>string</td></tr><tr><td>nameParent</td><td>string</td></tr><tr><td>collectionMint</td><td>string</td></tr><tr><td>contributor</td><td>string</td></tr><tr><td>treasuryManager</td><td>string</td></tr><tr><td>poolContributor</td><td>string</td></tr><tr><td>nameAccount</td><td>string</td></tr><tr><td>tokenMint</td><td>string</td></tr><tr><td>distributor</td><td>string</td></tr><tr><td>tldPoolsState</td><td>string</td></tr><tr><td>nameServiceProgram</td><td>string</td></tr><tr><td>tldManagerConfig</td><td>string</td></tr><tr><td>authorityAta</td><td>string</td></tr><tr><td>poolAta</td><td>string</td></tr><tr><td>tldState</td><td>string</td></tr><tr><td>mintAccount</td><td>string</td></tr><tr><td>contributorAta</td><td>string</td></tr><tr><td>instructionSysvarAccount</td><td>string</td></tr><tr><td>associatedTokenProgram</td><td>string</td></tr><tr><td>tldPoolState</td><td>string</td></tr><tr><td>tldHouseProgram</td><td>string</td></tr><tr><td>tldPoolConfig</td><td>string</td></tr></tbody></table>

#### args

| Field                    | Data Type   |
| ------------------------ | ----------- |
| isPaused                 | boolean     |
| tokenMint                | string      |
| platformTreasury         | string      |
| distributor              | string      |
| poolLockingAmount        | int         |
| unlockingUnsettledPeriod | int         |
| unlockingPeriod          | int         |
| softEntryLimit           | int         |
| settleLimit              | int         |
| lowerLimit               | int         |
| upperLimit               | int         |
| newAuthority             | string      |
| tld                      | string      |
| lockedAmount             | int         |
| pricingScheme            | \<STRUCT>   |
| thBump                   | int         |
| tsBump                   | int         |
| tmBump                   | int         |
| hashedName               | array\<int> |
| totalPayouts             | int         |

**pricingScheme**

| Field   | Data Type   |
| ------- | ----------- |
| mint    | string      |
| pricing | array\<int> |
