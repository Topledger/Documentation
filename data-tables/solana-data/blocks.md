---
description: A contiguous set of entries on the ledger covered by a vote.
---

# Blocks

**tl-solana-merged-data.blocks**

The table contains block data for the Solana blockchain. Use it to identify block activity and transaction changes over time.

| Column Name              | Column Type | Description                                           |
| ------------------------ | ----------- | ----------------------------------------------------- |
| hash                     | string      | string The hash of this block, base-58 encoded        |
| height                   | bigint      | The number of blocks beneath the current block        |
| slot                     | bigint      | This block’s slot index in the ledger                 |
| time                     | timestamp   | The (estimated) time this block was produced          |
| date                     | date        | Used to partition by                                  |
| parent\_slot             | bigint      | The slot index of this block's parent                 |
| previous\_block\_hash    | string      | The hash of this block's parent, base-58 encoded      |
| total\_transactions      | bigint      | Total number of transactions in this block            |
| successful\_transactions | bigint      | Total number of successful transactions in this block |
| failed\_transactions     | bigint      | Total number of failed transactions in this block     |
