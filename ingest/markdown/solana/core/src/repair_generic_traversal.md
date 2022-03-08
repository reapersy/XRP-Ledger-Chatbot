[View code on GitHub](https://github.com/solana-labs/solana/blob/master/core/src/repair_generic_traversal.rs)

The `repair_generic_traversal.rs` file contains code for repairing missing shreds in the Solana ledger. It provides two main functions: `get_unknown_last_index` and `get_closest_completion`. Both functions use a generic traversal iterator, `GenericTraversal`, to traverse the heaviest subtree fork choice.

`get_unknown_last_index` finds all slots with a missing last index and prioritizes them based on the number of shreds received. It returns a vector of `ShredRepairType::HighestShred` for each slot with a missing last index.

```rust
let repairs = get_unknown_last_index(
    &heaviest_subtree_fork_choice,
    &blockstore