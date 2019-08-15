# DataTransaction

Structure of a [data transaction](/blockchain/transaction-type/data-transaction.md).

### Constructor

``` ride
DataTransaction(data: List[DataEntry], id: ByteVector, fee: Int, timestamp: Int, version: Int, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

### Fields

| # | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | data | List[DataEntry] | [Transaction](/blockchain/transaction.md)'s data array |
| 2 | id | ByteVector | Transaction ID |
| 3 | fee | Int | [Transaction fee](/blockchain/transaction-fee.md) |
| 4 | timestamp | Int | Transaction timestamp |
| 5 | version | Int | Version of the [transaction binary format](/blockchain/binary-format/transaction-binary-format.md) |
| 6 | sender | Address | [Address](/blockchain/address.md) of a transaction sender |
| 7 | senderPublicKey | ByteVector | Account public key of a sender |
| 8 | bodyBytes | ByteVector | Transaction's array of bytes |
| 9 | proofs | List[ByteVector] | Array of [proofs](/blockchain/transaction-proof.md) |
