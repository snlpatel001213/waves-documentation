# Транзакция сжигания токенов

**Транзакция сжигания токенов** — транзакция, которая сжигает токены.

## Структура данных v2

| **Порядковый номер поля** | **Название поля** | **Тип поля** | **Размер поля в байтах** | **Описание поля** |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Флаг версии | Байт | 1 | Указывает что [структура данных](/blockchain/transaction-data-structure.md) транзакции имеет версию 2 или выше. <br>Значение должно быть равно 0 |
| 2 | Тип транзакции | Байт | 1 | ID [типа транзакции](/blockchain/transaction-type.md). <br>Значение должно быть равно 6 |
| 3 | Номер версии | Байт | 1 | Номер версии структуры данных транзакции. <br>Значение должно быть равно 2 |
| 4 | ID сети | Байт | 1 | Задает сеть, в которой транзакция будет опубликована. <br>84 для тестовой сети, 87 для основной сети |
| 5 | Публичный ключ отправителя | Массив байтов | 32 | Публичный ключ аккаунта отправителя |
| 6 | ID ассета | Массив байтов | 32 | ID сжигаемого ассета |
| 7 | Количество токенов | Длинное целое | 8 | Количество сжигаемых токенов |
| 8 | Комиссия | Длинное целое | 8 | Комиссия за транзакцию в [WAVELET](/blockchain/token/wavelet.md) |
| 9 | Временная метка | Длинное целое | 8 | Unix-время публикации транзакции в сеть |
| 10 | Подтверждения | Массив подтверждений транзакции | `S` | Если массив пустой, то `S`= 3. <br>Если массив не пустой, то `S`= 3 + 2 × `N` + \(`P`<sub>`1`</sub> + `P`<sub>`2`</sub> + ... + `P`<sub>`n`</sub>\), где `N` — количество подтверждений в массиве, `P`<sub>`n`</sub> — размер `N`-го подтверждения в байтах. <br>Максимальное количество подтверждений в массиве — 8. Максимальный размер каждого подтверждения — 64 байта |

## JSON-представление транзакции со структурой данных v2

```json
{  
   "type":6,
   "version":2,
   "chainId":87,
   "senderPublicKey":"9GaQj7gktEiiS1TTTjGbVjU9bva3AbCiawZ11qFZenBX",
   "assetId":"FVxhjrxZYTFCa9Bd4JYhRqXTjwKuhYbSAbD2DWhsGidQ",
   "amount":9999,
   "fee":100000,
   "timestamp":1548660675277,
   "proofs":[  
      "61jCivdv3KTuTY6QHgxt4jaGrXcszWg3vb9TmUR26xv7mjWWwjyqs7X5VDUs9c2ksndaPogmdunHDdjWCuG1GGhh"
   ],
   "id":"csr25XQHT1c965Fg7cY2vJ7XHYVsudPYrUbdaFqgaqL",
   "sender":"3P9QZNrHbyxXj8P9VrJZmVu2euodNtA11UW",
   "height":1370971
}
```

## Структура данных v1

| **Порядковый номер поля** | **Название поля** | **Тип поля** | **Размер поля в байтах** | Описание поля |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Тип транзакции | Байт | 1 | ID типа транзакции. <br>Значение должно быть равно 6 |
| 2 | Публичный ключ отправителя | Массив байтов | 32 | Публичный ключ аккаунта отправителя |
| 3 | ID ассета | Массив байтов | 32 | ID сжигаемого ассета |
| 4 | Количество токенов | Длинное целое | 8 | Количество сжигаемых токенов  |
| 5 | Комиссия | Длинное целое | 8 | Комиссия за транзакцию в WAVELET |
| 6 | Временная метка | Длинное целое | 8 | Unix-время публикации транзакции в сеть |
| 7 | Подпись | Массив байтов | 64 | [Подпись транзакции](/blockchain/transaction-signature.md) |