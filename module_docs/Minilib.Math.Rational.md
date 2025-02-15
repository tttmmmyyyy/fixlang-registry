# `module Minilib.Math.Rational`

Rational number arithmetic, for example `1/2 + 1/3 = 5/6`.

## Types and aliases

### `namespace Minilib.Math.Rational`

#### `type Rational a = unbox struct { ...fields... }`

Rational number

##### field `num : a`

##### field `den : a`

## Traits and aliases

## Trait implementations

### `impl [a : Minilib.Math.Types::Euclid, a : Minilib.Math.Types::One] Minilib.Math.Rational::Rational a : Minilib.Math.Types::One`

### `impl [a : Minilib.Math.Types::Euclid] Minilib.Math.Rational::Rational a : Std::Add`

### `impl [a : Minilib.Math.Types::Euclid] Minilib.Math.Rational::Rational a : Std::Div`

### `impl [a : Minilib.Math.Types::Euclid] Minilib.Math.Rational::Rational a : Std::Eq`

### `impl [a : Minilib.Math.Types::Euclid] Minilib.Math.Rational::Rational a : Std::Mul`

### `impl [a : Minilib.Math.Types::Euclid] Minilib.Math.Rational::Rational a : Std::Neg`

### `impl [a : Minilib.Math.Types::Euclid] Minilib.Math.Rational::Rational a : Std::Sub`

### `impl [a : Minilib.Math.Types::Euclid, a : Std::ToString] Minilib.Math.Rational::Rational a : Std::ToString`

### `impl [a : Minilib.Math.Types::Euclid, a : Minilib.Math.Types::One] Minilib.Math.Rational::Rational a : Std::Zero`

## Values

### `namespace Minilib.Math.Rational::Rational`

#### `make : [a : Minilib.Math.Types::Euclid] a -> a -> Minilib.Math.Rational::Rational a`

`make(num, den)` creates a rational number `(num/den)`.
Aborts if `den` is zero.

#### `rational : [a : Minilib.Math.Types::Euclid] a -> a -> Minilib.Math.Rational::Rational a`

Synonym for `make`.

#### `reduce : [a : Minilib.Math.Types::Euclid] Minilib.Math.Rational::Rational a -> Minilib.Math.Rational::Rational a`

Reduces a rational number.