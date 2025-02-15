# `module Minilib.Monad.FreeRandom`

Free Random Monad.

## Types and aliases

### `namespace Minilib.Monad.FreeRandom`

#### `type FreeRandom a = box union { ...variants... }`

Free Random Monad.

This type may be used in a situation such as polymorphic types cannot be used,
for example an interface of an API.

##### variant `fr_pure : a`

##### variant `fr_u64 : Std::U64 -> Minilib.Monad.FreeRandom::FreeRandom a`

##### variant `fr_bytes : (Std::I64, Std::Array Std::U8 -> Minilib.Monad.FreeRandom::FreeRandom a)`

## Traits and aliases

## Trait implementations

### `impl Minilib.Monad.FreeRandom::FreeRandom : Minilib.Monad.Random::MonadRandomIF`

### `impl Minilib.Monad.FreeRandom::FreeRandom : Std::Functor`

### `impl Minilib.Monad.FreeRandom::FreeRandom : Std::Monad`

## Values

### `namespace Minilib.Monad.FreeRandom::FreeRandom`

#### `interpret : [m : Minilib.Monad.Random::MonadRandom] Minilib.Monad.FreeRandom::FreeRandom a -> m a`