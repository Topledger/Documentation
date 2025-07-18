---
description: Asset backed trading with zero price impact & upto 100x leverage
---

# Flash

**flash.txns**

This table has similar schema as of Solana [transactions](../solana-data/transactions.md) table

#### flash.perpetuals

The perpetual table contains the parsed instructions data for [flash perpetuals](https://beast.flash.trade/). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                | Column Type    | Description                                                                                              |
| ------------------------------------------ | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                | date           | Event date                                                                                               |
| block\_time                                | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                       | string         | Solana program address                                                                                   |
| inner\_instruction\_index                  | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](flash.md#input-accounts) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                         | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                          | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                     | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                     | string         | The first signature in the transaction                                                                   |
| [args](flash.md#args)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### **input accounts**

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>dispensingCustody</td><td>string</td></tr><tr><td>feepayer</td><td>string</td></tr><tr><td>program</td><td>string</td></tr><tr><td>collateralOracleAccount</td><td>string</td></tr><tr><td>custody</td><td>string</td></tr><tr><td>transferAuthority</td><td>string</td></tr><tr><td>ixSysvar</td><td>string</td></tr><tr><td>receivingCustodyTokenAccount</td><td>string</td></tr><tr><td>feeCustodyTokenAccount</td><td>string</td></tr><tr><td>eventAuthority</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>custodyTokenMint</td><td>string</td></tr><tr><td>receivingFlpTokenAccount</td><td>string</td></tr><tr><td>receivingTokenAccount</td><td>string</td></tr><tr><td>flpStakeAccount</td><td>string</td></tr><tr><td>custodyOracleAccount</td><td>string</td></tr><tr><td>feeCustody</td><td>string</td></tr><tr><td>receivingCustody</td><td>string</td></tr><tr><td>pool</td><td>string</td></tr><tr><td>position</td><td>string</td></tr><tr><td>custodyTokenAccount</td><td>string</td></tr><tr><td>collectionMint</td><td>string</td></tr><tr><td>oracleAccount</td><td>string</td></tr><tr><td>targetOracleAccount</td><td>string</td></tr><tr><td>rewardCustody</td><td>string</td></tr><tr><td>nftMint</td><td>string</td></tr><tr><td>receivingAccount</td><td>string</td></tr><tr><td>fundingAccount</td><td>string</td></tr><tr><td>signer</td><td>string</td></tr><tr><td>targetCustody</td><td>string</td></tr><tr><td>feeDistributionTokenAccount</td><td>string</td></tr><tr><td>lpTokenAccount</td><td>string</td></tr><tr><td>market</td><td>string</td></tr><tr><td>perpetuals</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>stakedLpTokenAccount</td><td>string</td></tr><tr><td>authorizationRulesProgram</td><td>string</td></tr><tr><td>admin</td><td>string</td></tr><tr><td>dispensingCustodyOracleAccount</td><td>string</td></tr><tr><td>rent</td><td>string</td></tr><tr><td>dispensingCustodyTokenAccount</td><td>string</td></tr><tr><td>perpetualsProgramData</td><td>string</td></tr><tr><td>upgradeAuthority</td><td>string</td></tr><tr><td>metadataAccount</td><td>string</td></tr><tr><td>collateralCustody</td><td>string</td></tr><tr><td>nftTokenAccount</td><td>string</td></tr><tr><td>authorizationRulesAccount</td><td>string</td></tr><tr><td>poolFlpTokenAccount</td><td>string</td></tr><tr><td>referralAccount</td><td>string</td></tr><tr><td>metadataProgram</td><td>string</td></tr><tr><td>multisig</td><td>string</td></tr><tr><td>fundingFlpTokenAccount</td><td>string</td></tr><tr><td>lpTokenMint</td><td>string</td></tr><tr><td>tradingAccount</td><td>string</td></tr><tr><td>perpetualsProgram</td><td>string</td></tr><tr><td>collateralCustodyTokenAccount</td><td>string</td></tr><tr><td>receivingCustodyOracleAccount</td><td>string</td></tr><tr><td>oracleAuthority</td><td>string</td></tr><tr><td>owner</td><td>string</td></tr></tbody></table>

#### args

| Field  | Data Type |
| ------ | --------- |
| Params | \<STRUCT> |

params

| Field               | Data Type      |
| ------------------- | -------------- |
| minSignatures       | int            |
| permissions         | \<STRUCT>      |
| name                | string         |
| maxAumUsd           | int            |
| metadataTitle       | string         |
| metadataSymbol      | string         |
| metadataUri         | string         |
| isStable            | bool           |
| depegAdjustment     | bool           |
| isVirtual           | bool           |
| oracle              | \<STRUCT>      |
| pricing             | \<STRUCT>      |
| fees                | \<STRUCT>      |
| borrowRate          | \<STRUCT>      |
| ratios              | array\<STRUCT> |
| side                | string         |
| correlation         | bool           |
| maxPayoffBps        | int            |
| customOracleAccount | string         |
| maxDivergenceBps    | int            |
| maxConfBps          | int            |
| maxPriceAgeSec      | int            |
| rewardThreshold     | int            |
| allowUngatedTrading | bool           |
| tradingDiscount     | list\<int>     |
| referralRebate      | list\<int>     |
| referralDiscount    | int            |
| voltageMultiplier   | \<STRUCT>      |
| oracleAuthority     | string         |
| stakingFeeShareBps  | int            |
| feeShareBps         | int            |
| amount              | int            |
| price               | int            |
| expo                | int            |
| conf                | int            |
| ema                 | int            |
| publishTime         | int            |
| time                | int            |
| amountIn            | int            |
| minAmountOut        | int            |
| useFeesPool         | bool           |
| minLpAmountOut      | int            |
| lpAmountIn          | int            |
| depositAmount       | int            |
| unstakeAmount       | int            |
| collectionIndex     | int            |
| priceWithSlippage   | \<STRUCT>      |
| collateralAmount    | int            |
| sizeAmount          | int            |
| privilege           | string         |
| collateralDelta     | int            |
| sizeDelta           | int            |
| collateral          | int            |
| size                | int            |
| useFeePool          | bool           |
| event\_name         | string         |
| fields              | \<STRUCT>      |



#### permissions

| Field                     | Data Type |
| ------------------------- | --------- |
| allowSwap                 | bool      |
| allowAddLiquidity         | bool      |
| allowRemoveLiquidity      | bool      |
| allowOpenPosition         | bool      |
| allowClosePosition        | bool      |
| allowCollateralWithdrawal | bool      |
| allowSizeChange           | bool      |
| allowLiquidation          | bool      |
| allowFlpStaking           | bool      |
| allowFeeDistribution      | bool      |
| allowUngatedTrading       | bool      |
| allowFeeDiscounts         | bool      |
| allowReferralRebates      | bool      |

#### oracle

| Field               | Data Type |
| ------------------- | --------- |
| oracleAccount       | string    |
| customOracleAccount | string    |
| oracleType          | string    |
| maxDivergenceBps    | int       |
| maxConfBps          | int       |
| maxPriceAgeSec      | int       |

#### pricing

| Field                | Data Type |
| -------------------- | --------- |
| tradeSpreadLong      | int       |
| tradeSpreadShort     | int       |
| swapSpread           | int       |
| minInitialLeverage   | int       |
| maxInitialLeverage   | int       |
| maxLeverage          | int       |
| minCollateralUsd     | int       |
| delaySeconds         | int       |
| maxUtilization       | int       |
| maxPositionLockedUsd | int       |
| maxTotalLockedUsd    | int       |

####

#### fees

| Field            | Data Type |
| ---------------- | --------- |
| mode             | string    |
| swapIn           | \<STRUCT> |
| swapOut          | \<STRUCT> |
| stableSwapIn     | \<STRUCT> |
| stableSwapOut    | \<STRUCT> |
| addLiquidity     | \<STRUCT> |
| removeLiquidity  | \<STRUCT> |
| openPosition     | int       |
| closePosition    | int       |
| removeCollateral | int       |

#### swapIn

| Field     | Data Type |
| --------- | --------- |
| minFee    | int       |
| targetFee | int       |
| maxFee    | int       |

####

#### swapOut

| Field     | Data Type |
| --------- | --------- |
| minFee    | int       |
| targetFee | int       |
| maxFee    | int       |

####

#### stableSwapIn

| Field     | Data Type |
| --------- | --------- |
| minFee    | int       |
| targetFee | int       |
| maxFee    | int       |

#### stableSwapOut

| Field     | Data Type |
| --------- | --------- |
| minFee    | int       |
| targetFee | int       |
| maxFee    | int       |

#### addLiquidity

| Field     | Data Type |
| --------- | --------- |
| minFee    | int       |
| targetFee | int       |
| maxFee    | int       |

#### removeLiquiduty

| Field     | Data Type |
| --------- | --------- |
| minFee    | int       |
| targetFee | int       |
| maxFee    | int       |

#### borrowRate

| Field              | Data Type |
| ------------------ | --------- |
| baseRate           | int       |
| slope1             | int       |
| slope2             | int       |
| optimalUtilization | int       |

#### ratios

| Field  | Data Type |
| ------ | --------- |
| target | int       |
| min    | int       |
| max    | int       |



**voltageMultiplier**

| Field   | Data Type |
| ------- | --------- |
| volume  | int       |
| rewards | int       |
| rebates | int       |

**priceWithSlippage**

| Field    | Data Type |
| -------- | --------- |
| price    | int       |
| exponent | int       |



#### fields

Whenever there is instruction type of 'events\_log' then events are getting emitted in instruction itself and the event type can be known from args.params.event\_name and the argument in the event can be fetched from args.params.field.

| Field            | Data Type |
| ---------------- | --------- |
| activated        | int       |
| owner            | string    |
| market           | string    |
| collateralAmount | int       |
| poolName         | string    |
| custodyId        | string    |
| amountIn         | string    |
| lpAmountOut      | int       |
| priceUsd         | int       |
| sizeAmount       | int       |
| sizeUsd          | int       |
| profitUsd        | int       |
| lossUsd          | int       |
| feeCollected     | int       |
| deactivated      | int       |
| sizeDelta        | int       |
| sizeDeltaUsd     | int       |
| settledReturns   | int       |
| deltaProfitUsd   | int       |
| deltaLossUsd     | int       |
| lpTokens         | int       |
| feeAmount        | int       |
| collateralUsd    | int       |
| lpAmountIn       | int       |
| custodyIdIn      | int       |
| custodyIdOut     | int       |
| amountOut        | int       |
| feeInAmount      | int       |
| feeOutAmount     | int       |



#### flash.perp\_composability

The perp\_composability table contains the parsed instructions data for [perpetual composability](https://beast.flash.trade/) . Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                  | Column Type    | Description                                                                                              |
| -------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                  | date           | Event date                                                                                               |
| block\_time                                  | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                  | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                         | string         | Solana program address                                                                                   |
| inner\_instruction\_index                    | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](flash.md#input-accounts-1) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                           | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                            | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                       | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                       | string         | The first signature in the transaction                                                                   |
| [args](flash.md#args-1)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### input accounts

| Fields                         |        |
| ------------------------------ | ------ |
| tokenProgram                   | string |
| dispensingCustodyTokenAccount  | string |
| perpProgram                    | string |
| market                         | string |
| owner                          | string |
| perpetuals                     | string |
| transferAuthority              | string |
| positionPool                   | string |
| collateralCustodyTokenAccount  | string |
| eventAuthority                 | string |
| dispensingCustody              | string |
| ixSysvar                       | string |
| receivingAccount               | string |
| collateralCustody              | string |
| receivingCustodyTokenAccount   | string |
| targetOracleAccount            | string |
| dispensingCustodyOracleAccount | string |
| collateralOracleAccount        | string |
| fundingAccount                 | string |
| fundingAccount                 | string |
| receivingCustody               | string |
| position                       | string |
| systemProgram                  | string |
| swapPool                       | string |

#### args

| Field  | Data Type |
| ------ | --------- |
| params | \<STRUCT> |



#### params

| Fields                 | Data Type |
| ---------------------- | --------- |
| amountIn               | int       |
| minAmountOut           | bool      |
| openPriceWithSlippage  | \<STRUCT> |
| openSizeAmount         | int       |
| privilege              | string    |
| closePriceWithSlippage | \<STRUCT> |
| collateralDelta        | int       |



#### openPriceWiithSlippage

| Field    | Data Type |
| -------- | --------- |
| price    | int       |
| exponent | int       |



#### closePriceWithSlippage

| Field    | Data Type |
| -------- | --------- |
| price    | int       |
| exponent | int       |

####

####

####
