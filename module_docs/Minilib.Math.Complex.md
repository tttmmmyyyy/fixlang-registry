# `module Minilib.Math.Complex`

Complex number, for example `1 + 2i`.

## Types and aliases

### `namespace Minilib.Math.Complex`

#### `type Complex a = unbox struct { ...fields... }`

A type that represents a complex number.
`a` is typically F64 or F32.

##### field `re : a`

##### field `im : a`

## Traits and aliases

## Trait implementations

### `impl [a : Std::Add] Minilib.Math.Complex::Complex a : Std::Add`

### `impl [a : Minilib.Math.Types::Field] Minilib.Math.Complex::Complex a : Std::Div`

### `impl [a : Std::Eq] Minilib.Math.Complex::Complex a : Std::Eq`

### `impl [a : Minilib.Math.Types::Ring] Minilib.Math.Complex::Complex a : Std::Mul`

### `impl [a : Std::Neg] Minilib.Math.Complex::Complex a : Std::Neg`

### `impl [a : Std::Sub] Minilib.Math.Complex::Complex a : Std::Sub`

### `impl [a : Std::ToString] Minilib.Math.Complex::Complex a : Std::ToString`

Converts a complex number to a string.

### `impl [a : Std::Zero] Minilib.Math.Complex::Complex a : Std::Zero`

## Values

### `namespace Minilib.Math.Complex`

#### `abs : Minilib.Math.Complex::Complex Std::F64 -> Std::F64`

Returns the absolute value of a complex number.

#### `abs2 : [a : Std::Add, a : Std::Mul] Minilib.Math.Complex::Complex a -> a`

Returns the square of the absolute value of a complex number.

#### `arg : Minilib.Math.Complex::Complex Std::F64 -> Std::F64`

Returns the argument of a complex number, ie.

#### `complex : a -> a -> Minilib.Math.Complex::Complex a`

`complex` is synonym for `make`.

#### `conj : [a : Std::Neg] Minilib.Math.Complex::Complex a -> Minilib.Math.Complex::Complex a`

Returns the conjugate complex number.

#### `make : a -> a -> Minilib.Math.Complex::Complex a`

Creates a complex number.