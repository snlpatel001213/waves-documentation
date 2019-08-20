# Asset

Структура [токена](/blockchain/token.md).

## Конструктор

``` ride
Asset(quantity: Int, decimals: Int, issuer: Address, issuerPublicKey: ByteVector, reissuable: Boolean, scripted: Boolean, sponsored: Boolean)
```

## Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | quantity | [Int](/ride/data-types/int.md) | Количество выпущенных [токенов](/blockchain/token.md) |
| 2 | decimals | [Int](/ride/data-types/int.md) | Число знаков после запятой у токена |
| 3 | issuer | [Address](/ride/structures/common-structures/address.md) | Адрес аккаунта, который выпустил токен |
| 4 | issuerPublicKey | [ByteVector](/ride/data-types/byte-vector.md) | Публичный ключ аккаунта, выпустившего токен |
| 5 | reissuable | [Boolean](/ride/data-types/boolean.md) | true — токен можно довыпускать, false — нельзя довыпускать |
| 6 | scripted | [Boolean](/ride/data-types/boolean.md) | true — [смарт-ассет](/blockchain/smart-asset.md), false — обычный токен |
| 7 | sponsored | [Boolean](/ride/data-types/boolean.md) | true — токен спонсируемый, false — неспонсируемый |
