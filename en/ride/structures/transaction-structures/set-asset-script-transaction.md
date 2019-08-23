# SetAssetScriptTransaction

Structure of a [set asset script transaction](/blockchain/transaction-type/set-asset-script-transaction.md).

## Constructor

``` ride
SetAssetScriptTransaction(script: ByteVector|Unit, assetId: ByteVector, id: ByteVector, fee: Int, timestamp: Int, version: Int, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

## Fields

| # | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | script | [ByteVector](/ride/data-types/byte-vector.md)&#124;[Unit](/ride/data-types/unit.md) | Script that must be set for the [token](/blockchain/token.md) |
| 2 | assetId | [ByteVector](/ride/data-types/byte-vector.md) | ID of a token |
| 3 | id | [ByteVector](/ride/data-types/byte-vector.md) | [Transaction ID](/blockchain/transaction/transaction-id.md) |
| 4 | fee | [Int](/ride/data-types/int.md) | [Transaction fee](/blockchain/transaction/transaction-fee.md) |
| 5 | timestamp | [Int](/ride/data-types/int.md) | [Transaction timestamp](/blockchain/transaction/transaction-timestamp.md) |
| 6 | version | [Int](/ride/data-types/int.md) | Version of the [data structure](/blockchain/binary-format/transaction-binary-format.md) of a transaction |
| 7 | sender | [Address](/ride/structures/common-structures/address.md) | [Address](/blockchain/address.md) of a transaction sender |
| 8 | senderPublicKey | [ByteVector](/ride/data-types/byte-vector.md) | Account public key of a sender |
| 9 | bodyBytes | [ByteVector](/ride/data-types/byte-vector.md) | [Transaction body bytes](/blockchain/transaction/transaction-body-bytes.md) |
| 10 | proofs | [List](/ride/data-types/list.md)[[ByteVector](/ride/data-types/byte-vector.md)] | Array of [proofs](/blockchain/transaction/transaction-proof.md) |
