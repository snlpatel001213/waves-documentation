# ReissueTransaction

Structure of a [reissue transaction](/blockchain/transaction-type/reissue-transaction.md).

## Constructor

``` ride
ReissueTransaction(quantity: Int, assetId: ByteVector, reissuable: Boolean, id: ByteVector, fee: Int, timestamp: Int, version: Int, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

## Fields

| # | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | quantity | [Int](/ride/data-types/int.md) | Amount of [tokens](/blockchain/token.md) |
| 2 | assetId | [ByteVector](/ride/data-types/byte-vector.md) | ID of a token |
| 3 | reissuable | [Boolean](/ride/data-types/boolean.md) | Reissue ability flag |
| 4 | id | [ByteVector](/ride/data-types/byte-vector.md) | [Transaction ID](/blockchain/transaction/transaction-id.md) |
| 5 | fee | [Int](/ride/data-types/int.md) | [Transaction fee](/blockchain/transaction-fee.md) |
| 6 | timestamp | [Int](/ride/data-types/int.md) | [Transaction timestamp](/blockchain/transaction/transaction-timestamp.md) |
| 7 | version | [Int](/ride/data-types/int.md) | Version of the [data structure](/blockchain/binary-format/transaction-binary-format.md) of a transaction |
| 8 | sender | [Address](/ride/structures/common-structures/address.md) | [Address](/blockchain/address.md) of a transaction sender |
| 9 | senderPublicKey | [ByteVector](/ride/data-types/byte-vector.md) | Account public key of a sender |
| 10 | bodyBytes | [ByteVector](/ride/data-types/byte-vector.md) | [Transaction body bytes](/blockchain/transaction/transaction-body-bytes.md) |
| 11 | proofs | [List](/ride/data-types/list.md)[[ByteVector](/ride/data-types/byte-vector.md)] | Array of [proofs](/blockchain/transaction-proof.md) |
