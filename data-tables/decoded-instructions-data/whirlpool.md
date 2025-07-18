---
description: >-
  Whirpool is an open-source concentrated liquidity AMM contract on the Solana
  blockchain.
---

# Whirlpool

#### whirlpool.parsed

The table contains the parsed instructions data for orca's [whirlpools](https://www.orca.so/whirlpools). Data related to instruction type, executing account, account arguments, arguments, etc. is available here.

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

<table><thead><tr><th width="374.3333333333333">Field</th><th>Column Type</th></tr></thead><tbody><tr><td>associatedTokenProgram</td><td>string</td></tr><tr><td>funder</td><td>string</td></tr><tr><td>metadataProgram</td><td>string</td></tr><tr><td>metadataUpdateAuth</td><td>string</td></tr><tr><td>oracle</td><td>string</td></tr><tr><td>owner</td><td>string</td></tr><tr><td>position</td><td>string</td></tr><tr><td>positionAuthority</td><td>string</td></tr><tr><td>positionMetadataAccount</td><td>string</td></tr><tr><td>positionMint</td><td>string</td></tr><tr><td>positionTokenAccount</td><td>string</td></tr><tr><td>receiver</td><td>string</td></tr><tr><td>rent</td><td>string</td></tr><tr><td>rewardOwnerAccount</td><td>string</td></tr><tr><td>rewardVault</td><td>string</td></tr><tr><td>systemProgram</td><td>string</td></tr><tr><td>tickArray0</td><td>string</td></tr><tr><td>tickArray1</td><td>string</td></tr><tr><td>tickArray2</td><td>string</td></tr><tr><td>tickArrayLower</td><td>string</td></tr><tr><td>tickArrayUpper</td><td>string</td></tr><tr><td>tokenAuthority</td><td>string</td></tr><tr><td>tokenOwnerAccountA</td><td>string</td></tr><tr><td>tokenOwnerAccountB</td><td>string</td></tr><tr><td>tokenProgram</td><td>string</td></tr><tr><td>tokenVaultA</td><td>string</td></tr><tr><td>tokenVaultB</td><td>string</td></tr><tr><td>whirlpool</td><td>string</td></tr></tbody></table>

#### args

| Field                  | Data Type |
| ---------------------- | --------- |
| aToB                   | boolean   |
| amount                 | bigint    |
| amountSpecifiedIsInput | boolean   |
| bumps                  | \<struct> |
| liquidityAmount        | bigint    |
| otherAmountThreshold   | double    |
| rewardIndex            | int       |
| sqrtPriceLimit         | double    |
| tickLowerIndex         | bigint    |
| tickUpperIndex         | bigint    |
| tokenMaxA              | bigint    |
| tokenMaxB              | bigint    |
| tokenMinA              | bigint    |
| tokenMinB              | bigint    |

#### bumps

| Field        | Data Type |
| ------------ | --------- |
| metadataBump | int       |
| positionBump | int       |

