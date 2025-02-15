# `module HashMap`

## Types and aliases

### `namespace HashMap`

#### `type HashMap k v = unbox struct { ...fields... }`

##### field `_table : Std::Array (Std::Array (Std::Option (k, v)))`

##### field `_size : Std::I64`

#### `type HashMapIterator = Std::Iterator::FlattenIterator (Std::Iterator::MapIterator Std::Iterator::RangeIterator Std::I64 (Std::Iterator::FlattenIterator (Std::Iterator::MapIterator Std::Iterator::RangeIterator Std::I64 (Std::Option::OptionIterator (Std::Option kv))) (Std::Option::OptionIterator (Std::Option kv)))) (Std::Iterator::FlattenIterator (Std::Iterator::MapIterator Std::Iterator::RangeIterator Std::I64 (Std::Option::OptionIterator (Std::Option kv))) (Std::Option::OptionIterator (Std::Option kv)))`

## Traits and aliases

## Trait implementations

## Values

### `namespace HashMap`

#### `_find_place : [k : Hash::HashKey] k -> HashMap::HashMap k v -> (Std::I64, Std::Option Std::I64)`

Finds the place where an element with a key is stored.
Returns pair of (index in hash table, index in bucket).

#### `_get_pot_geq : Std::I64 -> Std::I64`

Gets a POT (power-of-two) value which is less than or equal to the given value.
This is used for calculating capacity value.

#### `contains_key : [k : Hash::HashKey] k -> HashMap::HashMap k v -> Std::Bool`

Checks whether a hashmap contains a key.

#### `empty : Std::I64 -> HashMap::HashMap k v`

Creates an empty HashMap which is reserved so that it will not rehash until size exceeds the spacified value.

#### `erase : [k : Hash::HashKey] k -> HashMap::HashMap k v -> HashMap::HashMap k v`

Erases an element from a HashMap.

#### `find : [k : Hash::HashKey] k -> HashMap::HashMap k v -> Std::Option v`

Finds an element from a HashMap.

#### `find_or : [k : Hash::HashKey] k -> v -> HashMap::HashMap k v -> v`

Finds an element from a HashMap. If the map doesn't contain the key, it returns the given default value.

#### `get_capacity : HashMap::HashMap k v -> Std::I64`

Gets capacity of a HashMap.

#### `get_size : HashMap::HashMap k v -> Std::I64`

Gets size (number of elements) of a HashMap.

#### `insert : [k : Hash::HashKey] k -> v -> HashMap::HashMap k v -> HashMap::HashMap k v`

Inserts an element into a HashMap.

#### `reserve : [k : Hash::HashKey] Std::I64 -> HashMap::HashMap k v -> HashMap::HashMap k v`

Reserves a HashMap so that it will not rehash until size exceeds the spacified value.

#### `to_iter : HashMap::HashMap k v -> HashMap::HashMapIterator (k, v)`

Converts a HashMap into an iterator.