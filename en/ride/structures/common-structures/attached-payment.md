# AttachedPayment

Structure of an [invoke script transaction](/blockchain/transaction-type/invoke-script-transaction.md) payment.

## Constructor

``` ride
AttachedPayment(assetId: ByteVector|Unit, amount: Int)
```

## Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | assetId | ByteVector&#124;Unit | ID of a [token](/blockchain/token.md) |
| 2 | amount | Int | Payment amount |
