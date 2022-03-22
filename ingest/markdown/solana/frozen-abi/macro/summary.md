[View code on GitHub](https://github.com/solana-labs/solana/tree/master/na/frozen-abi/macro)

The `autodoc/solana/frozen-abi/macro` folder contains Rust macros that help ensure ABI (Application Binary Interface) stability in the Solana project. These macros generate implementations for the `AbiExample` and `AbiEnumVisitor` traits, which are used to test the ABI stability of structs and enums.

The `src/lib.rs` file defines three macros:

1. `frozen_abi`: This macro attribute is used to specify the expected ABI digest for a given struct, enum, or type alias. When applied, it generates a test module that checks if the actual ABI digest matches the expected one. If the digests don't match, it suggests that the ABI might have changed, and the developer should investigate the differences