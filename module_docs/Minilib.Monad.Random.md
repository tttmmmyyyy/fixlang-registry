# `module Minilib.Monad.Random`

Random Number Generator Monad

## Types and aliases

## Traits and aliases

### `namespace Minilib.Monad.Random`

#### trait `[m : *->*] m : MonadRandomIF`

A trait for a monad that generates random numbers every time.

##### method `random_U64 : m Std::U64`

`random_U64` generates a random integer of U64.

##### method `random_bytes : Std::I64 -> m (Std::Array Std::U8)`

`random_bytes` generates random bytes of specified size.

## Trait implementations

### `impl [rg : Minilib.Trait.Rng::Rng, lf1 : Minilib.Trait.Lifter::Lifter, lf2 : Minilib.Trait.Lifter::Lifter, m : Std::Monad] Minilib.Monad.State::StateT rg m : Minilib.Monad.Random::MonadRandomIF`

An implementation of `MonadRandomIF` for the `StateT` monad.

A state monad `StateT rg m` can be used as a `MonadRandom`,
if the state `rg` implements `Rng` trait, and the target monad `m` is compatible to `RngResult`.
The result type of `Rng` is lifted to the target monad `m` by the lifter.

## Values

### `namespace Minilib.Monad.Random`

#### `random_I64_range : [m : Minilib.Monad.Random::MonadRandom] Std::I64 -> Std::I64 -> m Std::I64`

`random_I64_range(begin, end)` generates a random integer `r`
such that `begin <= r && r < end`.
if `begin >= end`, it panicks.

#### `random_U16 : [m : Minilib.Monad.Random::MonadRandom] m Std::U16`

`random_U16` generates a random integer of U8.

#### `random_U32 : [m : Minilib.Monad.Random::MonadRandom] m Std::U32`

`random_U32` generates a random integer of U32.

#### `random_U8 : [m : Minilib.Monad.Random::MonadRandom] m Std::U8`

`random_U8` generates a random integer of U8.

#### `random_array : [m : Minilib.Monad.Random::MonadRandom] Std::I64 -> m a -> m (Std::Array a)`

`random_array(size, random)` generates a random array of specified size
by performing `random` repeatedly.

#### `shuffle : [m : Minilib.Monad.Random::MonadRandom] Std::Array a -> m (Std::Array a)`

Shuffles an array.

### `namespace Minilib.Monad.Random::MonadRandomIF`

#### `random_U64 : [m : Minilib.Monad.Random::MonadRandomIF] m Std::U64`

`random_U64` generates a random integer of U64.

#### `random_bytes : [m : Minilib.Monad.Random::MonadRandomIF] Std::I64 -> m (Std::Array Std::U8)`

`random_bytes` generates random bytes of specified size.