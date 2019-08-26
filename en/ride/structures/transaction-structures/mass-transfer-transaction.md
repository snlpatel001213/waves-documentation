# MassTransferTransaction

Structure of a [mass transfer transaction](/blockchain/transaction-type/mass-transfer-transaction.md).

## Constructor

``` ride
MassTransferTransaction(feeAssetId: ByteVector|Unit, assetId: ByteVector|Unit, totalAmount: Int, transfers: List[Transfer], transferCount: Int, attachment: ByteVector, id: ByteVector, fee: Int, timestamp: Int, version: Int, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

## Fields

| # | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | feeAssetId | [ByteVector](/ride/data-types/byte-vector.md)&#124;[Unit](/ride/data-types/unit.md) | [Token](/blockchain/token.md) to pay the commission. Currently it can be [WAVES](/blockchain/token/waves.md) only |
| 2 | assetId | [ByteVector](/ride/data-types/byte-vector.md)&#124;[Unit](/ride/data-types/unit.md) | ID of a token |
| 3 | totalAmount | [Int](/ride/data-types/int.md) | Total amount of tokens for mass transfer |
| 4 | transfers | [List](/ride/data-types/list.md)[[Transfer](/ride/structures/common-structures/transfer.md)] | Set of token transfers within current transaction |
| 5 | transferCount | [Int](/ride/data-types/int.md) | Token transfers amount |
| 6 | attachment | [ByteVector](/ride/data-types/byte-vector.md) | Arbitrary data attached to transfer |
| 7 | id | [ByteVector](/ride/data-types/byte-vector.md) | [Transaction ID](/blockchain/transaction/transaction-id.md) |
| 8 | fee | [Int](/ride/data-types/int.md) | [Transaction fee](/blockchain/transaction/transaction-fee.md) |
| 9 | timestamp | [Int](/ride/data-types/int.md) | [Transaction timestamp](/blockchain/transaction/transaction-timestamp.md) |
| 10 | version | [Int](/ride/data-types/int.md) | [Transaction version](/blockchain/transaction/transaction-version.md) |
| 11 | sender | [Address](/ride/structures/common-structures/address.md) | [Address](/blockchain/address.md) of a transaction sender |
| 12 | senderPublicKey | [ByteVector](/ride/data-types/byte-vector.md) | Account public key of a sender |
| 13 | bodyBytes | [ByteVector](/ride/data-types/byte-vector.md) | [Transaction body bytes](/blockchain/transaction/transaction-body-bytes.md) |
| 14 | proofs | [List](/ride/data-types/list.md)[[ByteVector](/ride/data-types/byte-vector.md)] | Array of [proofs](/blockchain/transaction/transaction-proof.md) |
