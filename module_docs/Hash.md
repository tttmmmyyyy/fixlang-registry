# `module Hash`

Provides the `Hash` trait and related traits, and basic hashing functions.

## Types and aliases

## Traits and aliases

### `namespace Hash`

#### trait `a : Hash`

Hashable types.

##### method `hash : a -> Std::U64`

## Trait implementations

### `impl [a : Hash::Hash, b : Hash::Hash] (a, b) : Hash::Hash`

### `impl [a : Hash::Hash] Std::Array a : Hash::Hash`

### `impl Std::I64 : Hash::Hash`

### `impl Std::String : Hash::Hash`

### `impl Std::U64 : Hash::Hash`

### `impl Std::U8 : Hash::Hash`

## Values

### `namespace Hash`

#### `combine_hash : Std::U64 -> Std::U64 -> Std::U64`

Combines two hashes.

Using method described in https://stackoverflow.com/questions/5889238/why-is-xor-the-default-way-to-combine-hashes.

### `namespace Hash::Hash`

#### `hash : [a : Hash::Hash] a -> Std::U64`