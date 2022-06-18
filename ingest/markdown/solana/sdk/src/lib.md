[View code on GitHub](https://github.com/solana-labs/solana/blob/master/sdk/src/lib.rs)

The `solana-sdk` crate is the base library for all off-chain programs that interact with Solana or otherwise operate on Solana data structures. It provides a set of modules that are primarily of use to the Solana runtime itself. The crate re-exports the modules of the `solana-program` crate, which is used by on-chain programs. 

The `solana-sdk` crate provides a set of additional crates that provide capabilities built on top of it. These include the `solana-client` crate for interacting with a Solana node via the JSON-RPC API, the `solana-cli-config` crate for loading and saving the Solana CLI configuration file, and the `solana-clap-utils` crate for setting up the CLI using `clap`, 