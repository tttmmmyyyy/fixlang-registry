# `module Minilib.Comonad.IdentityC`

Identity comonad

## Types and aliases

### `namespace Minilib.Comonad.IdentityC`

#### `type IdentityC a = unbox struct { ...fields... }`

Identity comonad

##### field `data : a`

## Traits and aliases

## Trait implementations

### `impl Minilib.Comonad.IdentityC::IdentityC : Minilib.Trait.Comonad::Comonad`

### `impl Minilib.Comonad.IdentityC::IdentityC : Std::Functor`

## Values

### `namespace Minilib.Comonad.IdentityC`

#### `get : Minilib.Comonad.IdentityC::IdentityC a -> a`

Gets a value from an identity comonad.

#### `make : a -> Minilib.Comonad.IdentityC::IdentityC a`

Creates an identity comonad from a value.