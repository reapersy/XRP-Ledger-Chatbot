[View code on GitHub](https://github.com/solana-labs/solana/blob/master/core/src/cluster_nodes.rs)

The `solana/core/src/cluster_nodes.rs` file contains the implementation of the `ClusterNodes` and `ClusterNodesCache` structures, which are used to manage the nodes in a Solana cluster. These structures are used by the `BroadcastStage` and `RetransmitStage` to determine the peers to which shreds should be sent.

The `ClusterNodes` structure contains information about the nodes in the cluster, including their public keys, stakes, and contact information. It also provides methods for submitting metrics and getting broadcast and retransmit peers.

The `ClusterNodesCache` structure is used to cache the `ClusterNodes` for different epochs. It has a time-to-live (TTL) eviction policy to refresh entries in case gossip contact-infos are updated.

The `RetransmitPeers` structure is used to store information about the retransmit peers for a node, including the root distance, neighbors, children, and their addresses.

The `get_retransmit_peers` function is used to compute the retransmit peers for a node based on its position in the cluster and the fanout value. It returns a `RetransmitPeers` structure containing the computed peers.

The `get_data_plane_fanout` function is used to get the data plane fanout value for a given shred slot and root bank. It takes into account the feature activations for enabling and disabling turbine fanout experiments.

The `check_feature_activation` function checks if a feature is effective for a given shred slot by comparing the feature's activation slot with the shred slot's epoch.

The `make_test_cluster` function is used to create a test cluster with a specified number of nodes and an optional unstaked ratio. It returns the nodes, stakes, and cluster info for the test cluster.

The `get_retransmit_peers` function computes the retransmit peers for a node based on its position in the cluster and the fanout value. It returns an iterator over the computed peers.
## Questions: 
 1. **Question**: What is the purpose of the `ClusterNodes` struct and how is it used in the code?
   **Answer**: The `ClusterNodes` struct is used to store information about the nodes in the cluster, including their public keys, stakes, and contact information. It is used to manage the nodes in the clu