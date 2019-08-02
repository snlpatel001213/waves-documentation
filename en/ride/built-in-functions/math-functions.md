# Math functions

| # | Name | Description | Complexity |
|:---| :--- | :--- | :--- |
| 1 | [fraction(Int, Int, Int): Int](#fraction) | Converts arbitrarily large signed integer to integer | 1 |
| 2 |[log(Int, Int, Int, Int, Int, Union): Int](#log)| Calculates logarithm of the number | 100 |
| 3 |[pow(Int, Int, Int, Int, Int, Union): Int](#pow) | Raises the number to a power| 100 |

## fraction(Int, Int, Int): Int<a id="fraction"></a>

Converts arbitrarily large signed integer to integer.

```ride
fraction(value: Int, numerator: Int, denominator: Int): Int
```

### Parameters

#### `value`: Int

Arbitrarily large signed integer.

#### `numerator`: Int

Numerator of the fraction.

#### `denominator`: Int

Denominator of the fraction.

### Conversion formula

Conversion is done by the formula:

```ride
fraction = value × numerator / denominator
```

## log(Int, Int, Int, Int, Int, Union): Int<a id="log"></a>

Calculates logarithm of the number.

``` ride
log(value: Int, ep: Int, base: Int, bp: Int, rp: Int, round: Union): Int
```

### Parameters

#### `value`: Int

Given number.

#### `ep`: Int

Number of decimals of the given number.

#### `base`: Int

Base of the logarithm.

#### `bp`: Int

Number of decimals of the base.

#### `rp`: Int

Number of decimals of the resulting value.

#### `round`: Union

One of the [rounding function](#rounding-functions).

The `HalfUp()` function may be used as the default value.

## pow(Int, Int, Int, Int, Int, Union): Int<a id="pow"></a>

Raises the number to a power.

``` ride
pow(base: Int, bp: Int, exponent: Int, ep: Int, rp: Int, round: Union): Int
```

### Parameters

#### `base`: Int

Given number.

#### `bp`: Int

Number of decimals of the given number.

#### `exponent`: Int

Power.

#### `ep`: Int

Number of decimals of power.

#### `rp`: Int

Number of decimals of the resulting value.

#### `round`: Union

One of the [rounding functions](#rounding-functions).

The `HalfUp()` function may be used as the default value.

## Rounding functions

The rounding functions are _only_ used as the parameters of [log](#log) and [pow](#pow) functions and they are not used by themselves.

|Name | Description |
| :--- | :--- |
| Ceiling(): Int | Rounding towards positive infinity |
| Down(): Int | Rounding towards zero |
| Floor(): Int | Rounding towards negative infinity |
| HalfDown(): Int | Rounding down towards the nearest integer |
| HalfEven(): Int | Rounding towards the nearest even integer |
| HalfUp(): Int   | Rounding up towards the nearest integer   |
| Up(): Int | Rounding away from zero |

### Examples

| | -1.6 | -1.5 | -1.4 | -1.0 | 1.0 | 1.4 | 1.5 | 1.6 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Ceiling | -1 | -1 | -1 | -1 | 1 | 2 | 2 | 2 |
| Down | -1 | -1 | -1 | -1 | 1 | 1 | 1 | 1 |
| Floor | -2 | -2 | -2 | -1 | 1 | 1 | 1 | 1 |
| HalfDown | -2 | -1 | -1 | -1 | 1 | 1 | 1 | 2 |
| HalfEven | -2 | -2 | -1 | -1 | 1 | 1 | 2 | 2 |
| HalfUp | -2 | -2 | -1 | -1 | 1 | 1 | 2 | 2 |
| Up | -2 | -2 | -2 | -1 | 1 | 2 | 2 | 2 |
