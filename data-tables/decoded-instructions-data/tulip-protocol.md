---
description: >-
  Tulip Protocol is the first yield aggregation platform built on Solana with
  auto-compounding vault strategies.
---

# Tulip Protocol

#### tuli&#x70;**.txns**

This table has similar schema as of Solana [transactions](../solana-data/transactions.md) table

#### tuli&#x70;**.vault**

The table contains the parsed instructions data for [Tulip V2 Vault](https://tulip-protocol.gitbook.io/tulip-protocol/tulip-autovaults/v2-vaults). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                         | Column Type    | Description                                                                                              |
| --------------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                         | date           | Event date                                                                                               |
| block\_time                                         | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                         | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                                | string         | Solana program address                                                                                   |
| inner\_instruction\_index                           | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](tulip-protocol.md#input-accounts) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                                  | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                                   | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                              | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                              | string         | The first signature in the transaction                                                                   |
| args                                                | string         | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### **input accounts**

<table><thead><tr><th width="374.3333333333333">Field</th><th>Data Type</th></tr></thead><tbody><tr><td>authority</td><td>string</td></tr><tr><td>management</td><td>string</td></tr><tr><td>vault</td><td>string</td></tr><tr><td>vaultPda</td><td>string</td></tr><tr><td>vaultStakerAccount</td><td>string</td></tr><tr><td>farmAccount</td><td>string</td></tr><tr><td>farmStakeTokenAccount</td><td>string</td></tr><tr><td>cropAccount</td><td>string</td></tr><tr><td>cropRewardTokenAccount</td><td>string</td></tr><tr><td>vaultHarvesterAccount</td><td>string</td></tr><tr><td>vaultRewardTokenAccount</td><td>string</td></tr><tr><td>underlyingCompoundQueue</td><td>string</td></tr><tr><td>feeCollectorTokenAccount</td><td>string</td></tr><tr><td>sharesMint</td><td>string</td></tr><tr><td>atrixFarmProgram</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>clock</td><td>string</td></tr></tbody></table>



#### tuli&#x70;**.farming**

The table contains the parsed instructions data for [Tulip Farming](https://tulip-protocol.gitbook.io/tulip-protocol/leveraged-yield-farming/opening-a-position). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Field                                                 | Column Type    | Description                                                                                             |
| ----------------------------------------------------- | -------------- | ------------------------------------------------------------------------------------------------------- |
| block\_date                                           | date           | Event date                                                                                              |
| block\_time                                           | timestamp      | The (estimated) time this block was produced                                                            |
| block\_slot                                           | bigint         | This block’s slot index in the ledger                                                                   |
| dapp                                                  | string         | Solana program address                                                                                  |
| inner\_instruction\_index                             | int            | The order of inner instruction of an instruction in a txns                                              |
| [input\_accounts](tulip-protocol.md#input-accounts-1) | array\<string> | Ordered list of accounts to pass to the program                                                         |
| instruction\_index                                    | int            | The order of the instruction in a txns                                                                  |
| instruction\_type                                     | string         | Name of the function of a Solana program invoked via an instruction                                     |
| is\_inner\_instruction                                | boolean        | Whether the respective instruction of a txns has an inner instruction                                   |
| tx\_id                                                | string         | The first signature in the transaction                                                                  |
| [args](tulip-protocol.md#args)                        | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter  |

#### input accounts

| Field                                  | Data Type |
| -------------------------------------- | --------- |
| ammAuthority                           | string    |
| ammId                                  | string    |
| ammOpenOrders                          | string    |
| ammQuantitiesOrTargetOrders            | string    |
| aquaFarmProgram                        | string    |
| authority                              | string    |
| authorityTokenAccount                  | string    |
| authorityTulipTokenAccount             | string    |
| baseTokenAccount                       | string    |
| borrowAuthorizer                       | string    |
| clock                                  | string    |
| coinDepositReserveAccount              | string    |
| coinDestinationTokenAccount            | string    |
| coinReserveLiquidityFeeReceiver        | string    |
| coinReserveLiquidityOracle             | string    |
| coinSourceReserveLiquidityTokenAccount | string    |
| coinSourceTokenAccount                 | string    |
| coinWallet                             | string    |
| convertAuthority                       | string    |
| convertAuthorityDd                     | string    |
| derivedLendingMarketAuthority          | string    |
| dexProgram                             | string    |
| farmDdTokenMint                        | string    |
| farmTokenMint                          | string    |
| fundingTokenAccount                    | string    |
| global                                 | string    |
| globalBaseDdTokenVault                 | string    |
| globalBaseTokenVault                   | string    |
| globalFarm                             | string    |
| globalFarmDd                           | string    |
| globalRewardDdTokenVault               | string    |
| globalRewardTokenVault                 | string    |
| lendingMarket                          | string    |
| lendingMarketAccount                   | string    |
| lendingProgram                         | string    |
| levFarmCoinTokenAccount                | string    |
| levFarmPcTokenAccount                  | string    |
| leveragedFarm                          | string    |
| leveragedUserFarm                      | string    |
| liquidatorBaseAccount                  | string    |
| liquidatorLpAccount                    | string    |
| liquidatorQuoteAccount                 | string    |
| liquidityProgramId                     | string    |
| lpMintAddress                          | string    |
| lpPythPriceAccount                     | string    |
| lpTokenAccount                         | string    |
| market                                 | string    |
| obligationLiquidity                    | string    |
| obligationVaultAddress                 | string    |
| orcaUserFarm                           | string    |
| pcDepositReserveAccount                | string    |
| pcDestinationTokenAccount              | string    |
| pcReserveLiquidityFeeReceiver          | string    |
| pcReserveLiquidityOracle               | string    |
| pcSourceReserveLiquidityTokenAccount   | string    |
| pcSourceTokenAccount                   | string    |
| pcWallet                               | string    |
| poolAuthority                          | string    |
| poolCoinTokenAccount                   | string    |
| poolId                                 | string    |
| poolLpTokenAccount                     | string    |
| poolPcTokenAccount                     | string    |
| poolRewardATokenAccount                | string    |
| poolRewardBTokenAccount                | string    |
| pythPriceAccount                       | string    |
| quoteTokenAccount                      | string    |
| raySwap                                | string    |
| receivingTokenAccount                  | string    |
| removeLiquidity                        | string    |
| rent                                   | string    |
| reserveLiquidityFeeReceiver            | string    |
| serumAsks                              | string    |
| serumBids                              | string    |
| serumCoinVaultAccount                  | string    |
| serumEventQueue                        | string    |
| serumMarket                            | string    |
| serumPcVaultAccount                    | string    |
| serumProgramId                         | string    |
| serumVaultSigner                       | string    |
| solfarmVaultProgram                    | string    |
| sourceReserveLiquidityTokenAccount     | string    |
| stakeProgramId                         | string    |
| swapOrLiquidityProgramId               | string    |
| systemProgram                          | string    |
| tokenProgram                           | string    |
| tokenProgramId                         | string    |
| userBalanceAccount                     | string    |
| userBalanceMetadata                    | string    |
| userBaseTokenAccount                   | string    |
| userFarm                               | string    |
| userFarmDd                             | string    |
| userFarmDdTokenAccount                 | string    |
| userFarmObligation                     | string    |
| userFarmOwner                          | string    |
| userFarmTokenAccount                   | string    |
| userInfoAccount                        | string    |
| userLpTokenAccount                     | string    |
| userObligationLiquidation              | string    |
| userRewardATokenAccount                | string    |
| userRewardBTokenAccount                | string    |
| userRewardDdTokenAccount               | string    |
| userRewardTokenAccount                 | string    |
| userTransferAuthority                  | string    |
| userTulipRewardMetadata                | string    |
| userTulipTokenAccount                  | string    |
| vault                                  | string    |
| vaultAccount                           | string    |
| vaultPda                               | string    |
| vaultPdaAccount                        | string    |
| vaultProgram                           | string    |
| vaultSigner                            | string    |
| vaultTulipTokenAccount                 | string    |
| vaultUserAccount                       | string    |
| withdrawFarm                           | string    |

#### args

| Field                                        | Data Type      |
| -------------------------------------------- | -------------- |
| borrowAmount                                 | double         |
| borrowToken                                  | double         |
| coinAmount                                   | double         |
| coinBorrowAmount                             | double         |
| [depositArgs](tulip-protocol.md#depositargs) | STRUCT         |
| farmProgramId                                | string         |
| [harvestArgs](tulip-protocol.md#harvestargs) | STRUCT         |
| metaNonce                                    | int            |
| nonce                                        | int            |
| obligationIndex                              | int            |
| order                                        | int            |
| pcAmount                                     | double         |
| pcBorrowAmount                               | double         |
| queueAuthority                               | string         |
| reserves                                     | array\<string> |

#### depositArgs

| Field        | Data Type |
| ------------ | --------- |
| accountNonce | int       |
| metaNonce    | int       |
| nonce        | int       |

#### harvestArgs

| Field       | Data Type |
| ----------- | --------- |
| metaNonce   | int       |
| nonce       | int       |
| rewardNonce | int       |

#### tuli&#x70;**.lending**

The table contains the parsed instructions data for [Tulip Lending](https://tulip-protocol.gitbook.io/tulip-protocol/lending/lending-reserves). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                           | Column Type    | Description                                                                                              |
| ----------------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                           | date           | Event date                                                                                               |
| block\_time                                           | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                           | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                                  | string         | Solana program address                                                                                   |
| inner\_instruction\_index                             | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](tulip-protocol.md#input-accounts-2) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                                    | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                                     | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                                | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                                | string         | The first signature in the transaction                                                                   |
| [args](tulip-protocol.md#args-1)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input accounts

| Field                                  | Data Type |
| -------------------------------------- | --------- |
| authority                              | string    |
| derivedLendingMarketAuthority          | string    |
| destinationCollateralTokenAccount      | string    |
| destinationLiquidityTokenAccount       | string    |
| lendingMarketAccount                   | string    |
| reserveAccount                         | string    |
| reserveCollateralSPLTokenMint          | string    |
| reserveLiquidityOracleAccount          | string    |
| reserveLiquiditySupplySPLTokenAccount  | string    |
| reserveLiquiditySupplySPLTokenAccount. | string    |
| sourceCollateralTokenAccount           | string    |
| sourceLiquidityTokenAccount            | string    |
| sysvar                                 | string    |
| tokenProgramId                         | string    |

#### args

| Field              | Data Type |
| ------------------ | --------- |
| collateral\_amount | double    |
| liquidity\_amount  | double    |

#### tuli&#x70;**.staking**

The table contains the parsed instructions data for [Tulip Staking.](https://tulip-protocol.gitbook.io/tulip-protocol/tulip-dao/staking) Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                           | Column Type    | Description                                                                                              |
| ----------------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                           | date           | Event date                                                                                               |
| block\_time                                           | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                           | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                                  | string         | Solana program address                                                                                   |
| inner\_instruction\_index                             | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](tulip-protocol.md#input-accounts-3) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                                    | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                                     | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                                | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                                | string         | The first signature in the transaction                                                                   |
| [args](tulip-protocol.md#args-2)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input accounts

| Field                 | Data Type |
| --------------------- | --------- |
| rent                  | string    |
| sTokenFrom            | string    |
| sTokenFromAuthority   | string    |
| sTokenMint            | string    |
| sTokenTo              | string    |
| stakingAccount        | string    |
| systemProgram         | string    |
| tokenFrom             | string    |
| tokenFromAuthority    | string    |
| tokenLockVault        | string    |
| tokenMint             | string    |
| tokenProgram          | string    |
| tokenTo               | string    |
| tokenToAuthority      | string    |
| tokenVault            | string    |
| userStakingAccount    | string    |
| userTulipTokenAccount | string    |

#### args

| Field            | Data Type |
| ---------------- | --------- |
| amount           | double    |
| index            | int       |
| nonceLockVault   | int       |
| nonceStaking     | int       |
| nonceUserStaking | int       |
| nonceVault       | int       |

#### tuli&#x70;**.info**

The table contains the info data for [Tulip Lending](https://github.com/sol-farm/solfarm-sdk/blob/84f4c49d427ec71b597488f76ec1eac305c2b17a/src/constants/lending_info.json). Data related to loan\_to\_value\_ratio, liquidation\_threshold, liquidity\_supply\_token\_mint, collateral\_token\_mint, etc. is available here.



| Column Name                             | Data Type |
| --------------------------------------- | --------- |
| name                                    | string    |
| account                                 | string    |
| liquidity\_supply\_token\_mint          | string    |
| liquidity\_supply\_token\_account       | string    |
| liquidity\_fee\_receiver                | string    |
| collateral\_token\_mint                 | string    |
| collateral\_token\_supply               | string    |
| destination\_collateral\_token\_account | string    |
| quote\_token\_mint                      | string    |
| platform\_fees                          | bigint    |
| [config](tulip-protocol.md#config)      | STRUCT    |

#### config

| Field                          | Data Type |
| ------------------------------ | --------- |
| degen\_borrow\_rate            | bigint    |
| degen\_utilization\_rate       | bigint    |
| [fees](tulip-protocol.md#fees) | STRUCT    |
| liquidation\_bonus             | bigint    |
| liquidation\_threshold         | bigint    |
| loan\_to\_value\_ratio         | bigint    |
| max\_borrow\_rate              | bigint    |
| min\_borrow\_rate              | bigint    |
| optimal\_borrow\_rate          | bigint    |
| optimal\_utilization\_rate     | bigint    |

#### fees

| Field                 | Data Type |
| --------------------- | --------- |
| borrow\_fee\_wad      | bigint    |
| flash\_loan\_fee\_wad | bigint    |
| host\_fee\_percentage | bigint    |
