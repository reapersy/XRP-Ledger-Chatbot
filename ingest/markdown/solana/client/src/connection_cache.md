[View code on GitHub](https://github.com/solana-labs/solana/blob/master/client/src/connection_cache.rs)

The `connection_cache.rs` file provides a thin wrapper over the `connection-cache/ConnectionCache` to ease the construction of the ConnectionCache for code dealing with both UDP and QUIC protocols. It is designed to be used in scenarios where both UDP and QUIC are used. For scenarios using only one of the protocols, it is recommended to use `connection-cache/ConnectionCache` directly.

The `ConnectionCache` enum has two variants, `Quic` and `Udp`, each containing an `Arc` reference to a `BackendConnectionCache` with the respective protocol's configuration. The `BlockingClientConnection` and `NonblockingClientConnection` enums also have `Quic` and `Udp` variants, each containing an `Arc` reference to the respective protocol's `BaseClientConnection`.

The `ConnectionCache` provides methods to create a new instance with QUIC or UDP configurations, such as `new`, `new_with_client_options`, and `with_udp`. It also provides methods to get a blocking or non-blocking connection to a specified address, such as `get_connection` and `get_nonblocking_connection`.

The `impl Default for ConnectionCache` block provides a default implementation for creating a new `ConnectionCache` instance. By default, it uses QUIC with a default connection pool size and client certificate.

The `dispatch!` macro is used to define methods for the `C