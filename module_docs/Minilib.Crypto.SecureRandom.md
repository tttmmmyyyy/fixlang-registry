# `module Minilib.Crypto.SecureRandom`

Secure random number generator.

Currently only Linux is supported, because it uses `/dev/urandom` as a secure random source.

## Types and aliases

### `namespace Minilib.Crypto.SecureRandom`

#### `type SecureRandom = unbox struct { ...fields... }`

##### field `data : Std::FFI::Destructor Std::IO::IOHandle`

## Traits and aliases

## Trait implementations

### `impl Minilib.Crypto.SecureRandom::SecureRandom : Minilib.Trait.Rng::Rng`

## Values

### `namespace Minilib.Crypto.SecureRandom`

#### `generate_U64 : Minilib.Crypto.SecureRandom::SecureRandom -> Std::IO::IOFail (Minilib.Crypto.SecureRandom::SecureRandom, Std::U64)`

Generates a random integer of U64.

#### `generate_bytes : Std::I64 -> Minilib.Crypto.SecureRandom::SecureRandom -> Std::IO::IOFail (Minilib.Crypto.SecureRandom::SecureRandom, Std::Array Std::U8)`

Generates a random byte array with specified size.

#### `make : Std::IO::IOFail Minilib.Crypto.SecureRandom::SecureRandom`

Creates a SecureRandom instance.