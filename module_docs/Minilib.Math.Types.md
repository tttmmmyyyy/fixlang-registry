# `module Minilib.Math.Types`

Type definitions for mathematical concepts, for example AdditiveGroup, Ring, Field.

## Types and aliases

## Traits and aliases

### `namespace Minilib.Math.Types`

#### trait `a : DivMod`

A trait for division-with-remainder.

##### method `divmod : a -> a -> (a, a)`

`divmod(a, b)` returns `(a/b, a%b)`.

#### trait `a : One`

A trait that represents a multiplicative unit.

##### method `one : a`

## Trait implementations

### `impl Std::F32 : Minilib.Math.Types::One`

### `impl Std::F64 : Minilib.Math.Types::One`

### `impl Std::I64 : Minilib.Math.Types::DivMod`

### `impl Std::I64 : Minilib.Math.Types::One`

### `impl Std::U64 : Minilib.Math.Types::DivMod`

## Values

### `namespace Minilib.Math.Types::DivMod`

#### `divmod : [a : Minilib.Math.Types::DivMod] a -> a -> (a, a)`

`divmod(a, b)` returns `(a/b, a%b)`.

### `namespace Minilib.Math.Types::One`

#### `one : [a : Minilib.Math.Types::One] a`