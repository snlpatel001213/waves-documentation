# BlockInfo

Structure of a [block](/blockchain/block.md).

## Constructor

``` ride
BlockInfo(timestamp: Int, height: Int, baseTarget: Int, generationSignature: ByteVector, generator: Address, generatorPublicKey: ByteVector)
```

## Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | timestamp | [Int](/ride/data-types/int.md) | [Unix time](https://en.wikipedia.org/wiki/Unix-time) of the creation of a block |
| 2 | height | [Int](/ride/data-types/int.md) | [Block height](/blockchain/block/block-height.md) |
| 3 | baseTarget | [Int](/ride/data-types/int.md) | [Base target](/blockchain/block/block-generation/base-target.md) |
| 4 | generationSignature | [ByteVector](/ride/data-types/byte-vector.md) | Signature of a key block |
| 5 | generator | [Address](/ride/structures/common-structures/address.md) | [Address](/blockchain/address.md) of the [account](/blockchain/account.md) that created a block |
| 6 | generatorPublicKey | [ByteVector](/ride/data-types/byte-vector.md) | Public key of the account that created a block |
