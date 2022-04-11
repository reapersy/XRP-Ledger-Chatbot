[View code on GitHub](https://github.com/solana-labs/solana/blob/master/program-runtime/src/accounts_data_meter.rs)

The `accounts_data_meter.rs` file in the Solana project contains constants and types for tracking and metering the accounts data space during program runtime. The accounts data space has a maximum size it is permitted to grow to, and this module contains the maximum allowed size, in bytes, of the accounts data. The maximum size is set to 128 GB, which is the RAM amount listed under Hardware Recommendations on the Validator Requirements page, and validators often put the ledger on a RAM disk (i.e. tmpfs).

The `AccountsDataMeter` struct is used to meter and track the amount of available accounts data space. It has two fields: `initial` and `delta`. `initial` is the initial amount of accounts data space used (in bytes), and `delta` is the amount of accounts data space that has changed since `initial` (in bytes). The `AccountsDataMeter` struct has four methods: `new()`, `initial()`, `delta()`, and `current()`. 

The `new()` method creates a new `AccountsDataMeter` instance with an initial amount of accounts data space used (in bytes). The `initial()` method returns the initial amount of accounts data space used (in bytes). The `delta()` method returns the amount of accounts data space that has changed (in bytes). The `current()` method returns the current amount of accounts data space used (in bytes). 

The `adjust_delta_unchecked()` method adjusts the space used by accounts data by `amount` (in bytes). It takes a mutable reference to `self` and updates the `delta` field by adding `amount` to it. 

The `tests` module contains two unit tests for the `AccountsDataMeter` struct. The `test_new()` method tests that a new `AccountsDataMeter` instance is created with the correct initial amount o