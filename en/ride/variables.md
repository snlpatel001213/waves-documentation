# Variables

All variables in RIDE are _immutable_. After definition, the value of the variable does not change.

Definition and simultaneous initialization of the variable are performed with the help of the `let` [operator](/ride/operator.md).

You cannot declare a variable without initialisation.

During the variable assignment at the right side of the "=" sign must be an [expression](/ride/expression.md). The value of the variable is the [expression result](/ride/expression.md#expression-result).

## Examples

Definition of the integer variable.

``` ride
let size = 5
```

Definition of the string variable.

``` ride
let season = "Spring"
```

Since a [function](/ride/functions.md) is a [definition](/ride/definition.md) and not an [expression](/ride/expression.md), you can assign a function value to a variable but not the function itself.

``` ride
func f() = {
    true
}
let result = f()
```

## Laziness

RIDE has the lazy variable initialisation, so the value of the variable is calculated only at the first call to it.
