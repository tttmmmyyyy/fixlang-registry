# `module Minilib.Encoding.Json`

Definition of the structure of a JSON value.

## Types and aliases

### `namespace Minilib.Encoding.Json`

#### `type Json = box union { ...variants... }`

A structure representing a JSON value.

##### variant `null : ()`

##### variant `bool : Std::Bool`

##### variant `number : Std::F64`

##### variant `string : Std::String`

##### variant `object : Minilib.Collection.OrderedMap::OrderedMap Std::String Minilib.Encoding.Json::Json`

##### variant `array : Std::Array Minilib.Encoding.Json::Json`

## Traits and aliases

## Trait implementations

### `impl Minilib.Encoding.Json::Json : Std::Eq`

Checks whether two JSON values are equal.

### `impl Minilib.Encoding.Json::Json : Std::ToString`

## Values

### `namespace Minilib.Encoding.Json`

#### `to_object : Std::Array (Std::String, Minilib.Encoding.Json::Json) -> Minilib.Encoding.Json::Json`

Converts an array of keys and values to a JSON object.