[View code on GitHub](https://github.com/solana-labs/solana/tree/master/na/sdk/program/src/nonce)

The `nonce` module in the Solana SDK is responsible for managing durable transaction nonces, which are used to prevent replay attacks on transactions. This module ensures that each transaction can only be executed once by generating unique nonces for each transaction.

The entry point for the `nonce` module is the `mod.rs` file, which defines the `NONCED_TX_MARKER_IX_INDEX` constant and exports the `State` struct from the `state` module. The `NONCED_TX_MARKER_IX_INDEX` constant is used to identify the index of the nonced transaction marker in the account data, while the `State` struct represents the current state of the nonce account, including the current nonce value and the hash of the recent blockhash.

The `nonce` module is used extensively throughout the Solana project to ensure the security and integrity of transactions. For example, it is used in the `system_instruction` module to generate nonces for system instructions, such as creating new accounts or transferring funds. The `nonce` module is also used in the `transaction` module to generate nonces for user transactions.

```rust
use solana_sdk::nonce::State;

let mut state = State::default();
let new_nonce = state.advance_nonce();
println!("New nonce