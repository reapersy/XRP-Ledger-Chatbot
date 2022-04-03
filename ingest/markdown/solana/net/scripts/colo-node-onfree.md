[View code on GitHub](https://github.com/solana-labs/solana/blob/master/net/scripts/colo-node-onfree.sh)

The `colo-node-onfree.sh` script is a Bash script that is used to clean up a Solana node's environment when the node is being decommissioned. The script is designed to be run on a node that is being shut down, and it performs two main tasks: process cleanup and filesystem cleanup.

The process cleanup section of the script is responsible for killing any running processes that are associated with the Solana node. This includes screen and tmux sessions, as well as any other processes that are running on the node. The script first retrieves