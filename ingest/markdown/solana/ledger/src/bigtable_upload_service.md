[View code on GitHub](https://github.com/solana-labs/solana/blob/master/ledger/src/bigtable_upload_service.rs)

The `BigTableUploadService` struct is responsible for uploading confirmed blocks to Google BigTable. It runs in a separate thread and continuously checks for new blocks to upload. 

The `new` and `new_with_config` methods create a new instance of `BigTableUploadService`. They take in several parameters, including a `Runtime` instance, a `LedgerStorage` instance for BigTable, a `Blockstore` instance, a `BlockCommitmentCache` instance, and several `AtomicU64` instances. The `new` method calls `new_with_config` with a default `ConfirmedBlockUploadConfig`. 

The `run` method is the main logic of the service. It continuously checks for new blocks to upload by getting the highest root that has complete transaction-status metadata and rewards. It then uploads blocks from the current start slot to the end slot, which is the minimum of the highest complete root and the start slot plus twice the maximum numb