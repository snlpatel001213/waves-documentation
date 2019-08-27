# Бинарный формат транзакции создания псевдонима

## Бинарный формат версии 2

| Порядковый номер поля | Название поля | Название JSON-поля | Тип поля | Размер поля в байтах | Описание поля |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Флаг версии |  | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Указывает что [структура данных](/blockchain/binary-format/transaction-binary-format.md) транзакции имеет версию 2 или выше.<br>Значение должно быть равно 0 |
| 2 | Тип транзакции | type | [Byte](/blockchain/blockchain/blockchain-data-types.md)  | 1 | ID [типа транзакции](/blockchain/transaction-type.md).<br>Значение должно быть равно 10 |
| 3 | Версия | version | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Номер версии структуры данных транзакции.<br> Значение должно быть равно 2 |
| 4 | Публичный ключ отправителя | senderPublicKey | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 | Публичный ключ аккаунта отправителя |
| 5 | Длина псевдонима | | [Short](/blockchain/blockchain/blockchain-data-types.md) | 2 | Длина псевдонима адреса аккаунта |
| 6 | Псевдоним | alias | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | от 4 до 30 | Псевдоним адреса аккаунта |
| 7 | Комиссия | fee | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 | Комиссия за транзакцию в [WAVELET](/blockchain/token/wavelet.md) |
| 8 | Временная метка | timestamp | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 | Unix-время отправки транзакции в блокчейн |
| 9 | Подтверждения | proofs | Массив [подтверждений](/blockchain/transaction/transaction-proof.md) | `S` | Если массив пустой, то `S` = 3. <br> Если массив не пустой, то `S`   = 3 + 2 × `N` + (`P`<sub>1</sub> + `P`<sub>2</sub> + ... + `P`<sub>n</sub>), <br>где <br>`N` — количество подтверждений в массиве,<br> `P`<sub>n</sub> — размер `N`-го подтверждения в байтах. <br> Максимальное количество подтверждений в массиве — 8. Максимальный размер каждого подтверждения — 64 байта |

## JSON-представление транзакции бинарного формата версии 2

```json
{
   "type":10,
   "version":2,
   "senderPublicKey":"B3f8VFh6T2NGT26U7rHk2grAxn5zi9iLkg4V9uxG6C8q",
   "alias":"2.1.0a",
   "fee":100000,
   "timestamp":1548666019772,
   "proofs":[
      "3cUM8Eq5KfmbS6q1qHDfzhX98YzER1ocnVjVAHG9HSkQdw86zjqxUfmsUPVwnVgwu5zatt3ETLnNFteobRMyR8bY"
   ],
   "id":"5CZV9RouJs7uaRkZY741WDy9zV69npX1FTZqxo5fsryL",
   "sender":"3PNaua1fMrQm4TArqeTuakmY1u985CgMRk6",
   "height":1371063
}
```

## Бинарный формат версии 1

| Порядковый номер поля | Название поля | Тип поля | Размер поля в байтах | Описание поля |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Тип транзакции | [Byte](/blockchain/blockchain/blockchain-data-types.md)  | 1 | ID типа транзакции.<br>Значение должно быть равно 6 |
| 2 | Публичный ключ отправителя | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 | Публичный ключ аккаунта отправителя |
| 3 | Длина псевдонима  | [Short](/blockchain/blockchain/blockchain-data-types.md) | 2 | Длина псевдонима адреса аккаунта |
| 4 | Псевдоним | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | от 4 до 30 | Псевдоним адреса аккаунта |
| 5 | Комиссия | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 | Комиссия за транзакцию в WAVELET |
| 6 | Временная метка | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 | Unix-время отправки транзакции в блокчейн |
| 7 | Подпись | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 64 | [Подпись транзакции](/blockchain/transaction/transaction-signature.md) |
