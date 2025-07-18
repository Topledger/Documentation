---
description: >-
  Lending and borrowing for NFTs on Solana. Your bags + frakt = instant
  liquidity.
---

# Frakt

**frakt.txns**

This table has similar schema as of Solana [transactions](../solana-data/transactions.md) table

#### frakt.bonds

The bonds table contains the parsed instructions data for [frakt-bonds](https://docs.frakt.xyz/frakt/) . Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                | Column Type    | Description                                                                                              |
| ------------------------------------------ | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                | date           | Event date                                                                                               |
| block\_time                                | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                       | string         | Solana program address                                                                                   |
| inner\_instruction\_index                  | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](frakt.md#input-accounts) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                         | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                          | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                     | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                     | string         | The first signature in the transaction                                                                   |
| [args](frakt.md#args)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### **input accounts**

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>adapterProgramSigner</td><td>string</td></tr><tr><td>admin</td><td>string</td></tr><tr><td>assetReceiver</td><td>string</td></tr><tr><td>assetReceiverTokenAccount</td><td>string</td></tr><tr><td>associatedTokenProgram</td><td>string</td></tr><tr><td>authorityAdapter</td><td>string</td></tr><tr><td>authorityAdapter</td><td>string</td></tr><tr><td>bondCollateralOrSolReceiverTokenAccount</td><td>string</td></tr><tr><td>bondProgramAuthority</td><td>string</td></tr><tr><td>collateralBox</td><td>string</td></tr><tr><td>collateralTokenAccount</td><td>string</td></tr><tr><td>collateralTokenMint</td><td>string</td></tr><tr><td>crossMintAmmPairFundsSolVault</td><td>string</td></tr><tr><td>editionInfo</td><td>string</td></tr><tr><td>fbond</td><td>string</td></tr><tr><td>fbondTokenMint</td><td>string</td></tr><tr><td>feeSolVault</td><td>string</td></tr><tr><td>feeTokenAccount</td><td>string</td></tr><tr><td>fraktMarket</td><td>string</td></tr><tr><td>fundsSolVault</td><td>string</td></tr><tr><td>fundsTokenAccount</td><td>string</td></tr><tr><td>hadeswapNftPairBox</td><td>string</td></tr><tr><td>hadeswapPair</td><td>string</td></tr><tr><td>hadeswapPairAssetReceiver</td><td>string</td></tr><tr><td>hadeswapPairFeeSolVault</td><td>string</td></tr><tr><td>hadeswapPairFundsSolVault</td><td>string</td></tr><tr><td>hadeswapPairNftsOwner</td><td>string</td></tr><tr><td>hadeswapPairVaultNftTokenAccount</td><td>string</td></tr><tr><td>hadeswapProgram</td><td>string</td></tr><tr><td>hadeswapProtocolFeeReceiver</td><td>string</td></tr><tr><td>hadoMarket</td><td>string</td></tr><tr><td>hadoRegistry</td><td>string</td></tr><tr><td>instructions</td><td>string</td></tr><tr><td>metadataInfo</td><td>string</td></tr><tr><td>metadataProgram</td><td>string</td></tr><tr><td>newVaultTokenAccount</td><td>string</td></tr><tr><td>nftMint</td><td>string</td></tr><tr><td>nftMintFirst</td><td>string</td></tr><tr><td>nftMintSecond</td><td>string</td></tr><tr><td>nftPairBox</td><td>string</td></tr><tr><td>nftPairBoxFirst</td><td>string</td></tr><tr><td>nftPairBoxSecond</td><td>string</td></tr><tr><td>nftUserTokenAccount</td><td>string</td></tr><tr><td>nftUserTokenAccountFirst</td><td>string</td></tr><tr><td>nftUserTokenAccountSecond</td><td>string</td></tr><tr><td>nftValidationAdapter</td><td>string</td></tr><tr><td>nftsOwner</td><td>string</td></tr><tr><td>oracleFloor</td><td>string</td></tr><tr><td>pair</td><td>string</td></tr><tr><td>pairAuthorityAdapterProgram</td><td>string</td></tr><tr><td>pairTokenMint</td><td>string</td></tr><tr><td>partialAdapterProgram</td><td>string</td></tr><tr><td>partialAssetReceiver</td><td>string</td></tr><tr><td>pool</td><td>string</td></tr><tr><td>poolFundsSolVault</td><td>string</td></tr><tr><td>protocolFeeReceiver</td><td>string</td></tr><tr><td>rent</td><td>string</td></tr><tr><td>returnFundsOwner</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>tokenMint</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>user</td><td>string</td></tr><tr><td>userFbondTokenAccount</td><td>string</td></tr><tr><td>userTokenAccount</td><td>string</td></tr><tr><td>validation</td><td>string</td></tr><tr><td>validationAdapterProgram</td><td>string</td></tr><tr><td>validationWhitelist</td><td>string</td></tr><tr><td>vaultNftTokenAccount</td><td>string</td></tr><tr><td>vaultNftTokenAccountFirst</td><td>string</td></tr><tr><td>vaultNftTokenAccountSecond</td><td>string</td></tr><tr><td>vaultTokenAccount</td><td>string</td></tr><tr><td>whitelistEntry</td><td>string</td></tr><tr><td>whitelistedAddress</td><td>string</td></tr></tbody></table>

#### args

| Field                                 | Data Type |
| ------------------------------------- | --------- |
| [bumps](frakt.md#bumps)               | \<STRUCT> |
| amountToDeposit                       | int       |
| [params](frakt.md#params)             | \<STRUCT> |
| newAmountToReturn                     | int       |
| loanToValueFilter                     | int       |
| durationFilter                        | int       |
| maxReturnAmountFilter                 | int       |
| bondFeatures                          | string    |
| bondingCurveType                      | string    |
| pairType                              | string    |
| amountOfTokensToBuy                   | int       |
| [marketParams](frakt.md#marketparams) | \<STRUCT> |
| whitelistType                         | string    |
| maxAmountToPay                        | string    |
| skipFailed                            | bool      |
| amountToBuy                           | int       |
| minAmountToGet                        | int       |
| amountToSell                          | int       |
| amountOfTokensToWithdraw              | int       |
| amountToWithdraw                      | int       |
| duration                              | int       |
| nftValidationWhitelistType            | string    |
| scopeType                             | string    |
| proof                                 | int       |
| loanFeePoints                         | int       |
| solAmountToDeposit                    | int       |
| solAmountToWithdraw                   | int       |
| solAmountToBorrow                     | int       |
| solAmountToRepay                      | int       |

#### bumps

| Field                    | Data Type |
| ------------------------ | --------- |
| bondProgramAuthoritySeed | int       |
| returnFundsOwnerSeed     | int       |
| fundsSolVaultSeed        | int       |
| feeVaultSeed             | int       |
| nftsSeed                 | int       |

#### params

| Field          | Data Type |
| -------------- | --------- |
| amountToReturn | int       |
| bondDuration   | int       |
| delta          | string    |
| spotPrice      | int       |
| fee            | int       |

#### marketParams

| Field          | Data Type |
| -------------- | --------- |
| minBidCap      | int       |
| marketDecimals | int       |

#### frakt.lending

The bonds table contains the parsed instructions data for [frakt-lending](https://docs.frakt.xyz/frakt/) . Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                  | Column Type    | Description                                                                                              |
| -------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                  | date           | Event date                                                                                               |
| block\_time                                  | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                  | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                         | string         | Solana program address                                                                                   |
| inner\_instruction\_index                    | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](frakt.md#input-accounts-1) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                           | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                            | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                       | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                       | string         | The first signature in the transaction                                                                   |
| [args](frakt.md#args-1)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input accounts

| Fields                     |        |
| -------------------------- | ------ |
| admin                      | string |
| associatedTokenProgram     | string |
| attemptsNftMint            | string |
| authority                  | string |
| bank                       | string |
| collectionInfo             | string |
| communityPoolsAuthority    | string |
| creatorAddress             | string |
| deposit                    | string |
| editionInfo                | string |
| farm                       | string |
| farmAuthority              | string |
| farmTreasury               | string |
| farmer                     | string |
| feeAcc                     | string |
| fraktNftStakeAccount       | string |
| gemBank                    | string |
| gemBox                     | string |
| gemDepositReceipt          | string |
| gemFarm                    | string |
| gemMint                    | string |
| gemRarity                  | string |
| gemSource                  | string |
| identity                   | string |
| lendingStake               | string |
| liqOwner                   | string |
| liquidationLot             | string |
| liquidator                 | string |
| liquidityPool              | string |
| loan                       | string |
| lotTicket                  | string |
| metadataProgram            | string |
| nftAdminTokenAccount       | string |
| nftAttempts                | string |
| nftMint                    | string |
| nftUserTokenAccount        | string |
| pricingLookupAddress       | string |
| rent                       | string |
| rewardADestination         | string |
| rewardADestinationIdentity | string |
| rewardAMint                | string |
| rewardAPot                 | string |
| rewardBDestination         | string |
| rewardBDestinationIdentity | string |
| rewardBMint                | string |
| rewardBPot                 | string |
| royaltyAddress             | string |
| systemProgram              | string |
| tokenProgram               | string |
| user                       | string |
| vault                      | string |
| vaultNftTokenAccount       | string |

#### args

| Fields                      | Data Type |
| --------------------------- | --------- |
| bumpPoolsAuth               | int       |
| isPriceBased                | bool      |
| originalPriceFromUser       | double    |
| loanToValue                 | int       |
| nftPrice                    | int       |
| discount                    | int       |
| amount                      | int       |
| [params](frakt.md#params-1) | \<STRUCT> |
| depositBump                 | int       |
| gracePeriod                 | int       |
| isWinning                   | bool      |
| nftAttemptsBump             | int       |
| bumpAuth                    | int       |

#### params

| Fields                  | Data Type |
| ----------------------- | --------- |
| loanToValue             | int       |
| collaterizationRate     | int       |
| royaltyFeeTime          | int       |
| royaltyFeePrice         | int       |
| expirationTime          | int       |
| isPriceBased            | bool      |
| id                      | int       |
| baseBorrowRate          | int       |
| variableSlope1          | int       |
| variableSlope2          | int       |
| utilizationRateOptimal  | int       |
| reserveFactor           | int       |
| borrowCommission        | int       |
| depositCommission       | int       |
| rewardInterestRateTime  | int       |
| rewardInterestRateTime  | int       |
| rewardInterestRatePrice | int       |
| feeInterestRatePrice    | int       |
| period                  | int       |
| bumpPoolsAuth           | int       |
| bumpAuth                | int       |
| bumpAuthVaultAuthority  | int       |
| bumpRarity              | int       |
| bumpFarmer              | int       |
| bumpGdr                 | int       |
| bumpGemBox              | int       |
| bumpVault               | int       |
| isDegod                 | bool      |
| bumpAuthAuthority       | int       |
| bumpTreasury            | int       |
| bumpPotA                | int       |
| bumpPotB                | int       |

#### frakt.raffle

The bonds table contains the parsed instructions data for [frakt-raffle](https://docs.frakt.xyz/frakt/) . Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                  | Column Type    | Description                                                                                              |
| -------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                  | date           | Event date                                                                                               |
| block\_time                                  | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                  | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                         | string         | Solana program address                                                                                   |
| inner\_instruction\_index                    | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](frakt.md#input-accounts-2) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                           | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                            | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                       | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                       | string         | The first signature in the transaction                                                                   |
| [args](frakt.md#args-2)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

#### input accounts

| Fields                    | Data Type |
| ------------------------- | --------- |
| admin                     | string    |
| adminNftTokenAccount      | string    |
| associatedTokenProgram    | string    |
| auction                   | string    |
| authorizationRulesProgram | string    |
| bondsProgramId            | string    |
| destTokenRecord           | string    |
| editionInfo               | string    |
| fbond                     | string    |
| instructions              | string    |
| liquidatingPda            | string    |
| metadataProgram           | string    |
| nftMetadata               | string    |
| nftMint                   | string    |
| nftOwner                  | string    |
| nftOwnerTokenAccount      | string    |
| ownerTokenRecord          | string    |
| participation             | string    |
| raffle                    | string    |
| receiver                  | string    |
| rent                      | string    |
| returnFundsOwner          | string    |
| solHandler                | string    |
| systemProgram             | string    |
| tokenProgram              | string    |
| user                      | string    |
| userNftTokenAccount       | string    |

#### args

| Fields                                          | Data Type |
| ----------------------------------------------- | --------- |
| raffleTime                                      | int       |
| depositAmount                                   | double    |
| [authorizationData](frakt.md#authorizationdata) | \<STRUCT> |
| tickets                                         | int       |
| startPrice                                      | int       |
| delta                                           | int       |
| deltaType                                       | string    |
| denominator                                     | int       |



#### **authorizationData**

| Fields                      | Data Type |
| --------------------------- | --------- |
| [payload](frakt.md#payload) | \<STRUCT> |

#### payload

| Fields  | Data Type |
| ------- | --------- |
| name    | string    |
| payload | string    |

#### frakt.registry

The bonds table contains the parsed instructions data for [frakt-registry](https://docs.frakt.xyz/frakt/) . Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                  | Column Type    | Description                                                                                              |
| -------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                  | date           | Event date                                                                                               |
| block\_time                                  | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                  | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                         | string         | Solana program address                                                                                   |
| inner\_instruction\_index                    | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](frakt.md#input-accounts-3) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                           | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                            | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                       | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                       | string         | The first signature in the transaction                                                                   |
| [args](frakt.md#args-3)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input accounts

| Fields             | Data Type |
| ------------------ | --------- |
| admin              | string    |
| fraktMarket        | string    |
| oracle             | string    |
| rent               | string    |
|  systemProgram     | string    |
| user               | string    |
| whitelistEntry     | string    |
| whitelistedAddress | string    |

#### args

| Fields             | Data Type   |
| ------------------ | ----------- |
| whitelistType      | string      |
| root               | array\<int> |
| oracleAuthority    | string      |
| oracleInfo         | string      |
| floor              | bigint      |
| newOracleAuthority | string      |
| newFloor           | bigint      |

#### fract.system.txns

The bonds table contains the parsed instructions data for [frakt-system-txns](https://docs.frakt.xyz/frakt/) . Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                  | Column Type    | Description                                                                                              |
| -------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                  | date           | Event date                                                                                               |
| block\_time                                  | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                  | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                         | string         | Solana program address                                                                                   |
| inner\_instruction\_index                    | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](frakt.md#input-accounts-4) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                           | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                            | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                       | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                       | string         | The first signature in the transaction                                                                   |
| [args](frakt.md#args-4)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input accounts

| Fields                    | Data Type |
| ------------------------- | --------- |
| allocated\_account        | string    |
| assigned\_account         | string    |
| base\_account             | string    |
| created\_account          | string    |
| funding\_account          | string    |
| new\_account              | string    |
| nonce\_account            | string    |
| nonce\_authority          | string    |
| recent\_blockhash\_sysvar | string    |
| recipient\_account        | string    |
| rent\_sysvar              | string    |

#### args

|             |        |
| ----------- | ------ |
| lamports    | int    |
| space       | int    |
| owner       | string |
| base        | string |
| seed        | string |
| authority   | string |
| from\_seed  | string |
| from\_owner | string |
