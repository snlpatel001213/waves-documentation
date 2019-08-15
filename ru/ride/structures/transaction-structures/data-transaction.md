# DataTransaction

Структура [транзакции данных](/blockchain/transaction-type/data-transaction.md).

## Конструктор

``` ride
DataTransaction(data: List[DataEntry], id: ByteVector, fee: Int, timestamp: Int, version: Int, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

## Поля структуры

| # | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | data | List[DataEntry] | [Массив данных транзакции](/blockchain/transaction-type/data-transaction.md) |
| 2 | id | ByteVector | ID транзакции |
| 3 | fee | Int | [Комиссия за транзакцию](/blockchain/transaction-fee.md) |
| 4 | timestamp | Int | Временна́я метка транзакции |
| 5 | version | Int | Версия [структуры данных](/blockchain/transaction-data-structure.md)транзакции |
| 6 | sender | Address | [Адрес](/blockchain/address.md) отправителя транзакции |
| 7 | senderPublicKey | ByteVector | Публичный ключ отправителя транзакции |
| 8 | bodyBytes | ByteVector | [Байты тела транзакции](/blockchain/transaction/transaction-body-bytes.md) |
| 9 | proofs | List[ByteVector] | Список [подтверждений](/blockchain/transaction-proof.md) |
