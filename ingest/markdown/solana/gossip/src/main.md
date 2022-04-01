[View code on GitHub](https://github.com/solana-labs/solana/blob/master/gossip/src/main.rs)

The `solana-gossip` code provides a command-line executable for monitoring a cluster's gossip plane. It has two primary subcommands: `spy` and `rpc-url`.

The `spy` subcommand monitors the gossip entrypoint and waits for a specified number of nodes to be visible or a specific node to appear. It takes several optional arguments, such as `entrypoint`, `gossip_port`, `gossip_host`, `identity`, `num_nodes`, `num_nodes_exactly`, `node_pubkey`, and `timeout`. The `process_spy` function handles the logic for this subcommand, discovering nodes using the `discover` function from `solana_gossip::gossip_service`. After discovering nodes, it processes the results with the `process_spy_results` function, which checks if the desired conditions are met (e.g., the required number of nodes are visible or a specific node is found).

The `rpc-url` subcommand retrieves an RPC URL for the cluster. It takes arguments such as `entrypoint`, `all`, `any`, and `timeout`. The `process_rpc_url` function handles the logic for this subcommand, discovering nodes using the `discover` function similar to the `spy` subcommand. It then filters the discovered nodes based on the specified conditions (e.g., returning all RPC URLs, any RPC URL, or the entrypoint's RPC URL) and prints the resulting RPC URLs.

The `main` function sets up the logger, parses the command-line arguments, and calls the appropriate subcommand function based on the provided arguments. It also initializes the `SocketAddrSpace`, which determines whether to allow contacting private IP addresses.

Example usage:

- To monitor the gossip entrypoint and wait for at least 5 nodes to be visible:

  ```
  solana-gossip spy --entrypoint <entrypoint_host:port> --num-nodes 5
  ```

- To get an RPC URL for the cluster:

  ```
  solana-gossip rpc-url --entrypoint <entrypoint_host:port>
  ```
## Questions: 
 1. **Question**: What is the purpose of the `parse_matches()` function and how does it work?
   **Answer**: The `