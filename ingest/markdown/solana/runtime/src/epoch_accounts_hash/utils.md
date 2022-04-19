[View code on GitHub](https://github.com/solana-labs/solana/blob/master/runtime/src/epoch_accounts_hash/utils.rs)

The `utils.rs` file in the `solana/runtime/src/epoch_accounts_hash` directory contains utility functions and types for Epoch Accounts Hash (EAH). EAH is a feature that enables the calculation of a hash of all accounts in a bank at a specific slot. This hash is then stored in the bank's header and can be used to verify the integrity of the accounts in the bank.

The `is_enabled_this_epoch` function determines whether EAH is enabled for the current epoch. The function calculates the minimum calculation interval required for E