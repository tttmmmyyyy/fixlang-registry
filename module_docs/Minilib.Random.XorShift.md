# `module Minilib.Random.XorShift`

A random number generator which uses Xorshift algorithm.

For details, see: [Wikipedia: Xorshift](https://en.wikipedia.org/wiki/Xorshift)

## Types and aliases

### `namespace Minilib.Random.XorShift`

#### `type XorShift = unbox struct { ...fields... }`

A random number generator which uses Xorshift algorithm.

##### field `data : Std::U64`

## Traits and aliases

## Trait implementations

### `impl Minilib.Random.XorShift::XorShift : Minilib.Trait.Rng::Rng`

## Values

### `namespace Minilib.Random.XorShift`

#### `init_by_seed : Std::U64 -> Minilib.Random.XorShift::XorShift`

Initializes a random number generator by a specified seed.