[View code on GitHub](https://github.com/solana-labs/solana/blob/master/core/src/multi_iterator_scanner.rs)

The `MultiIteratorScanner` in `solana/core/src/multi_iterator_scanner.rs` is designed to create non-conflicting batches of elements to process in parallel. The main problem it addresses is processing a priority-ordered slice of transactions in parallel without conflicts. The solution is to use multiple iterators, up to the desired batch size, and create batches of transactions that do not conflict with each other.

The `MultiIteratorScanner` struct contains several fields, such as the maximum number of iterators, the slice to iterate over, a payload for shared mutable state, a function to check if an element should be processed, and state for the current positions of each iterator. The struct also provides methods for initializing and advancing the current positions, getting the current items, and marching the iterator to its next position.

The `ProcessingDecision` enum is used to determine how an element should be processed by the scanner. It has three variants: `Now`, `Later`, and `Never`. The `Now` variant indicates that the element should be proces