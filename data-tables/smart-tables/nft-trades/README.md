---
description: All NFT marketplace secondary sales.
---

# NFT Trades

#### How we are indexing our nft\_trades table?

We have written a Substreams to index this data. Substreams is a powerful blockchain indexing technology developed by [StreamingFast](https://www.streamingfast.io/). \
\
You can take a look at our indexing code [here](https://github.com/Topledger/solana-programs/tree/main/nft-trades). The table below contains the project names and their respective program addresses that we have included in our nft\_trades table.

<table data-full-width="true"><thead><tr><th width="182">Platform Name</th><th width="288">DAPP</th><th></th></tr></thead><tbody><tr><td>tensorswap</td><td><a href="https://solscan.io/account/TSWAPaqyCSx2KABk68Shruf4rp7CxcNi8hAsbdwmHbN">TSWAPaqyCSx2KABk68Shruf4rp7CxcNi8hAsbdwmHbN</a></td><td>BuySingleListing, SellNftTokenPool, BuyNft, SellNftTradePool</td></tr><tr><td>magiceden</td><td><a href="https://solscan.io/account/M2mx93ekt1fmXSVkTrUL9xVFHkmME8HTUi5Cyc5aF7K">M2mx93ekt1fmXSVkTrUL9xVFHkmME8HTUi5Cyc5aF7K</a></td><td>ExecuteSale, ExecuteSaleV2, Mip1ExecuteSaleV2, OcpExecuteSaleV2</td></tr><tr><td>hadeswap</td><td><a href="https://solscan.io/account/hadeK9DLv9eA7ya5KCTqSvSvRZeJC3JgD5a9Y3CNbvu">hadeK9DLv9eA7ya5KCTqSvSvRZeJC3JgD5a9Y3CNbvu</a></td><td>BuyNftFromPair, SellNftToLiquidityPair, SellNftToTokenToNftPair</td></tr><tr><td>coralcube_me_amm</td><td><a href="https://solscan.io/account/mmm3XBJg5gk8XJxEKBvdgptZz6SgK4tXvn36sodowMc">mmm3XBJg5gk8XJxEKBvdgptZz6SgK4tXvn36sodowMc</a></td><td>SolFulfillBuy, SolFulfillSell, SolMip1FulfillBuy, SolMip1FulfillSell,  SolOcpFulfillBuy</td></tr></tbody></table>

#### **nft\_trades**

The table below contains all the nft\_trades table columns , such as signer, buyer, seller, taker\_fee, maker\_fee, amount, etc.

<table><thead><tr><th width="176.33333333333331">Column Name</th><th width="143">Column Type</th><th>Description</th></tr></thead><tbody><tr><td>block_time</td><td>timestamp</td><td>The (estimated) time this block was produced</td></tr><tr><td>block_slot</td><td>bigint</td><td>This block’s slot index in the ledger</td></tr><tr><td>tx_id</td><td>string</td><td>The first signature in the transaction</td></tr><tr><td>mint </td><td>string</td><td>The mint of NFT getting traded</td></tr><tr><td>currency</td><td>string </td><td>Name of the currency in which trade is getting executed</td></tr><tr><td>amount</td><td>double</td><td>The amount paid to buy the NFT</td></tr><tr><td>category</td><td>string </td><td>various categories of trade such as buy, sell, etc.</td></tr><tr><td>buyer</td><td>string </td><td>Address of the buyer of NFT in a trade</td></tr><tr><td>seller</td><td>string</td><td>Address of the seller of NFT in a trade</td></tr><tr><td>taker_fee</td><td>double</td><td>Is the charge that platform imposes on traders who take/fill the order.</td></tr><tr><td>maker_fee</td><td>double</td><td>Is the charge that platform imposes on traders who make/place orders.</td></tr><tr><td>amm_fee</td><td>double</td><td>Fee charged by the AMM for providing liquidity to the market</td></tr><tr><td>royalty</td><td>double</td><td>Fee that is paid to the original creator of the NFT in exchange for the use of that creator's NFT</td></tr><tr><td>is_inner_instruction</td><td>boolean</td><td>Tells whether there is any inner instruction in the instruction or not </td></tr><tr><td>instruction_index</td><td>int</td><td>Index of various instructions in a transaction</td></tr><tr><td>instruction_type</td><td>string</td><td>Name of the function of a Solana program invoked via an instruction</td></tr><tr><td>inner_instruction_index</td><td>int</td><td>Index of various inner instructions in a instruction</td></tr><tr><td>outer_program</td><td>string</td><td>The main program of an instruction</td></tr><tr><td>inner_program</td><td>string</td><td>The inner program under the main/outer program</td></tr><tr><td>txn_fee</td><td>bigint</td><td>Fee this transaction was charged, as paid by first account</td></tr><tr><td>platform</td><td>string</td><td>Name of the platform on which trade happened</td></tr><tr><td>partition_0</td><td>string</td><td>The date on which the block was produced</td></tr></tbody></table>



####
