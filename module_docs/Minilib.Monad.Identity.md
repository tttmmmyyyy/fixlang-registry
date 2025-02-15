# `module Minilib.Monad.Identity`

Identity monad

## Types and aliases

### `namespace Minilib.Monad.Identity`

#### `type Identity a = unbox struct { ...fields... }`

Identity monad

##### field `data : a`

## Traits and aliases

## Trait implementations

### `impl Minilib.Monad.Identity::Identity : Std::Functor`

### `impl Minilib.Monad.Identity::Identity : Std::Monad`

## Values

### `namespace Minilib.Monad.Identity`

#### `get : Minilib.Monad.Identity::Identity a -> a`

Gets a value from an identity monad.

#### `make : a -> Minilib.Monad.Identity::Identity a`

Creates an identity monad from a value.