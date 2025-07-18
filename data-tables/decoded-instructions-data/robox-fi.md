---
description: >-
  Providing NFT traders and collectors with leverage without compromising
  collectability.
---

# Robox Fi

**robox.txns**&#x20;

This table has similar schema as of Solana [transactions](../solana-data/transactions.md) table

**robox.parsed**

The table contains the parsed instructions data for [Robox Fi](https://alpha.robox.fi/main). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

| Column Name                                   | Column Type    | Description                                                                                              |
| --------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------- |
| block\_date                                   | date           | Event date                                                                                               |
| block\_time                                   | timestamp      | The (estimated) time this block was produced                                                             |
| block\_slot                                   | bigint         | This block’s slot index in the ledger                                                                    |
| dapp                                          | string         | Solana program address                                                                                   |
| inner\_instruction\_index                     | int            | The order of inner instruction of an instruction in a txns                                               |
| [input\_accounts](robox-fi.md#input-accounts) | array\<string> | Ordered list of accounts to pass to the program                                                          |
| instruction\_index                            | int            | The order of the instruction in a txns                                                                   |
| instruction\_type                             | string         | Name of the function of a Solana program invoked via an instruction                                      |
| is\_inner\_instruction                        | boolean        | Whether the respective instruction of a txns has an inner instruction                                    |
| tx\_id                                        | string         | The first signature in the transaction                                                                   |
| [args](robox-fi.md#args)                      | \<STRUCT>      | The arguments passed to the invoked function. Generated after decoding the instructions data parameter   |

Some columns in the above table needs to be explained a bit for better understanding. Let's go into what each one of them contains.

#### **input accounts**

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>shared.nftMetadata</td><td>string</td></tr><tr><td>nativeMint</td><td>string</td></tr><tr><td>tokenMint</td><td>string</td></tr><tr><td>liquidateAuthorityNftAta</td><td>string</td></tr><tr><td>feeVault</td><td>string</td></tr><tr><td>metadataInfo</td><td>string</td></tr><tr><td>nftEdition</td><td>string</td></tr><tr><td>medenAuctionHouseAuthority</td><td>string</td></tr><tr><td>tswapProgram</td><td>string</td></tr><tr><td>ownerTokenRecord</td><td>string</td></tr><tr><td>meteoraLpMint</td><td>string</td></tr><tr><td>seizedNftsVault</td><td>string</td></tr><tr><td>tensorWhitelistProgram</td><td>string</td></tr><tr><td>bnplProgram</td><td>string</td></tr><tr><td>validationAdapter</td><td>string</td></tr><tr><td>medenEscrowPaymentAccount</td><td>string</td></tr><tr><td>bnAccountNftAta</td><td>string</td></tr><tr><td>shared.tswapPool</td><td>string</td></tr><tr><td>medenProgramAsSigner</td><td>string</td></tr><tr><td>takerBroker</td><td>string</td></tr><tr><td>sellerTokenRecord</td><td>string</td></tr><tr><td>medenAuctionHouseTreasury</td><td>string</td></tr><tr><td>adminNftAta</td><td>string</td></tr><tr><td>fundsSolVault</td><td>string</td></tr><tr><td>shared.tswapMintProof</td><td>string</td></tr><tr><td>adminTokenRecord</td><td>string</td></tr><tr><td>admin</td><td>string</td></tr><tr><td>liquidateAuthorityTokenRecord</td><td>string</td></tr><tr><td>tswap</td><td>string</td></tr><tr><td>user</td><td>string</td></tr><tr><td>medenSeller</td><td>string</td></tr><tr><td>depositCell</td><td>string</td></tr><tr><td>marginAccount</td><td>string</td></tr><tr><td>depositorAta</td><td>string</td></tr><tr><td>destTokenRecord</td><td>string</td></tr><tr><td>pda</td><td>string</td></tr><tr><td>feeSolVault</td><td>string</td></tr><tr><td>vaultNftTokenAccount</td><td>string</td></tr><tr><td>poolNativeAta</td><td>string</td></tr><tr><td>srcNftAta</td><td>string</td></tr><tr><td>poolAta</td><td>string</td></tr><tr><td>nftsOwner</td><td>string</td></tr><tr><td>payer</td><td>string</td></tr><tr><td>seizedNftsVaultTokenRecord</td><td>string</td></tr><tr><td>tensorswapProgram</td><td>string</td></tr><tr><td>currentNftHolderAta</td><td>string</td></tr><tr><td>medenSellerReferral</td><td>string</td></tr><tr><td>tswapPda</td><td>string</td></tr><tr><td>destNftAta</td><td>string</td></tr><tr><td>protocolFeeReceiver</td><td>string</td></tr><tr><td>liquidateAuthority</td><td>string</td></tr><tr><td>bnTokenRecord</td><td>string</td></tr><tr><td>nftPairBox</td><td>string</td></tr><tr><td>medenBuyerTradeState</td><td>string</td></tr><tr><td>pnftShared.authorizationRulesProgram</td><td>string</td></tr><tr><td>medenSellerTradeState</td><td>string</td></tr><tr><td>feesAuthority</td><td>string</td></tr><tr><td>order</td><td>string</td></tr><tr><td>nftReceipt</td><td>string</td></tr><tr><td>tswapFeeVault</td><td>string</td></tr><tr><td>editionInfo</td><td>string</td></tr><tr><td>shared.tswapPoolOwner</td><td>string</td></tr><tr><td>meteoraVault</td><td>string</td></tr><tr><td>tokenRecordInfo</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>metadataProgram</td><td>string</td></tr><tr><td>shared.tswapWhitelist</td><td>string</td></tr><tr><td>medenProgram</td><td>string</td></tr><tr><td>hadeswap</td><td>string</td></tr><tr><td>nftValidationAdapter</td><td>string</td></tr><tr><td>meteoraTokenVault</td><td>string</td></tr><tr><td>associatedTokenProgram</td><td>string</td></tr><tr><td>nftMint</td><td>string</td></tr><tr><td>poolNativeMintAta</td><td>string</td></tr><tr><td>meteoraVaultProgram</td><td>string</td></tr><tr><td>tempEscrowTokenRecord</td><td>string</td></tr><tr><td>bnAccountTokenRecord</td><td>string</td></tr><tr><td>tswapPool</td><td>string</td></tr><tr><td>authorizationRulesProgram</td><td>string</td></tr><tr><td>shared.tswap</td><td>string</td></tr><tr><td>shared.tswapFeeVault</td><td>string</td></tr><tr><td>executor</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>shared.tswapSolEscrow</td><td>string</td></tr><tr><td>solEscrow</td><td>string</td></tr><tr><td>currentNftHolderTokenRecord</td><td>string</td></tr><tr><td>pair</td><td>string</td></tr><tr><td>tswapSingleListing</td><td>string</td></tr><tr><td>nftMetadata</td><td>string</td></tr><tr><td>instructions</td><td>string</td></tr><tr><td>nftEscrow</td><td>string</td></tr><tr><td>ruleSet</td><td>string</td></tr><tr><td>bnAccount</td><td>string</td></tr><tr><td>tswapTokenRecord</td><td>string</td></tr><tr><td>userNftAta</td><td>string</td></tr><tr><td>assetReceiver</td><td>string</td></tr><tr><td>singleListing</td><td>string</td></tr><tr><td>userTokenRecord</td><td>string</td></tr><tr><td>bnAccNftAta</td><td>string</td></tr><tr><td>owner</td><td>string</td></tr><tr><td>bnAta</td><td>string</td></tr><tr><td>srcTokenRecord</td><td>string</td></tr><tr><td>tswapPoolOwnerTokenAta</td><td>string</td></tr><tr><td>medenNotary</td><td>string</td></tr><tr><td>pool</td><td>string</td></tr><tr><td>poolMeteoraLpAta</td><td>string</td></tr><tr><td>pnftShared</td><td>string</td></tr><tr><td>medenSellerNftAta</td><td>string</td></tr><tr><td>medenBuyerReferral</td><td>string</td></tr><tr><td>bnplwlProgram</td><td>string</td></tr><tr><td>authRules</td><td>string</td></tr><tr><td>rent</td><td>string</td></tr><tr><td>tswapWhitelist</td><td>string</td></tr><tr><td>tswapPoolOwner</td><td>string</td></tr><tr><td>depositor</td><td>string</td></tr><tr><td>pnftShared.instructions</td><td>string</td></tr><tr><td>seizedNftsVaultAta</td><td>string</td></tr><tr><td>nftDest</td><td>string</td></tr><tr><td>bnAccTokenRecord</td><td>string</td></tr><tr><td>tokenMetadataProgram</td><td>string</td></tr></tbody></table>

#### args

| Field                                | Data Type      |
| ------------------------------------ | -------------- |
| [poolParams](robox-fi.md#poolparams) | \<STRUCT>      |
| [data](robox-fi.md#data)             | \<STRUCT>      |
| [params](robox-fi.md#params)         | \<STRUCT>      |
| enabledIxs                           | array\<string> |
| disabledIxs                          | array\<string> |

#### **poolParams**

| Field                | Data  Type |
| -------------------- | ---------- |
| poolId               | int        |
| minUserParticipation | int        |
| maxUserParticipation | int        |
| maxMortgageDuration  | int        |
| minInterestRate      | int        |
| maxInterestRate      | int        |

#### **params**

| Field        | Data Type |
| ------------ | --------- |
| poolId       | int       |
| usersAmount  | int       |
| poolsAmount  | int       |
| mortgageTerm | int       |

#### **data**

| Field                                              | Data  Type |
| -------------------------------------------------- | ---------- |
| poolId                                             | int        |
| totalAmount                                        | int        |
| depositCumulative                                  | int        |
| maxMortgageDurationSecs                            | int        |
| minInterestRate                                    | int        |
| maxInterestRate                                    | int        |
| feesAmount                                         | int        |
| amount                                             | int        |
| termSecs                                           | int        |
| loanAmount                                         | int        |
| mortgageTerm                                       | int        |
| rulesAccPresent                                    | boolean    |
| usersAmount                                        | int        |
| maxPrice                                           | int        |
| [authData](robox-fi.md#authdata)                   | \<STRUCT>  |
| [config](robox-fi.md#config)                       | \<STRUCT>  |
| minPrice                                           | int        |
| [authorizationData](robox-fi.md#authorizationdata) | \<STRUCT>  |
| price                                              | int        |
| buyerCreatorRoyaltyBp                              | int        |
| escrowPaymentBump                                  | int        |
| programAsSignerBump                                | int        |
| sellerStateExpiry                                  | int        |
| minimumLpTokenAmount                               | int        |
| unmintAmount                                       | int        |
| minOutAmount                                       | int        |
| nftMint                                            | string     |
| collectionId                                       | string     |
| realPrice                                          | int        |
| poolsAmount                                        | int        |
| [nftState](robox-fi.md#nftstate)                   | \<STRUCT>  |

#### **authData**

| Field                          | Data Type |
| ------------------------------ | --------- |
| [payload](robox-fi.md#payload) | \<STRUCT> |

#### **authorizationData**

| Field                          | Data Type |
| ------------------------------ | --------- |
| [payload](robox-fi.md#payload) | \<STRUCT> |

#### **payload**

| Field                            | Data Type |
| -------------------------------- | --------- |
| name                             | string    |
| [payload](robox-fi.md#payload-1) | \<STRUCT> |

#### payload

| Field                        | Data Type |
| ---------------------------- | --------- |
| name                         | string    |
| [fields](robox-fi.md#fields) | \<STRUCT> |

#### **fields**

| Field                                        | Data Type |
| -------------------------------------------- | --------- |
| valPubkey                                    | string    |
| [valSeeds](robox-fi.md#valseeds)             | \<STRUCT> |
| [valMerkleProof](robox-fi.md#valmerkleproof) | \<STRUCT> |
| valNumber                                    | int       |

#### **valSeeds**

| Field  | Data Type |
| ------ | --------- |
| seeds  | int       |



#### **valMerkleProof**

| Field  | Data Type   |
| ------ | ----------- |
| proof  | array\<int> |

#### **config**

| Field          | Data Type |
| -------------- | --------- |
| poolType       | string    |
| curveType      | string    |
| startingPrice  | int       |
| delta          | int       |
| mmCompoundFees | boolean   |
| mmFeeBps       | int       |

#### **nftState**

| Field    | Data Type |
| -------- | --------- |
| name     | string    |
| fields   | \<STRUCT> |
| closePda | boolean   |

**fields**

| Field | Data Type |
| ----- | --------- |
| pair  | string    |
| price | int       |
