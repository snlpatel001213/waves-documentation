# Variables

All variables in RIDE are _immutable_. After definition, the value of the variable does not change.

Definition and simultaneous initialization of the variable are performed with the help of the `let` [operator](/ride/operator.md).

You cannot declare a variable without initialisation.

## Relationship between a variable and an expression

During the variable assignment at the right side of the "=" sign must be the expression.

The value of the variable is the result of the expression.

## Examples

Definition of the integer variable.

``` ride
let size = 5
```

Definition of the string variable.

``` ride
let season = "Spring"
```

Since a function is a [definition](/ride/definition.md) and not an expression, you can assign a function value to a variable but not the function itself.

``` ride
func f() = {
    true
}
let result = f()
```

## Laziness

RIDE has the lazy variable initialisation, so the value of the variable is calculated only at the first call to it.
