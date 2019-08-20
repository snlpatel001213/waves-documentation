# ScriptResult

Structure of the execution result of a callable function.

## Constructor

``` ride
ScriptResult(writeSet: WriteSet, transferSet: TransferSet)
```

## Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | writeSet | WriteSet | List of records of an [account data storage](/blockchain/account-data-storage.md) |
| 2 | transferSet | TransferSet | List of [tokens](/blockchain/token.md) of a transfer |
