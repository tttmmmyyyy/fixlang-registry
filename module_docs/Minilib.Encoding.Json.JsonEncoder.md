# `module Minilib.Encoding.Json.JsonEncoder`

Encodes a JSON value to a string.

## Types and aliases

### `namespace Minilib.Encoding.Json.JsonEncoder`

#### `type EncodeParam = unbox struct { ...fields... }`

##### field `space : Std::String`

##### field `newline : Std::String`

##### field `indent : Std::String`

##### field `indent_incr : Std::String`

##### field `number_prec : Std::U8`

## Traits and aliases

## Trait implementations

## Values

### `namespace Minilib.Encoding.Json.JsonEncoder`

#### `_encode : Minilib.Encoding.Json.JsonEncoder::EncodeParam -> Std::Array Std::String -> Minilib.Encoding.Json::Json -> Std::Array Std::String`

#### `_encode_array : Minilib.Encoding.Json.JsonEncoder::EncodeParam -> Std::Array Std::String -> Std::Array Minilib.Encoding.Json::Json -> Std::Array Std::String`

#### `_encode_number : Minilib.Encoding.Json.JsonEncoder::EncodeParam -> Std::F64 -> Std::String`

#### `_encode_object : Minilib.Encoding.Json.JsonEncoder::EncodeParam -> Std::Array Std::String -> Minilib.Collection.OrderedMap::OrderedMap Std::String Minilib.Encoding.Json::Json -> Std::Array Std::String`

#### `_encode_string : Std::String -> Std::String`

#### `_escape_table : Std::Array Std::U8`

#### `_hex_table : Std::Array Std::U8`

#### `encode : Minilib.Encoding.Json::Json -> Std::String`

Encodes JSON and converts it to a string.

#### `encode_pretty : Minilib.Encoding.Json::Json -> Std::String`

Encodes JSON and converts it to a string. (pretty-printing)

#### `encode_with_param : Minilib.Encoding.Json.JsonEncoder::EncodeParam -> Minilib.Encoding.Json::Json -> Std::String`

Encodes JSON and converts it to a string using the specified parameter.

### `namespace Minilib.Encoding.Json.JsonEncoder::EncodeParam`

#### `default : Minilib.Encoding.Json.JsonEncoder::EncodeParam`

#### `increment_indent : Minilib.Encoding.Json.JsonEncoder::EncodeParam -> Minilib.Encoding.Json.JsonEncoder::EncodeParam`

#### `pretty_print : Minilib.Encoding.Json.JsonEncoder::EncodeParam`