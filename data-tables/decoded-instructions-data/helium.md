---
description: >-
  This People's Network represents a paradigm shift for decentralized wireless
  infrastructure.
---

# Helium

**helium.txns**

This table has similar schema as of Solana [transactions](../solana-data/transactions.md) table

#### helium.ciruit\_breaker

The table contains the parsed instructions data for helium [circuit breaker](https://www.helium.com/). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                 | Column Type    | Description                                                                                              |
| ------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                 | date           | Event date                                                                                               |
| block\_time                                 | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                 | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                        | string         | Solana program address                                                                                   |
| inner\_instruction\_index                   | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](helium.md#input-accounts) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                          | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                           | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                      | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                      | string         | The first signature in the transaction                                                                   |
| [args](helium.md#args)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### **input accounts**

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>mint</td><td>string</td></tr><tr><td>payer</td><td>string</td></tr><tr><td>mintAuthority</td><td>string</td></tr><tr><td>owner</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>to</td><td>string</td></tr><tr><td>authority</td><td>string</td></tr><tr><td>syatemProgram</td><td>string</td></tr><tr><td>circuitBreaker</td><td>string</td></tr><tr><td>tokenAccount</td><td>string</td></tr><tr><td>from</td><td>string</td></tr></tbody></table>

#### args

| Field         | Data Type |
| ------------- | --------- |
| authority     | string    |
| mintAuthority | string    |
| config        | \<STRUCT> |
| owner         | string    |
| amount        | int       |
| newAuthority  | int       |

#### config

| Field             | Data Type |
| ----------------- | --------- |
| windowSizeSeconds | int       |
| thresholdType     | string    |
| threshold         | int       |

#### helium.data\_credits

The  table contains the parsed instructions data for [data credits](https://www.helium.com/) on helium . Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                   | Column Type    | Description                                                                                              |
| --------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                   | date           | Event date                                                                                               |
| block\_time                                   | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                   | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                          | string         | Solana program address                                                                                   |
| inner\_instruction\_index                     | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](helium.md#input-accounts-1) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                            | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                             | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                        | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                        | string         | The first signature in the transaction                                                                   |
| [args](helium.md#args-1)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input accounts

| Fields                              |        |
| ----------------------------------- | ------ |
| burner                              | string |
| burnAccounts                        | string |
| destinationDelegatedDataCredits     | string |
| from                                | string |
| freezeAuthority                     | string |
| recipientTokenAccount               | string |
| burnAccounts.systemProgram          | string |
| accountPayer                        | string |
| burnAccounts.owner                  | string |
| registrar                           | string |
| subDaoEpochInfo                     | string |
| burnAccounts.burner                 | string |
| associatedTokenProgram              | string |
| circuitBreakerProgram               | string |
| fromAccount                         | string |
| escrowAccount                       | string |
| mintAuthority                       | string |
| dataCredits                         | string |
| circuitBreaker                      | string |
| dcMint                              | string |
| delegatedDataCredits                | string |
| burnAccounts.dcMint                 | string |
| hntMint                             | string |
| dao                                 | string |
| burnAccounts.associatedTokenProgram | string |
| payer                               | string |
| recipient                           | string |
| burnAccounts.tokenProgram           | string |
| tokenProgram                        | string |
| destinationSubDao                   | string |
| dcBurnAuthority                     | string |
| systemProgram                       | string |
| authority                           | string |
| hntPriceOracle                      | string |
| subDao                              | string |
| lazySigner                          | string |
| to                                  | string |
| heliumSubDaosProgram                | string |
| destinationEscrowAccount            | string |

#### args

| Fields         | Data Type |
| -------------- | --------- |
| authority      | string    |
| config         | \<STRUCT> |
| hntAmount      | int       |
| dcAmount       | int       |
| amount         | int       |
| routerKey      | string    |
| newAuthority   | string    |
| hntPriceOracle | string    |

#### config

| Field             | Data Type |
| ----------------- | --------- |
| windowSizeSeconds | int       |
| thresholdType     | string    |
| threshold         | int       |

#### helium.entity\_manager

The table contains the parsed instructions data for [entity manager](https://www.helium.com/) on helium . Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                   | Column Type    | Description                                                                                              |
| --------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                   | date           | Event date                                                                                               |
| block\_time                                   | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                   | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                          | string         | Solana program address                                                                                   |
| inner\_instruction\_index                     | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](helium.md#input-accounts-1) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                            | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                             | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                        | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                        | string         | The first signature in the transaction                                                                   |
| [args](helium.md#args-1)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### **input accounts**

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>authority</td><td>string</td></tr><tr><td>dcMint</td><td>string</td></tr><tr><td>updateAuthority</td><td>string</td></tr><tr><td>info</td><td>string</td></tr><tr><td>instruction</td><td>string</td></tr><tr><td>makerApproval</td><td>string</td></tr><tr><td>dataCreditsProgram</td><td>string</td></tr><tr><td>bubblegumSigner</td><td>string</td></tr><tr><td>refund</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>newTreeAuthority</td><td>string</td></tr><tr><td>dcFeePayer</td><td>string</td></tr><tr><td>hotspotOwner</td><td>string</td></tr><tr><td>payer</td><td>string</td></tr><tr><td>oldTreeAuthority</td><td>string</td></tr><tr><td>noEmitProgram</td><td>string</td></tr><tr><td>treeAuthority</td><td>string</td></tr><tr><td>tokenMetadataProgram</td><td>string</td></tr><tr><td>logWrapper</td><td>string</td></tr><tr><td>collection</td><td>string</td></tr><tr><td>dcBurner</td><td>string</td></tr><tr><td>eccVerifier</td><td>string</td></tr><tr><td>bubblegumProgram</td><td>string</td></tr><tr><td>dntBurner</td><td>string</td></tr><tr><td>masterEdition</td><td>string</td></tr><tr><td>newMerkleTree</td><td>string</td></tr><tr><td>maker</td><td>string</td></tr><tr><td>issuingAuthority</td><td>string</td></tr><tr><td>signer</td><td>string</td></tr><tr><td>recipientAccount</td><td>string</td></tr><tr><td>tokenAccount</td><td>string</td></tr><tr><td>subDao</td><td>string</td></tr><tr><td>metadata</td><td>string</td></tr><tr><td>programApproval</td><td>string</td></tr><tr><td>programApprover</td><td>string</td></tr><tr><td>keyToAsset</td><td>string</td></tr><tr><td>heliumSubDaosProgram</td><td>string</td></tr><tr><td>dao</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>activeDeviceAuthority</td><td>string</td></tr><tr><td>escrow</td><td>string</td></tr><tr><td>iotInfo</td><td>string</td></tr><tr><td>associatedTokenProgram</td><td>string</td></tr><tr><td>mint</td><td>string</td></tr><tr><td>entityCreator</td><td>string</td></tr><tr><td>dataOnlyConfig</td><td>string</td></tr><tr><td>collectionAuthority</td><td>string</td></tr><tr><td>dc</td><td>string</td></tr><tr><td>recipient</td><td>string</td></tr><tr><td>lazySigner</td><td>string</td></tr><tr><td>collectionMetadata</td><td>string</td></tr><tr><td>mobileInfo</td><td>string</td></tr><tr><td>rewardableEntityConfig</td><td>string</td></tr><tr><td>dataOnlyEscrow</td><td>string</td></tr><tr><td>dntPrice</td><td>string</td></tr><tr><td>collectionMasterEdition</td><td>string</td></tr><tr><td>compressionProgram</td><td>string</td></tr><tr><td>rent</td><td>string</td></tr><tr><td>merkleTree</td><td>string</td></tr><tr><td>dntMint</td><td>string</td></tr></tbody></table>

#### args

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>symbol</td><td>&#x3C;STRUCT></td></tr><tr><td>programId</td><td>string</td></tr><tr><td>issuingAuthority</td><td>string</td></tr><tr><td>name</td><td>string</td></tr><tr><td>metadataUrl</td><td>string</td></tr><tr><td>entityKey</td><td>array&#x3C;int></td></tr><tr><td>keySerialization</td><td>string</td></tr><tr><td>approverSeeds</td><td>array&#x3C;int></td></tr><tr><td>location</td><td>int</td></tr><tr><td>elevation</td><td>int</td></tr><tr><td>gain</td><td>int</td></tr><tr><td>isFullHotspot</td><td>bool</td></tr><tr><td>numLocationAsserts</td><td>int</td></tr><tr><td>dataHash</td><td>array&#x3C;int></td></tr><tr><td>creatorHash</td><td>array&#x3C;int></td></tr><tr><td>root</td><td>array&#x3C;int></td></tr><tr><td>index</td><td>int</td></tr><tr><td>newAuthority</td><td>string</td></tr><tr><td>maxDepth</td><td>int</td></tr><tr><td>maxBufferSize</td><td>int</td></tr><tr><td>authority</td><td>string</td></tr><tr><td>newTreeDepth</td><td>int</td></tr><tr><td>newTreeBufferSize</td><td>int</td></tr><tr><td>newTreeSpace</td><td>int</td></tr><tr><td>newTreeFeeLamports</td><td>int</td></tr><tr><td>isActive</td><td>bool</td></tr></tbody></table>

#### symbol

| Field    | Data Type |
| -------- | --------- |
| settings | \<STRUCT> |

#### settings

| Field | Data Type |
| ----- | --------- |
| name  | \<STRUCT> |

#### name

| Field | Data Type |
| ----- | --------- |
| field | \<STRUCT> |



#### field

| Fields                           | Data Type |
| -------------------------------- | --------- |
| min\_gain                        | string    |
| max\_gain                        | \<STRUCT> |
| full\_location\_staking\_fee     | int       |
| dataonly\_location\_staking\_fee | int       |

#### helium.lazy\_transactions

The  table contains the parsed instructions data for [lazy transactions](https://www.helium.com/) on helium . Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                   | Column Type    | Description                                                                                              |
| --------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                   | date           | Event date                                                                                               |
| block\_time                                   | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                   | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                          | string         | Solana program address                                                                                   |
| inner\_instruction\_index                     | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](helium.md#input-accounts-1) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                            | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                             | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                        | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                        | string         | The first signature in the transaction                                                                   |
| [args](helium.md#args-1)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input accounts



| Fields           | Data Type |
| ---------------- | --------- |
| block            | string    |
| payer            | string    |
| lazyTransactions | string    |
| systemProgram    | string    |
| authority        | string    |
| refund           | string    |
| canopy           | string    |
| lazySigner       | string    |

#### args

| Fields       | Data Type   |
| ------------ | ----------- |
| root         | array\<int> |
| name         | string      |
| authority    | string      |
| maxDepth     | int         |
| instructions | \<struct>   |
| signerSeeds  | array\<int> |
| index        | int         |
| offset       | int         |
| bytes        | array\<int> |

#### instructions

| Fields         | Data Type   |
| -------------- | ----------- |
| programIdIndex | int         |
| accounts       | array\<int> |
| data           | array\<int> |

#### helium.sub\_daos

The table contains the parsed instructions data for [sub doas](https://www.helium.com/) on helium . Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                   | Column Type    | Description                                                                                              |
| --------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                   | date           | Event date                                                                                               |
| block\_time                                   | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                   | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                          | string         | Solana program address                                                                                   |
| inner\_instruction\_index                     | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](helium.md#input-accounts-1) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                            | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                             | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                        | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                        | string         | The first signature in the transaction                                                                   |
| [args](helium.md#args-1)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input accounts

<table><thead><tr><th width="321">Fields</th><th></th></tr></thead><tbody><tr><td>threadPayer</td><td>string</td></tr><tr><td>treasuryManagementProgram</td><td>string</td></tr><tr><td>hntFreezeAuthority</td><td>string</td></tr><tr><td>mint</td><td>string</td></tr><tr><td>delegatorPoolCircuitBreaker</td><td>string</td></tr><tr><td>circuitBreaker</td><td>string</td></tr><tr><td>circuitBreakerProgram</td><td>string</td></tr><tr><td>targetVault</td><td>string</td></tr><tr><td>dntMint</td><td>string</td></tr><tr><td>treasuryCircuitBreaker</td><td>string</td></tr><tr><td>rewardsEscrow</td><td>string</td></tr><tr><td>registrar</td><td>string</td></tr><tr><td>positionAuthority</td><td>string</td></tr><tr><td>treasuryManagement</td><td>string</td></tr><tr><td>vsrProgram</td><td>string</td></tr><tr><td>clockwork</td><td>string</td></tr><tr><td>dao</td><td>string</td></tr><tr><td>daoEpochInfo</td><td>string</td></tr><tr><td>hntMint</td><td>string</td></tr><tr><td>issueThread</td><td>string</td></tr><tr><td>delegatorPool</td><td>string</td></tr><tr><td>dcMint</td><td>string</td></tr><tr><td>subDaoEpochInfo</td><td>string</td></tr><tr><td>targetDelegatedPosition</td><td>string</td></tr><tr><td>sourceDelegatedPosition</td><td>string</td></tr><tr><td>depositMint</td><td>string</td></tr><tr><td>dntCircuitBreaker</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>targetPosition</td><td>string</td></tr><tr><td>calculateThread</td><td>string</td></tr><tr><td>sourceVault</td><td>string</td></tr><tr><td>positionTokenAccount</td><td>string</td></tr><tr><td>payer</td><td>string</td></tr><tr><td>delegatorAta</td><td>string</td></tr><tr><td>position</td><td>string</td></tr><tr><td>genesisEndSubDaoEpochInfo</td><td>string</td></tr><tr><td>dntMintAuthority</td><td>string</td></tr><tr><td>associatedTokenProgram</td><td>string</td></tr><tr><td>treasury</td><td>string</td></tr><tr><td>sourcePosition</td><td>string</td></tr><tr><td>subDaoFreezeAuthority</td><td>string</td></tr><tr><td>hntCircuitBreaker</td><td>string</td></tr><tr><td>historyBuffer</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>authority</td><td>string</td></tr><tr><td>prevDaoEpochInfo</td><td>string</td></tr><tr><td>closingTimeSubDaoEpochInfo</td><td>string</td></tr><tr><td>subDao</td><td>string</td></tr><tr><td>accountPayer</td><td>string</td></tr><tr><td>activeDeviceAggregator</td><td>string</td></tr><tr><td>delegatedPosition</td><td>string</td></tr><tr><td>hntMintAuthority</td><td>string</td></tr><tr><td>hstPool</td><td>string</td></tr><tr><td>thread</td><td>string</td></tr></tbody></table>

#### args

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>emissionSchedule</td><td>&#x3C;STRUCT></td></tr><tr><td>authority</td><td>string</td></tr><tr><td>hstEmissionSchedule</td><td>&#x3C;STRUCT></td></tr><tr><td>netEmissionsCap</td><td>int</td></tr><tr><td>registrar</td><td>int</td></tr><tr><td>treasuryCurve</td><td>&#x3C;STRUCT></td></tr><tr><td>onboardingDcFee</td><td>int</td></tr><tr><td>dcBurnAuthority</td><td>string</td></tr><tr><td>delegatorRewardsPercent</td><td>int</td></tr><tr><td>onboardingDataOnlyDcFee</td><td>int</td></tr><tr><td>hstPool</td><td>string</td></tr><tr><td>activeDeviceAggregator</td><td>string</td></tr><tr><td>vehntDelegated</td><td>double</td></tr><tr><td>vehntLastCalculatedTs</td><td>float</td></tr><tr><td>vehntFallRate</td><td>float</td></tr><tr><td>dcBurned</td><td>int</td></tr><tr><td>bump</td><td>int</td></tr><tr><td>newAuthority</td><td>string</td></tr><tr><td>epoch</td><td>int</td></tr><tr><td>amount</td><td>int</td></tr><tr><td>kind</td><td>string</td></tr><tr><td>periods</td><td>int</td></tr></tbody></table>

#### emissionSchedule

| Fields            | Data Type |
| ----------------- | --------- |
| startUnixTime     | int       |
| emissionsPerEpoch | int       |

#### hstEmissionSchedule

| Fields        | Data Type |
| ------------- | --------- |
| startUnixTime | int       |
| percent       | int       |

#### treasuryCurve

| Fields | Data Type |
| ------ | --------- |
| name   | int       |
| fields | \<struct> |

#### fields

| Fields | Data Type |
| ------ | --------- |
| k      | float     |

#### helium.treasury\_management

The table contains the parsed instructions data for [treasury management](https://www.helium.com/) on helium . Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                   | Column Type    | Description                                                                                              |
| --------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                   | date           | Event date                                                                                               |
| block\_time                                   | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                   | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                          | string         | Solana program address                                                                                   |
| inner\_instruction\_index                     | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](helium.md#input-accounts-1) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                            | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                             | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                        | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                        | string         | The first signature in the transaction                                                                   |
| [args](helium.md#args-1)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input accounts

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>owner</td><td>string</td></tr><tr><td>circuitBreaker</td><td>string</td></tr><tr><td>treasuryManagement</td><td>string</td></tr><tr><td>associatedTokenProgram</td><td>string</td></tr><tr><td>payer</td><td>string</td></tr><tr><td>circuitBreakerProgram</td><td>string</td></tr><tr><td>authority</td><td>string</td></tr><tr><td>from</td><td>string</td></tr><tr><td>treasuryMint</td><td>string</td></tr><tr><td>supplyMint</td><td>string</td></tr><tr><td>treasury</td><td>string</td></tr><tr><td>mintAuthority</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>destTreasury</td><td>string</td></tr><tr><td>to</td><td>string</td></tr><tr><td>admin</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr></tbody></table>

#### args

| Fields               | Data Type |
| -------------------- | --------- |
| authority            | string    |
| curve                | \<struct> |
| freezeUnixTime       | int       |
| windowConfig         | \<struct> |
| amount               | int       |
| expectedOutputAmount | int       |

#### curve

| Fields | Data Type |
| ------ | --------- |
| name   | int       |
| fields | \<struct> |

#### fields

| Fields | Data Type |
| ------ | --------- |
| k      | float     |

#### windowConfig

| Fields            | Data Type |
| ----------------- | --------- |
| windowSizeSeconds | int       |
| thresholdType     | string    |
| threshold         | int       |

#### helium.voter\_stake\_registry

The table contains the parsed instructions data for [voter staking](https://www.helium.com/) on helium . Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                   | Column Type    | Description                                                                                              |
| --------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                   | date           | Event date                                                                                               |
| block\_time                                   | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                   | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                          | string         | Solana program address                                                                                   |
| inner\_instruction\_index                     | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](helium.md#input-accounts-1) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                            | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                             | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                        | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                        | string         | The first signature in the transaction                                                                   |
| agrs\_fields                                  | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input accounts

| Fields                  | Data Type |
| ----------------------- | --------- |
| tokenMetadataProgram    | string    |
| beneficiary             | string    |
| maxVoterWeightRecord    | string    |
| associatedTokenProgram  | string    |
| mint                    | string    |
| recipient               | string    |
| solDestination          | string    |
| metadata                | string    |
| realm                   | string    |
| tokenProgram            | string    |
| positionUpdateAuthority | string    |
| positionTokenAccount    | string    |
| sourcePosition          | string    |
| voterAuthority          | string    |
| sourceVault             | string    |
| voteRecord              | string    |
| voteRecord              | string    |
| vault                   | string    |
| tokenAccount            | string    |
| payer                   | string    |
| registrar               | string    |
| targetVault             | string    |
| governance              | string    |
| approver                | string    |
| proposal                | string    |
| depositMint             | string    |
| collection              | string    |
| fromTokenAccount        | string    |
| to                      | string    |
| masterEdition           | string    |
| positionAuthority       | string    |
| voterWeightRecord       | string    |
| destination             | string    |
| voterTokenOwnerRecord   | string    |
| realmGoverningTokenMint | string    |
| realmAuthority          | string    |
| position                | string    |
| depositToken            | string    |
| governanceProgramId     | string    |
| depositAuthority        | string    |
| toTokenAccount          | string    |
| collectionMetadata      | string    |
| from                    | string    |
| collectionMasterEdition | string    |
| targetPosition          | string    |
| rent                    | string    |

#### agrs\_fields

| Field      |           |
| ---------- | --------- |
| args       | \<struct> |
| timeOffset | int       |

#### args

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>positionUpdateAuthority</td><td>string</td></tr><tr><td>idx</td><td>string</td></tr><tr><td>digitShift</td><td>string</td></tr><tr><td>baselineVoteWeightScaledFactor</td><td>string</td></tr><tr><td>maxExtraLockupVoteWeightScaledFactor</td><td>string</td></tr><tr><td>genesisVotePowerMultiplier</td><td>string</td></tr><tr><td>genesisVotePowerMultiplierExpirationTs</td><td>string</td></tr><tr><td>lockupSaturationSecs</td><td>string</td></tr><tr><td>kind</td><td>string</td></tr><tr><td>periods</td><td>string</td></tr><tr><td>amount</td><td>string</td></tr><tr><td>owner</td><td>string</td></tr><tr><td>voterWeightAction</td><td>string</td></tr><tr><td>proposal</td><td>string</td></tr></tbody></table>

#### helium.lazy\_distributor

The table contains the parsed instructions data for [lazy distributor ](https://www.helium.com/)on helium . Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                   | Column Type    | Description                                                                                              |
| --------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                   | date           | Event date                                                                                               |
| block\_time                                   | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                   | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                          | string         | Solana program address                                                                                   |
| inner\_instruction\_index                     | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](helium.md#input-accounts-1) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                            | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                             | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                        | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                        | string         | The first signature in the transaction                                                                   |
| agrs\_fields                                  | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input accounts

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>mint</td><td>string</td></tr><tr><td>recipientMintAccount</td><td>string</td></tr><tr><td>common.rewardsMint</td><td>string</td></tr><tr><td>oracle</td><td>string</td></tr><tr><td>recipient</td><td>string</td></tr><tr><td>merkleTree</td><td>string</td></tr><tr><td>common.rewardsEscrow</td><td>string</td></tr><tr><td>common.associatedTokenProgram</td><td>string</td></tr><tr><td>common.tokenProgram</td><td>string</td></tr><tr><td>circuitBreaker</td><td>string</td></tr><tr><td>payer</td><td>string</td></tr><tr><td>common.circuitBreaker</td><td>string</td></tr><tr><td>common.owner</td><td>string</td></tr><tr><td>common.destinationAccount</td><td>string</td></tr><tr><td>owner</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>common.circuitBreakerProgram</td><td>string</td></tr><tr><td>circuitBreakerProgram</td><td>string</td></tr><tr><td>rewardsMint</td><td>string</td></tr><tr><td>common.lazyDistributor</td><td>string</td></tr><tr><td>targetMetadata</td><td>string</td></tr><tr><td>lazyDistributor</td><td>string</td></tr><tr><td>associatedTokenProgram</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>common.systemProgram</td><td>string</td></tr><tr><td>compressionProgram</td><td>string</td></tr><tr><td>common.payer</td><td>string</td></tr><tr><td>rewardsEscrow</td><td>string</td></tr><tr><td>common.recipient</td><td>string</td></tr></tbody></table>

#### args

| Fields         | Data Type   |
| -------------- | ----------- |
| authority      | string      |
| oracles        | \<struct>   |
| approver       | string      |
| windowConfig   | \<struct>   |
| dataHash       | array\<int> |
| root           | array\<int> |
| index          | int         |
| oracleIndex    | int         |
| currentRewards | int         |
|                |             |

#### oracles

| Field  | Data Type |
| ------ | --------- |
| oracle | string    |
| url    | string    |



#### windowConfig

| Fields            | Data Type |
| ----------------- | --------- |
| windowSizeSeconds | int       |
| thresholdType     | string    |
| threshold         | int       |









































