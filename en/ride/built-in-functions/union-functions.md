# Union functions

| # | Name | Description | Complexity |
| :--- | :--- | :--- | :--- |
| 1 | [extract(T&#124;Unit): T](#extract) | Gets a data type from a [union](/ride/data-types/union.md) | 13 |
| 2 | [value(T&#124;Unit): T](#value) | Gets a data type from a [union](/ride/data-types/union.md) | 13 |
| 3 | [valueOrErrorMessage(T&#124;Unit, String): T](#value-error) | Gets a data type from a [union](/ride/data-types/union.md). Throws an exception if there is no data | 13 |

## extract(T|Unit): T<a id="extract"></a>

Gets a data type from a [union](/ride/data-types/union.md).

``` ride
extract(T|Unit): T
```

### Parameters

#### `a`: T|Unit

The argument.

## value(T|Unit): T<a id="value"></a>

Gets a data type from a [union](/ride/data-types/union.md).

``` ride
value(a: T|Unit): T
```

### Parameters

#### a: T|Unit

Value from an option.

## valueOrErrorMessage(T|Unit, String): T<a id="value-error"></a>

Gets a data type from a [union](/ride/data-types/union.md). Throws an exception if there is no data.

``` ride
valueOrErrorMessage(a: T|Unit, msg: String): T
```

### Parameters

#### a: T|Unit

Value from an option.

#### msg: String

Error message.
