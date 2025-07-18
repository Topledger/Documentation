---
description: All cNFT marketplace secondary sales.
---

# cNFT Trades

How we are indexing our cnft\_trades table? \


We have written a Substreams to index this data. Substreams is a powerful blockchain indexing technology developed by [StreamingFast](https://www.streamingfast.io/).

You can take a look at our indexing code [here](https://github.com/Topledger/solana-programs/tree/main/cnft-trades). The table below contains the project names and their respective program addresses that we have included in our cnft\_trades table.

<table><thead><tr><th width="168">Platform Name</th><th width="315">DAPP</th><th>Instructions</th></tr></thead><tbody><tr><td>tensorswap</td><td><a href="https://solscan.io/account/TCMPhJdwDryooaGtiocG1u3xcYbRpiJzb283XfCZsDp">TCMPhJdwDryooaGtiocG1u3xcYbRpiJzb283XfCZsDp</a></td><td>Buy, TakeBidFullMeta, TakeBidMetaHash</td></tr><tr><td>magiceden</td><td><a href="https://solscan.io/account/M3mxk5W2tt27WGT7THox7PmgRDp4m6NEhL5xvxrBfS1">M3mxk5W2tt27WGT7THox7PmgRDp4m6NEhL5xvxrBfS1</a></td><td>BuyNow</td></tr></tbody></table>

#### **cnft\_trades**

The table below contains all the cnft\_trades table columns , such as signer, buyer, seller, merkle\_tree, maker\_fee, amount, etc.

<table><thead><tr><th width="201.33333333333331">Column Name</th><th width="165">Column Type</th><th>Description</th></tr></thead><tbody><tr><td>block_time</td><td>timestamp</td><td>The (estimated) time this block was produced</td></tr><tr><td>block_slot</td><td>bigint</td><td>This block’s slot index in the ledger</td></tr><tr><td>tx_id</td><td>string</td><td>The first signature in the transaction</td></tr><tr><td>signer</td><td>string</td><td>The initial value from the account_keys array that initiates the transaction and pays the transaction fee</td></tr><tr><td>merkle_tree</td><td>string </td><td>Address of the merkle tree of the cNFT bunch on the block chain</td></tr><tr><td>amount</td><td>double</td><td>The amount paid to buy the cNFT</td></tr><tr><td>leaf_id</td><td>bigint </td><td>The leaf id of the merkle tree</td></tr><tr><td>currency</td><td>string </td><td>Name of the currency in which trade is getting executed</td></tr><tr><td>category</td><td>string</td><td>Various categories of trade such as buy, sell, etc.</td></tr><tr><td>taker_fee</td><td>double</td><td>Is the charge that platform imposes on traders who take/fill the order.</td></tr><tr><td>maker_fee</td><td>double</td><td>Is the charge that platform imposes on traders who make/place orders.</td></tr><tr><td>amm_fee</td><td>double</td><td>Fee charged by the AMM for providing liquidity to the market</td></tr><tr><td>royalty</td><td>double</td><td>Fee that is paid to the original creator of the NFT in exchange for the use of that creator's property.</td></tr><tr><td>buyer</td><td>string </td><td>Address of the buyer of cNFTs in a trade</td></tr><tr><td>seller</td><td>string </td><td>Address of the seller of cNFTs in a trade</td></tr><tr><td>is_inner_instruction</td><td>boolean</td><td>Tells whether there is any inner instruction in the instruction or not </td></tr><tr><td>instruction_index</td><td>bigint</td><td>Index of various instructions in a transaction</td></tr><tr><td>instruction_type</td><td>string</td><td>Name of the function of a Solana program invoked via an instruction</td></tr><tr><td>inner_instruction_index</td><td>bigint</td><td>Index of various inner instructions in a instruction</td></tr><tr><td>outer_program</td><td>string</td><td>The main program of an instruction</td></tr><tr><td>inner_program</td><td>string</td><td>The inner programs under the main/outer program</td></tr><tr><td>txn_fee</td><td>big_int</td><td>Fee this transaction was charged, as paid by first account</td></tr><tr><td>platform</td><td>string</td><td>Name of the platform on which trade is happening</td></tr><tr><td>partition_0</td><td>string </td><td>Date on which the block was produced</td></tr></tbody></table>



####
