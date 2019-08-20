# BlockInfo

Structure of a [block](/blockchain/block.md).

## Constructor

``` ride
BlockInfo(timestamp: Int, height: Int, baseTarget: Int, generationSignature: ByteVector, generator: Address, generatorPublicKey: ByteVector)
```

## Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | timestamp | Int | [Unix time](https://en.wikipedia.org/wiki/Unix-time) of the creation of a block |
| 2 | height | Int | [Block height](/blockchain/block/block-height.md) |
| 3 | baseTarget | Int | [Base target](/blockchain/block/block-generation/base-target.md) |
| 4 | generationSignature | ByteVector | Signature of a key block |
| 5 | generator | Address | [Address](/blockchain/address.md) of the [account](/blockchain/account.md) that created a block |
| 6 | generatorPublicKey | ByteVector | Public key of the account that created a block |
