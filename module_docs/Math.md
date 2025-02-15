# `module Math`

A math library.

This module requires `libm` installed.

## Types and aliases

## Traits and aliases

## Trait implementations

## Values

### `namespace Math`

#### `_gcd_nonneg : Std::I64 -> Std::I64 -> Std::I64`

Calculates greatest common divisor of two non-negative integers.

#### `acos : Std::F64 -> Std::F64`

Calculates arc cosine of the argument.

This is wrapper of C's acos.

#### `asin : Std::F64 -> Std::F64`

Calculates arc sine of the argument.

This is wrapper of C's asin.

#### `atan : Std::F64 -> Std::F64`

Calculates arc tangent of the argument.

This is wrapper of C's atan.

#### `atan2 : Std::F64 -> Std::F64 -> Std::F64`

Calculates arc tangent of y/x for argument x, y.

This is wrapper of C's atan2.

#### `binomial_coefficients : Std::I64 -> Std::Array (Std::Array Std::I64)`

Calculates table (2-dimensional array) of binomial coefficients.

Deprecated: this function will be moved to another project in the future.

`binomial_coefficients(m)` evaluates to an array of arrays `table` where `table.@(n).@(r)` is the binomial coefficient "binom(n, r)" for 0 <= n <= m and 0 <= r <= n.
Here `m` has to be less than or equal to 66 to avoid overflow.

#### `ceil : Std::F64 -> Std::F64`

Calculates the smallest integral value not less than the argument.

This is wrapper of C's ceil.

#### `cos : Std::F64 -> Std::F64`

Calculates the cosine of the argument.

This is wrapper of C's cos.

#### `cosh : Std::F64 -> Std::F64`

Calculates the hyperbolic cosine of the argument.

This is wrapper of C's cosh.

#### `e32 : Std::F32`

Napier's constant as F32

#### `e64 : Std::F64`

Napier's constant as F64

#### `exp : Std::F64 -> Std::F64`

Calculates the natural exponential of the argument.

This is wrapper of C's exp.

#### `floor : Std::F64 -> Std::F64`

Calculates the largest integral value not greater than the argument.

This is wrapper of C's floor.

#### `fmod : Std::F64 -> Std::F64 -> Std::F64`

Calculates the floating point remainder of division.

`x.fmod(y)` evaluates to the remainder of dividing x by y.

This is wrapper of C's fmod.

#### `frexp : Std::F64 -> (Std::F64, Std::I32)`

Splits a floating point number to normalized fraction and an exponent.

This is wrapper of C's frexp.

#### `gcd : Std::I64 -> Std::I64 -> Std::I64`

Calculates greatest common divisor of two integers.
Deprecated: this function will be moved to another project in the future.

NOTE: currently, this function does not support I64::minimum.

#### `ldexp : Std::I32 -> Std::F64 -> Std::F64`

Multiplies a floating point number by power of two.

This is wrapper of C's ldexp.

#### `log : Std::F64 -> Std::F64`

Calculates natural logarithm.

This is wrapper of C's log.

#### `log10 : Std::F64 -> Std::F64`

Calculates base-10 logarithm.

This is wrapper of C's log10.

#### `modf : Std::F64 -> (Std::F64, Std::F64)`

Converts a floating pointer number into the pair of fractional part and integral part.

This is wrapper of C's modf.

#### `pi32 : Std::F32`

pi as F32

#### `pi64 : Std::F64`

pi as F64

#### `pow : Std::F64 -> Std::F64 -> Std::F64`

Power function.

`x.pow(y)` evaluates to x^y.

This is wrapper of C's pow.

#### `sin : Std::F64 -> Std::F64`

Calculates the sine of the argument.

This is wrapper of C's sin.

#### `sinh : Std::F64 -> Std::F64`

Calculates the hyperbolic sine of the argument.

This is wrapper of C's sinh.

#### `sqrt : Std::F64 -> Std::F64`

Calculates square root of the argument.

This is wrapper of C's sqrt.

#### `tan : Std::F64 -> Std::F64`

Calculates the tangent of the argument.

This is wrapper of C's tan.

#### `tanh : Std::F64 -> Std::F64`

Calculates the hyperbolic tangent of the argument.

This is wrapper of C's tanh.