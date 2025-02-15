# `module Minilib.Trait.Rng`

A trait for Random Number Generator.

## Types and aliases

## Traits and aliases

### `namespace Minilib.Trait.Rng`

#### trait `rg : Rng`

A trait for Random Number Generator.

##### associated type `RngResult rg a`

The result type of `rng_xxx` functions. This should be a monad, for example `Identity a`, `IOFail a` etc.
This result will be lifted by the lifter.

##### associated type `[m : *->*] RngLift rg m a`

A lifter that lifts `RngResult` into a desired monad.
Requirements:
- Implements the `Lifter` trait.
- `LiftFrom` type must be `RngResult rg a`.
- `LiftTo` type must be `m a`.
Typically, this type is set to `LifterImpl (n a) (m a)` where `n a` = `RngResult rg a`.

##### method `rng_U64 : rg -> Minilib.Trait.Rng::Rng::RngResult rg (rg, Std::U64)`

Generates a random integer of U64.

##### method `rng_bytes : Std::I64 -> rg -> Minilib.Trait.Rng::Rng::RngResult rg (rg, Std::Array Std::U8)`

Generates random bytes of specified size.

## Trait implementations

### `impl Random::Random : Minilib.Trait.Rng::Rng`

`Random` implements the `Rng` trait

## Values

### `namespace Minilib.Trait.Rng`

#### `lens_rng : [rg : Minilib.Trait.Rng::Rng, rg2 : Minilib.Trait.Rng::Rng, f : Std::Functor, Minilib.Trait.Rng::Rng::RngResult rg a = f a] ((rg -> Minilib.Functor.Pair::PairLT a f rg) -> rg2 -> Minilib.Functor.Pair::PairLT a f rg2) -> (rg -> f (rg, a)) -> rg2 -> f (rg2, a)`

Converts a `rng_xxx` function using a lens action.
Useful for implementing the `Rng` trait for containers that have a member implementing the `Rng` trait.
For instance, `rng_U64.lens_rng(act_random)` creates an `rng_U64` function that performs the `act_random` action.
Refer to the `Container` type in `monad_random_test.fix` for a detailed example.
Note that this function is similar to `State::lens_state_t`.

### `namespace Minilib.Trait.Rng::Rng`

#### `rng_U64 : [rg : Minilib.Trait.Rng::Rng] rg -> Minilib.Trait.Rng::Rng::RngResult rg (rg, Std::U64)`

Generates a random integer of U64.

#### `rng_bytes : [rg : Minilib.Trait.Rng::Rng] Std::I64 -> rg -> Minilib.Trait.Rng::Rng::RngResult rg (rg, Std::Array Std::U8)`

Generates random bytes of specified size.