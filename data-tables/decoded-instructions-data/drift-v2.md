---
description: On-Chain Perpetual & Spot Trading with Leverage.
---

# Drift V2

#### drift\_v&#x32;**.txns**

This table has similar schema as of Solana [transactions](../solana-data/transactions.md) table

#### drift\_v&#x32;**.parsed**

The table contains the parsed instructions data for [Drift V2](https://www.drift.trade/). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name               | Column Type    | Description                                                                                              |
| ------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date               | date           | Event date                                                                                               |
| block\_time               | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot               | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                      | string         | Solana program address                                                                                   |
| inner\_instruction\_index | int            | The order of inner instruction of an instruction in a txns                                               |
| input\_accounts           | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index        | int            | The order of the instruction in a txns                                                                   |
| instruction\_type         | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction    | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                    | string         | The first signature in the transaction                                                                   |
| args                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### **input accounts**

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>admin</td><td>string</td></tr><tr><td>adminTokenAccount</td><td>string</td></tr><tr><td>authority</td><td>string</td></tr><tr><td>baseSpotMarket</td><td>string</td></tr><tr><td>driftSigner</td><td>string</td></tr><tr><td>filler</td><td>string</td></tr><tr><td>fillerStats</td><td>string</td></tr><tr><td>fromUser</td><td>string</td></tr><tr><td>insuranceFundStake</td><td>string</td></tr><tr><td>insuranceFundVault</td><td>string</td></tr><tr><td>liquidator</td><td>string</td></tr><tr><td>liquidatorStats</td><td>string</td></tr><tr><td>oracle</td><td>string</td></tr><tr><td>payer</td><td>string</td></tr><tr><td>perpMarket</td><td>string</td></tr><tr><td>quoteAssetMint</td><td>string</td></tr><tr><td>quoteSpotMarket</td><td>string</td></tr><tr><td>rent</td><td>string</td></tr><tr><td>serumFulfillmentConfig</td><td>string</td></tr><tr><td>serumMarket</td><td>string</td></tr><tr><td>serumOpenOrders</td><td>string</td></tr><tr><td>serumProgram</td><td>string</td></tr><tr><td>sourceVault</td><td>string</td></tr><tr><td>spotMarket</td><td>string</td></tr><tr><td>spotMarketMint</td><td>string</td></tr><tr><td>spotMarketVault</td><td>string</td></tr><tr><td>srmVault</td><td>string</td></tr><tr><td>state</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>taker</td><td>string</td></tr><tr><td>takerStats</td><td>string</td></tr><tr><td>toUser</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>user</td><td>string</td></tr><tr><td>userStats</td><td>string</td></tr><tr><td>userTokenAccount</td><td>string</td></tr></tbody></table>

#### args

| Field                                            | Data Type      |
| ------------------------------------------------ | -------------- |
| subAccountId                                     | int            |
| name                                             | array\<string> |
| marketIndex                                      | int            |
| amount                                           | double         |
| reduceOnly                                       | bool           |
| [params](drift-v2.md#params)                     | \<STRUCT>      |
| orderId                                          | int            |
| orderId                                          | int            |
| userOrderId                                      | int            |
| marketType                                       | string         |
| scale                                            | int            |
| direction                                        | string         |
| takerOrderId                                     | int            |
| fulfillmentType                                  | string         |
| nShares                                          | int            |
| sharesToBurn                                     | int            |
| marginRatio                                      | int            |
| marginTradingEnabled                             | bool           |
| delegate                                         | string         |
| makerOrderId                                     | int            |
| liquidatorMaxBaseAssetAmount                     | int            |
| limitPrice                                       | int            |
| assetMarketIndex                                 | int            |
| liabilityMarketIndex                             | int            |
| liquidatorMaxLiabilityTransfer                   | double         |
| perpMarketIndex                                  | int            |
| spotMarketIndex                                  | int            |
| liquidatorMaxPnlTransfer                         | double         |
| quoteSpotMarketIndex                             | int            |
| marketIndexes                                    | array\<int>    |
| expiryTs                                         | int            |
| optimalUtilization                               | int            |
| optimalBorrowRate                                | int            |
| maxBorrowRate                                    | int            |
| oracleSource                                     | string         |
| initialAssetWeight                               | string         |
| maintenanceAssetWeight                           | int            |
| initialLiabilityWeight                           | int            |
| maintenanceLiabilityWeight                       | int            |
| imfFactor                                        | int            |
| liquidatorFee                                    | int            |
| activeStatus                                     | bool           |
| status                                           | string         |
| ammBaseAssetReserve                              | double         |
| ammQuoteAssetReserve                             | double         |
| ammPeriodicity                                   | int            |
| ammPegMultiplier                                 | double         |
| marginRatioInitial                               | int            |
| marginRatioMaintenance                           | int            |
| baseAssetReserve                                 | double         |
| quoteAssetReserve                                | double         |
| sqrtK                                            | double         |
| newPegCandidate                                  | double         |
| unrealizedMaxImbalance                           | int            |
| maxRevenueWithdrawPerPeriod                      | int            |
| quoteMaxInsurance                                | int            |
| ifLiquidationFee                                 | int            |
| insuranceFundUnstakingPeriod                     | int            |
| withdrawGuardThreshold                           | int            |
| userIfFactor                                     | int            |
| totalIfFactor                                    | int            |
| revenueSettlePeriod                              | int            |
| assetTier                                        | string         |
| maxTokenDeposits                                 | int            |
| stepSize                                         | int            |
| tickSize                                         | int            |
| orderSize                                        | int            |
| ordersEnabled                                    | bool           |
| contractTier                                     | string         |
| unrealizedPnlImfFactor                           | int            |
| unrealizedInitialAssetWeight                     | int            |
| unrealizedMaintenanceAssetWeight                 | int            |
| concentrationScale                               | double         |
| curveUpdateIntensity                             | int            |
| lpCooldownTime                                   | int            |
| [feeStructure](drift-v2.md#feestructure)         | \<STRUCT>      |
| initialPctToLiquidate                            | int            |
| liquidationDuration                              | int            |
| [oracleGuardRails](drift-v2.md#oracleguardrails) | \<STRUCT>      |
| settlementDuration                               | int            |
| baseSpread                                       | int            |
| ammJitIntensity                                  | int            |
| maxSlippageRatio                                 | int            |
| maxFillReserveFraction                           | int            |
| maxOpenInterest                                  | double         |
| whitelistMint                                    | string         |
| discountMint                                     | string         |
| exchangeStatus                                   | int            |
| minPerpAuctionDuration                           | int            |
| defaultSpotAuctionDuration                       | int            |

#### params

| Field             | Data Type |
| ----------------- | --------- |
| orderType         | string    |
| marketType        | string    |
| direction         | string    |
| userOrderId       | int       |
| baseAssetAmount   | double    |
| price             | double    |
| marketIndex       | int       |
| reduceOnly        | bool      |
| postOnly          | bool      |
| immediateOrCancel | bool      |
| maxTs             | int       |
| triggerPrice      | double    |
| triggerCondition  | string    |
| oraclePriceOffset | int       |
| auctionDuration   | int       |
| auctionStartPrice | double    |
| auctionEndPrice   | double    |

#### [feeStructure](drift-v2.md#feetiers)

| Field                            | Data Type      |
| -------------------------------- | -------------- |
| [feeTiers](drift-v2.md#feetiers) | array\<STRUCT> |

#### feeTiers

| Field                     | Data Type |
| ------------------------- | --------- |
| feeNumerator              | int       |
| feeDenominator            | int       |
| makerRebateDenominator    | int       |
| referrerRewardNumerator   | int       |
| referrerRewardDenominator | double    |
| refereeFeeNumerator       | int       |
| refereeFeeDenominator     | int       |

#### oracleGuardRails

| Field                                          | Data Type |
| ---------------------------------------------- | --------- |
| [priceDivergence](drift-v2.md#pricedivergence) | \<STRUCT> |
| [validity](drift-v2.md#validity)               | \<STRUCT> |

#### priceDivergence

| Field                           | Data Type |
| ------------------------------- | --------- |
| markOracleDivergenceNumerator   | int       |
| markOracleDivergenceDenominator | int       |

#### validity

| Field                     | Data Type |
| ------------------------- | --------- |
| slotsBeforeStaleForAmm    | int       |
| slotsBeforeStaleForMargin | int       |
| confidenceIntervalMaxSize | int       |
| tooVolatileRatio          | int       |

#### drift\_v&#x32;**.events**

This table has all the drift v2 historically parsed events.

| Field                      | Column Type | Description                                  |
| -------------------------- | ----------- | -------------------------------------------- |
| block\_date                | date        | Event date                                   |
| block\_time                | timestamp   | The (estimated) time this block was produced |
| block\_slot                | bigint      | This block’s slot index in the ledger        |
| tx\_id                     | string      | The first signature in the transaction       |
| dapp                       | string      | Solana program address                       |
| event\_type                |             | The name of the event emitted                |
| [args](drift-v2.md#args-1) | \<STRUCT>   | The arguments of the respective event        |



#### args

| Field                                                                | Data Type   |
| -------------------------------------------------------------------- | ----------- |
| ts                                                                   | int         |
| userAuthority                                                        | string      |
| user                                                                 | string      |
| subAccountId                                                         | int         |
| name                                                                 | array\<int> |
| referrer                                                             | string      |
| direction                                                            | string      |
| depositRecordId                                                      | double      |
| amount                                                               | double      |
| marketIndex                                                          | int         |
| marketDepositBalance                                                 | double      |
| marketWithdrawBalance                                                | double      |
| marketCumulativeDepositInterest                                      | double      |
| marketCumulativeBorrowInterest                                       | double      |
| totalDepositsAfter                                                   | double      |
| totalWithdrawsAfter                                                  | double      |
| explanation                                                          | string      |
| transferUser                                                         | string      |
| depositBalance                                                       | double      |
| cumulativeDepositInterest                                            | double      |
| borrowBalance                                                        | double      |
| cumulativeBorrowInterest                                             | double      |
| optimalUtilization                                                   | int         |
| optimalBorrowRate                                                    | int         |
| maxBorrowRate                                                        | int         |
| fundingPayment                                                       | double      |
| baseAssetAmount                                                      | double      |
| userLastCumulativeFunding                                            | double      |
| ammCumulativeFundingLong                                             | double      |
| ammCumulativeFundingShort                                            | double      |
| recordId                                                             | double      |
| fundingRate                                                          | int         |
| fundingRateLong                                                      | double      |
| fundingRateShort                                                     | double      |
| cumulativeFundingRateLong                                            | double      |
| cumulativeFundingRateShort                                           | double      |
| oraclePriceTwap                                                      | int         |
| markPriceTwap                                                        | int         |
| periodRevenue                                                        | int         |
| baseAssetAmountWithAmm                                               | double      |
| baseAssetAmountWithUnsettledLp                                       | double      |
| pegMultiplierBefore                                                  | double      |
| baseAssetReserveBefore                                               | double      |
| quoteAssetReserveBefore                                              | double      |
| sqrtKBefore                                                          | double      |
| pegMultiplierAfter                                                   | double      |
| baseAssetReserveAfter                                                | double      |
| quoteAssetReserveAfter                                               | double      |
| sqrtKAfter                                                           | double      |
| baseAssetAmountLong                                                  | double      |
| baseAssetAmountShort                                                 | double      |
| totalFee                                                             | double      |
| totalFeeMinusDistributions                                           | double      |
| adjustmentCost                                                       | double      |
| fillRecord                                                           | double      |
| numberOfUsers                                                        | int         |
| [order](drift-v2.md#order)                                           | \<STRUCT>   |
| action                                                               | string      |
| actionExplanation                                                    | string      |
| marketType                                                           | string      |
| filler                                                               | string      |
| fillerReward                                                         | int         |
| fillRecordId                                                         | int         |
| baseAssetAmountFilled                                                | int         |
| quoteAssetAmountFilled                                               | int         |
| takerFee                                                             | int         |
| makerFee                                                             | int         |
| referrerReward                                                       | int         |
| quoteAssetAmountSurplus                                              | int         |
| spotFulfillmentMethodFee                                             | double      |
| taker                                                                | string      |
| takerOrderId                                                         | int         |
| takerOrderDirection                                                  | string      |
| takerOrderBaseAssetAmount                                            | double      |
| takerOrderCumulativeBaseAssetAmountFilled                            | double      |
| takerOrderCumulativeQuoteAssetAmountFilled                           | double      |
| maker                                                                | string      |
| makerOrderId                                                         | int         |
| makerOrderDirection                                                  | string      |
| makerOrderBaseAssetAmount                                            | double      |
| makerOrderCumulativeBaseAssetAmountFilled                            | double      |
| makerOrderCumulativeQuoteAssetAmountFilled                           | double      |
| oraclePrice                                                          | double      |
| nShares                                                              | int         |
| deltaBaseAssetAmount                                                 | int         |
| deltaQuoteAssetAmount                                                | int         |
| pnl                                                                  | double      |
| liquidationType                                                      | string      |
| liquidator                                                           | string      |
| marginRequirement                                                    | double      |
| totalCollateral                                                      | double      |
| marginFreed                                                          | int         |
| liquidationId                                                        | int         |
| bankrupt                                                             | bool        |
| canceledOrderIds                                                     | array\<int> |
| [liquidatePerp](drift-v2.md#liquidateperp)                           | \<STRUCT>   |
| [liquidateSpot](drift-v2.md#liquidatespot)                           | \<STRUCT>   |
| [liquidateBorrowForPerpPnl](drift-v2.md#liquidateborrowforperppnl)   | \<STRUCT>   |
| [liquidatePerpPnlForDeposit](drift-v2.md#liquidateperppnlfordeposit) | \<STRUCT>   |
| [perpBankruptcy](drift-v2.md#perpbankruptcy)                         | \<STRUCT>   |
| [spotBankruptcy](drift-v2.md#spotbankruptcy)                         | \<STRUCT>   |
| quoteAssetAmountAfter                                                | int         |
| quoteEntryAmount                                                     | int         |
| settlePrice                                                          | int         |
| spotMarketIndex                                                      | int         |
| perpMarketIndex                                                      | int         |
| userIfFactor                                                         | int         |
| totalIfFactor                                                        | int         |
| vaultAmountBefore                                                    | int         |
| insuranceVaultAmountBefore                                           | int         |
| totalIfSharesBefore                                                  | double      |
| totalIfSharesAfter                                                   | double      |
| ifSharesBefore                                                       | double      |
| userIfSharesBefore                                                   | double      |
| ifSharesAfter                                                        | double      |
| userIfSharesAfter                                                    | double      |

#### order

| Field                     | Data Type   |
| ------------------------- | ----------- |
| slot                      | int         |
| price                     | int         |
| baseAssetAmount           | double      |
| baseAssetAmountFilled     | int         |
| quoteAssetAmountFilled    | int         |
| triggerPrice              | int         |
| auctionStartPrice         | int         |
| auctionEndPrice           | int         |
| maxTs                     | int         |
| oraclePriceOffset         | int         |
| orderId                   | int         |
| marketIndex               | int         |
| status                    | string      |
| orderType                 | string      |
| marketType                | string      |
| userOrderId               | int         |
| existingPositionDirection | string      |
| direction                 | string      |
| reduceOnly                | bool        |
| postOnly                  | bool        |
| immediateOrCancel         | bool        |
| triggerCondition          | string      |
| auctionDuration           | int         |
| padding                   | array\<int> |



#### liquidatePerp

| Field             | Data Type |
| ----------------- | --------- |
| marketIndex       | int       |
| oraclePrice       | int       |
| quoteAssetAmount  | double    |
| lpShares          | int       |
| fillRecordId      | int       |
| userOrderId       | int       |
| liquidatorOrderId | int       |
| liquidatorFee     | int       |
| ifFee             | int       |

#### liquidateSpot

| Field                | Data Type |
| -------------------- | --------- |
| assetMarketIndex     | int       |
| assetPrice           | double    |
| liabilityMarketIndex | int       |
| liabilityPrice       | int       |
| liabilityTransfer    | double    |
| ifFee                | int       |

#### liquidateBorrowForPerpPnl

| Field                | Data Type |
| -------------------- | --------- |
| perpMarketIndex      | int       |
| marketOraclePrice    | int       |
| pnlTransfer          | double    |
| liabilityMarketIndex | int       |
| liabilityPrice       | int       |
| liabilityTransfer    | double    |

#### liquidatePerpPnlForDeposit

| Field             | Data Type |
| ----------------- | --------- |
| perpMarketIndex   | int       |
| marketOraclePrice | int       |
| pnlTransfer       | double    |
| assetMarketIndex  | int       |
| assetPrice        | int       |
| assetTransfer     | double    |

#### perpBankruptcy

| Filed                      | Data Type |
| -------------------------- | --------- |
| marketIndex                | int       |
| pnl                        | double    |
| ifPayment                  | int       |
| clawbackUser               | string    |
| clawbackUserPayment        | double    |
| cumulativeFundingRateDelta | double    |

#### spotBankruptcy

| Filed                          | Data Type |
| ------------------------------ | --------- |
| marketIndex                    | int       |
| borrowAmount                   | double    |
| ifPayment                      | double    |
| cumulativeDepositInterestDelta | double    |
