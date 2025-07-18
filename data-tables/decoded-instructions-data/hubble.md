---
description: >-
  Supercharge Your Liquidity On Solana. Mint USDH against multiple types of
  collateral. Repay whenever you want.
---

# Hubble

**hubble.txns**&#x20;

This table has similar schema as of Solana [transactions](../solana-data/transactions.md) table

**hubble.borrow**

The table contains the parsed instructions data for [Hubble Protocol](https://hubbleprotocol.io/). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                 | Column Type    | Description                                                                                              |
| ------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                 | date           | Event date                                                                                               |
| block\_time                                 | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                 | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                        | string         | Solana program address                                                                                   |
| inner\_instruction\_index                   | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](hubble.md#input-accounts) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                          | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                           | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                      | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                      | string         | The first signature in the transaction                                                                   |
| [args](hubble.md#args)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### **input accounts**

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>systemProgram</td><td>string</td></tr><tr><td>toAccount</td><td>string</td></tr><tr><td>userMetadata</td><td>string</td></tr><tr><td>borrowingVaults</td><td>string</td></tr><tr><td>rent</td><td>string</td></tr><tr><td>stablecoinMintAuthority</td><td>string</td></tr><tr><td>liquidator</td><td>string</td></tr><tr><td>borrowingFeesVault</td><td>string</td></tr><tr><td>otherStablecoinMint</td><td>string</td></tr><tr><td>programData</td><td>string</td></tr><tr><td>burningVault</td><td>string</td></tr><tr><td>program</td><td>string</td></tr><tr><td>additionalBorrowingMarketState</td><td>string</td></tr><tr><td>newMint</td><td>string</td></tr><tr><td>liquidationRewardsVaultAuthority</td><td>string</td></tr><tr><td>liquidationRewardsTo</td><td>string</td></tr><tr><td>treasuryVault</td><td>string</td></tr><tr><td>userHbbStakingAta</td><td>string</td></tr><tr><td>userStablecoinRewardsAta</td><td>string</td></tr><tr><td>borrowingFeesVaultAuthority</td><td>string</td></tr><tr><td>stablecoinMint</td><td>string</td></tr><tr><td>userHbbAta</td><td>string</td></tr><tr><td>newVault</td><td>string</td></tr><tr><td>originalBorrowingMarketState</td><td>string</td></tr><tr><td>clock</td><td>string</td></tr><tr><td>psmVaultAuthority</td><td>string</td></tr><tr><td>usdhMint</td><td>string</td></tr><tr><td>redeemer</td><td>string</td></tr><tr><td>stabilityFeesVault</td><td>string</td></tr><tr><td>psmVault</td><td>string</td></tr><tr><td>hbbAta</td><td>string</td></tr><tr><td>liquidationRewardsVault</td><td>string</td></tr><tr><td>redeemerCollateralAta</td><td>string</td></tr><tr><td>collateralVault</td><td>string</td></tr><tr><td>stakingPoolState</td><td>string</td></tr><tr><td>stablecoinAta</td><td>string</td></tr><tr><td>stabilityProviderState</td><td>string</td></tr><tr><td>collateralVaultsAuthority</td><td>string</td></tr><tr><td>scopePrices</td><td>string</td></tr><tr><td>stabilityPoolProvider</td><td>string</td></tr><tr><td>stakingVaultAuthority</td><td>string</td></tr><tr><td>usdhAta</td><td>string</td></tr><tr><td>liquidatorUsdhAta</td><td>string</td></tr><tr><td>otherStablecoinAta</td><td>string</td></tr><tr><td>adminAuthority</td><td>string</td></tr><tr><td>ownerSignatureState</td><td>string</td></tr><tr><td>borrowingMarketState</td><td>string</td></tr><tr><td>globalConfig</td><td>string</td></tr><tr><td>collateralFrom</td><td>string</td></tr><tr><td>newOwner</td><td>string</td></tr><tr><td>stakingVault</td><td>string</td></tr><tr><td>userStakingState</td><td>string</td></tr><tr><td>treasuryVaultOtherStable</td><td>string</td></tr><tr><td>closingAccount</td><td>string</td></tr><tr><td>burningVaultAuthority</td><td>string</td></tr><tr><td>stablecoinStabilityPoolVaultAuthority</td><td>string</td></tr><tr><td>clearingAgent</td><td>string</td></tr><tr><td>stablecoinStabilityPoolVault</td><td>string</td></tr><tr><td>psmReserve</td><td>string</td></tr><tr><td>hbbMint</td><td>string</td></tr><tr><td>owner</td><td>string</td></tr><tr><td>epochToScaleToSum</td><td>string</td></tr><tr><td>hbbMintAuthority</td><td>string</td></tr><tr><td>redeemerStablecoinAta</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>stablecoinBorrowingAssociatedAccount</td><td>string</td></tr><tr><td>clearingAgentAta</td><td>string</td></tr><tr><td>stabilityPoolState</td><td>string</td></tr><tr><td>treasuryVaultAuthority</td><td>string</td></tr><tr><td>collateralTo</td><td>string</td></tr><tr><td>usdhMintAuthority</td><td>string</td></tr><tr><td>liquidationsQueue</td><td>string</td></tr></tbody></table>

#### args

| Field                        | Data Type   |
| ---------------------------- | ----------- |
| mintId                       | int         |
| setVaultToPda                | bool        |
| vaultIsForLiquidationRewards | bool        |
| key                          | int         |
| value                        | array\<int> |
| action                       | int         |
| tokenId                      | int         |
| collateral                   | int         |
| capInLamports                | bigint      |
| amountInLamports             | bigint      |
| amount                       | bigint      |
| depositAmount                | bigint      |
| depositAsset                 | int         |
| borrowAmount                 | bigint      |
| maxCapacity                  | bigint      |
| intervalLength               | bigint      |
| changeCollateralCap          | bool        |
| collateralId                 | int         |
| accumActionBool              | bool        |
| debtToRepay                  | bigint      |
| token                        | int         |
| bump                         | int         |
| mintFeeBps                   | bigint      |
| burnFeeBps                   | bigint      |
| operationType                | int         |
| interval                     | bigint      |
| changeStableCap              | bool        |
| resetAccums                  | bool        |
| newValue                     | bigint      |
| updateMode                   | int         |
| swapToken                    | string      |
| stablecoinProvided           | bigint      |
| minSwapTokenToReceive        | bigint      |
| signature                    | array\<int> |



**hubble.kamino**

The table contains the parsed instructions data for [Kamino Finance](https://app.kamino.finance/). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                   | Column Type    | Description                                                                                              |
| --------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                   | date           | Event date                                                                                               |
| block\_time                                   | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                   | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                          | string         | Solana program address                                                                                   |
| inner\_instruction\_index                     | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](hubble.md#input-accounts-1) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                            | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                             | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                        | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                        | string         | The first signature in the transaction                                                                   |
| [args](hubble.md#args-1)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### **input accounts**

<table><thead><tr><th width="411.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>treasuryFeeVaultAuthority</td><td>string</td></tr><tr><td>raydiumPoolConfigOrBaseVaultAuthority</td><td>string</td></tr><tr><td>tokenBMint</td><td>string</td></tr><tr><td>treasuryFeeTokenBVault</td><td>string</td></tr><tr><td>rewardVault</td><td>string</td></tr><tr><td>globalConfig</td><td>string</td></tr><tr><td>oldPositionOrBaseVaultAuthority</td><td>string</td></tr><tr><td>newPool</td><td>string</td></tr><tr><td>scopePrices</td><td>string</td></tr><tr><td>poolRewardVault2</td><td>string</td></tr><tr><td>newAccount</td><td>string</td></tr><tr><td>instructionSysvarAccount</td><td>string</td></tr><tr><td>funder</td><td>string</td></tr><tr><td>userTokenAAta</td><td>string</td></tr><tr><td>tokenAVault</td><td>string</td></tr><tr><td>oldTickArrayLowerOrBaseVaultAuthority</td><td>string</td></tr><tr><td>userTokenBAta</td><td>string</td></tr><tr><td>sharesMetadata</td><td>string</td></tr><tr><td>position</td><td>string</td></tr><tr><td>poolTokenVaultB</td><td>string</td></tr><tr><td>poolRewardVault1</td><td>string</td></tr><tr><td>ownerSignatureState</td><td>string</td></tr><tr><td>poolTokenVaultA</td><td>string</td></tr><tr><td>programData</td><td>string</td></tr><tr><td>metadataProgram</td><td>string</td></tr><tr><td>whirlpool</td><td>string</td></tr><tr><td>closingAccount</td><td>string</td></tr><tr><td>mint</td><td>string</td></tr><tr><td>collInfo</td><td>string</td></tr><tr><td>reward1Vault</td><td>string</td></tr><tr><td>sharesMint</td><td>string</td></tr><tr><td>tokenBAta</td><td>string</td></tr><tr><td>userSharesAta</td><td>string</td></tr><tr><td>tokenVaultB</td><td>string</td></tr><tr><td>poolRewardVault0</td><td>string</td></tr><tr><td>tokenAccount</td><td>string</td></tr><tr><td>tickArray2</td><td>string</td></tr><tr><td>program</td><td>string</td></tr><tr><td>sharesMintAuthority</td><td>string</td></tr><tr><td>feeMint</td><td>string</td></tr><tr><td>treasuryFeeTokenAVault</td><td>string</td></tr><tr><td>tokenVaultA</td><td>string</td></tr><tr><td>owner</td><td>string</td></tr><tr><td>treasuryFeeVault</td><td>string</td></tr><tr><td>oldPositionMintOrBaseVaultAuthority</td><td>string</td></tr><tr><td>rewardAta</td><td>string</td></tr><tr><td>tokenBVault</td><td>string</td></tr><tr><td>user</td><td>string</td></tr><tr><td>oldPosition</td><td>string</td></tr><tr><td>scopePriceId</td><td>string</td></tr><tr><td>baseVaultAuthority</td><td>string</td></tr><tr><td>pool</td><td>string</td></tr><tr><td>tokenOwnerAccountA</td><td>string</td></tr><tr><td>positionMetadataAccount</td><td>string</td></tr><tr><td>tokenAMint</td><td>string</td></tr><tr><td>scopeProgramId</td><td>string</td></tr><tr><td>tokenAuthority</td><td>string</td></tr><tr><td>tokenAAta</td><td>string</td></tr><tr><td>oldTickArrayUpperOrBaseVaultAuthority</td><td>string</td></tr><tr><td>tokenOwnerAccountB</td><td>string</td></tr><tr><td>positionMint</td><td>string</td></tr><tr><td>associatedTokenProgram</td><td>string</td></tr><tr><td>positionTokenAccount</td><td>string</td></tr><tr><td>reward2Vault</td><td>string</td></tr><tr><td>system</td><td>string</td></tr><tr><td>userRewardTokenAccount</td><td>string</td></tr><tr><td>actionsAuthority</td><td>string</td></tr><tr><td>oracle</td><td>string</td></tr><tr><td>strategy</td><td>string</td></tr><tr><td>rent</td><td>string</td></tr><tr><td>reward0Vault</td><td>string</td></tr><tr><td>rewardMint</td><td>string</td></tr><tr><td>tickArray0</td><td>string</td></tr><tr><td>tickArray1</td><td>string</td></tr><tr><td>poolProgram</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>adminAuthority</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>tickArrayUpper</td><td>string</td></tr><tr><td>whirlpoolProgram</td><td>string</td></tr><tr><td>tickArrayLower</td><td>string</td></tr><tr><td>raydiumProtocolPositionOrBaseVaultAuthority</td><td>string</td></tr><tr><td>payer</td><td>string</td></tr><tr><td>oldPositionTokenAccountOrBaseVaultAuthority</td><td>string</td></tr><tr><td>tokenInfos</td><td>string</td></tr></tbody></table>

#### **args**

| Field                  | Data Type      |
| ---------------------- | -------------- |
| strategyType           | bigint         |
| tokenACollateralId     | bigint         |
| tokenBCollateralId     | bigint         |
| kaminoRewardIndex      | bigint         |
| collateralToken        | bigint         |
| amount                 | bigint         |
| index                  | bigint         |
| mode                   | bigint         |
| value                  | array\<int>    |
| name                   | string         |
| symbol                 | string         |
| uri                    | string         |
| key                    | int            |
| collateralId           | int            |
| rewardIndex            | int            |
| tickLowerIndex         | bigint         |
| tickUpperIndex         | bigint         |
| bump                   | int            |
| tokenMaxA              | bigint         |
| tokenMaxB              | bigint         |
| sharesAmount           | bigint         |
| action                 | int            |
| tokenAIn               | bigint         |
| tokenBIn               | bigint         |
| rewardCollateralId     | bigint         |
| minCollateralTokenOut  | bigint         |
| targetLimitBps         | bigint         |
| aToB                   | bool           |
| minRepayAmount         | bigint         |
| amountToLeaveToUser    | bigint         |
| otherAmountThreshold   | bigint         |
| sqrtPriceLimit         | double         |
| amountSpecifiedIsInput | bool           |
| signature              | array\<bigint> |
