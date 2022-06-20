[View code on GitHub](https://github.com/solana-labs/solana/blob/master/tokens/src/token_display.rs)

The `token_display.rs` file in the Solana project defines a `Token` struct and related functionality for displaying and formatting token amounts. The `Token` struct contains an `amount` field of type `u64`, a `decimals` field of type `u8`, and a `token_type` field of type `TokenType`. The `TokenType` enum defines two possible values: `Sol` and `SplToken`. 

The `Token` struct has two associated functions: `sol` and `spl_token`. These functions create a new `Token` instance with the specified `amount`, `decimals`, and `token_type`. The `sol` function sets the `token_type` to `Sol` and the `decimals` to 9, while the `spl_token` function allows the caller to specify the `decimals` value.

The `Token` struct also implements the `Display` and `Debug` traits, which allow instances of the struct to be printed to the console or formatted as strings. The `write_with_symbol` function is used to format the `Token` instance with the approp