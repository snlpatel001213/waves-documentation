# Бинарный формат транзакции генезиса

## Бинарный формат версии 1

| Порядковый номер поля | Название поля | Название JSON-поля |Тип поля | Размер поля в байтах | Описание поля |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Тип транзакции |type| [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | ID [типа транзакции](/blockchain/transaction-type.md). <br>Значение должно быть равно 6 |
| 2 | Временная метка | timestamp | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 | Unix-время отправки транзакции в блокчейн |
| 3 | Адрес аккаунта | recipient | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 26 |  |
| 4 | Количество | amount | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 | Количество [WAVES](/blockchain/token/waves.md), которое будет начислено аккаунту |
| 5 | Комиссия | fee | [Long](/blockchain/blockchain/blockchain-data-types.md)| 8 | Комиссия за транзакцию в [WAVELET](/blockchain/token/wavelet.md) |
| 6 | Подпись | signature | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 64 | [Подпись транзакции](/blockchain/transaction/transaction-signature.md) |

## JSON-представление транзакции бинарного формата версии 1 <a id="json"></a>

```json
{
   "type":1,
   "timestamp":2686163577562422135,
   "recipient":"3MowSBodyYH25xayqCWoCtY7KBHc7wvv8cs",
   "amount":3074457345618258602,
   "id":"3E2qJVdMC1wzFEZwCyejA1a1AwDv52wwi2CRPaf5uNw3WTQYNW9C32cxGWBehJi2ED5f2YtYg2RJRcAX2U3wPhxy",
   "fee":0,
   "signature":"3E2qJVdMC1wzFEZwCyejA1a1AwDv52wwi2CRPaf5uNw3WTQYNW9C32cxGWBehJi2ED5f2YtYg2RJRcAX2U3wPhxy",
}
```
