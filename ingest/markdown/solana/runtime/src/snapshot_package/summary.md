[View code on GitHub](https://github.com/solana-labs/solana/tree/master/na/runtime/src/snapshot_package)

The `solana/runtime/src/snapshot_package/compare.rs` file provides essential functions for comparing and prioritizing different types of snapshot and accounts packages within the Solana project. These functions help determine the processing order of packages, ensuring that higher priority packages are processed before lower priority ones.

The main functions provided in this file are:

1. `cmp_snapshot_packages_by_priority(a: &SnapshotPackage, b: &SnapshotPackage) -> Ordering`: This function compares two snapshot packages by their priority, first by their type (Full or Incremental), and then by their slot. Full snapshots have higher priority than 