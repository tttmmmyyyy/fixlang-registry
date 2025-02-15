# `module Minilib.Media.Image`

Basic image definitions.

## Types and aliases

### `namespace Minilib.Media.Image`

#### `type Image = unbox struct { ...fields... }`

##### field `width : Std::I64`

##### field `height : Std::I64`

##### field `channels : Std::I64`

##### field `format : Std::String`

##### field `data : Std::Array Std::U8`

## Traits and aliases

## Trait implementations

## Values

### `namespace Minilib.Media.Image`

#### `calc_channels_by_format : Std::String -> Std::I64`

#### `calc_index : Std::I64 -> Std::I64 -> Std::I64 -> Minilib.Media.Image::Image -> Std::I64`

#### `get : Std::I64 -> Minilib.Media.Image::Image -> Std::U8`

#### `get_rgb : Std::I64 -> Minilib.Media.Image::Image -> (Std::U8, Std::U8, Std::U8)`

#### `make : Std::I64 -> Std::I64 -> Std::String -> Minilib.Media.Image::Image`

#### `set : Std::I64 -> Std::U8 -> Minilib.Media.Image::Image -> Minilib.Media.Image::Image`

#### `set_rgb : Std::I64 -> (Std::U8, Std::U8, Std::U8) -> Minilib.Media.Image::Image -> Minilib.Media.Image::Image`