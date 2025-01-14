# BlockInfo

Структура [блока](/blockchain/block.md).

## Конструктор

``` ride
BlockInfo(timestamp: Int, height: Int, baseTarget: Int, generationSignature: ByteVector, generator: Address, generatorPublicKey: ByteVector)
```

## Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | timestamp | [Int](/ride/data-types/int.md) | Unix-время создания [блока](/blockchain/block.md) |
| 2 | height | [Int](/ride/data-types/int.md) | [Высота блока](/blockchain/block/block-height.md) |
| 3 | baseTarget | [Int](/ride/data-types/int.md) | Сложность создания блока |
| 4 | generationSignature | [ByteVector](/ride/data-types/byte-vector.md) | Подпись ключевого блока |
| 5 | generator | [Address](/ride/structures/common-structures/address.md) | [Адрес](/blockchain/address.md) аккаунта, который создал блок |
| 6 | generatorPublicKey | [ByteVector](/ride/data-types/byte-vector.md) | Публичный ключ аккаунта, который создал блок |
