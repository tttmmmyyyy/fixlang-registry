# `module Minilib.Encoding.Binary`

Binary utility, such as:
- Byte order
- Byte buffer

## Types and aliases

### `namespace Minilib.Encoding.Binary`

#### `type ByteBuffer = unbox struct { ...fields... }`

A type of byte buffer that supports encoding values to/decoding values from memory.

##### field `array : Std::Array Std::U8`

##### field `byte_order : Minilib.Encoding.Binary::ByteOrder`

##### field `position : Std::I64`

#### `type ByteOrder = unbox union { ...variants... }`

A union type of byte order (endianness).
For example, `0x12345678_U32` is encoded as `[0x78_U8, 0x56_U8, 0x34_U8, 0x12_U8]` in little endian,
`[0x12_U8, 0x34_U8, 0x56_U8, 0x78_U8]` in big endian.

##### variant `little_endian : ()`

##### variant `big_endian : ()`

## Traits and aliases

### `namespace Minilib.Encoding.Binary`

#### trait `a : Marshal`

Trait for a type that supports marshalling (encoding) a value to a byte buffer.
For details, see https://en.wikipedia.org/wiki/Marshalling_(computer_science).

##### method `marshal : a -> Minilib.Encoding.Binary::ByteBuffer -> Minilib.Encoding.Binary::ByteBuffer`

Encodes a value to the byte buffer.

#### trait `a : Unmarshal`

Trait for a type that supports unmarshalling (decoding) a value from a byte buffer.
For details, see https://en.wikipedia.org/wiki/Marshalling_(computer_science).

##### method `unmarshal : Minilib.Encoding.Binary::ByteBuffer -> Std::Result Std::String (a, Minilib.Encoding.Binary::ByteBuffer)`

Decodes a value from the byte buffer.

## Trait implementations

### `impl Std::U16 : Minilib.Encoding.Binary::Marshal`

### `impl Std::U16 : Minilib.Encoding.Binary::Unmarshal`

### `impl Std::U32 : Minilib.Encoding.Binary::Marshal`

### `impl Std::U32 : Minilib.Encoding.Binary::Unmarshal`

### `impl Std::U64 : Minilib.Encoding.Binary::Marshal`

### `impl Std::U64 : Minilib.Encoding.Binary::Unmarshal`

### `impl Std::U8 : Minilib.Encoding.Binary::Marshal`

### `impl Std::U8 : Minilib.Encoding.Binary::Unmarshal`

## Values

### `namespace Minilib.Encoding.Binary`

#### `get_u16_be : Std::I64 -> Std::Array Std::U8 -> Std::U16`

Decodes U16 from `array` at position `i` with big endian.

#### `get_u16_le : Std::I64 -> Std::Array Std::U8 -> Std::U16`

Decodes U16 from `array` at position `i` with little endian.

#### `get_u32_be : Std::I64 -> Std::Array Std::U8 -> Std::U32`

Decodes U32 from `array` at position `i` with big endian.

#### `get_u32_le : Std::I64 -> Std::Array Std::U8 -> Std::U32`

Decodes U32 from `array` at position `i` with little endian.

#### `get_u64_be : Std::I64 -> Std::Array Std::U8 -> Std::U64`

Decodes U64 from `array` at position `i` with big endian.

#### `get_u64_le : Std::I64 -> Std::Array Std::U8 -> Std::U64`

Decodes U64 from `array` at position `i` with little endian.

#### `get_u8_be : Std::I64 -> Std::Array Std::U8 -> Std::U8`

Decodes U8 from `array` at position `i` with big endian.

#### `get_u8_le : Std::I64 -> Std::Array Std::U8 -> Std::U8`

Decodes U8 from `array` at position `i` with little endian.

#### `set_u16_be : Std::I64 -> Std::U16 -> Std::Array Std::U8 -> Std::Array Std::U8`

Encodes U16 into `array` at position `i` with big endian.

#### `set_u16_le : Std::I64 -> Std::U16 -> Std::Array Std::U8 -> Std::Array Std::U8`

Encodes U16 into `array` at position `i` with little endian.

#### `set_u32_be : Std::I64 -> Std::U32 -> Std::Array Std::U8 -> Std::Array Std::U8`

Encodes U32 into `array` at position `i` with big endian.

#### `set_u32_le : Std::I64 -> Std::U32 -> Std::Array Std::U8 -> Std::Array Std::U8`

Encodes U32 into `array` at position `i` with little endian.

#### `set_u64_be : Std::I64 -> Std::U64 -> Std::Array Std::U8 -> Std::Array Std::U8`

Encodes U64 into `array` at position `i` with big endian.

#### `set_u64_le : Std::I64 -> Std::U64 -> Std::Array Std::U8 -> Std::Array Std::U8`

Encodes U64 into `array` at position `i` with little endian.

#### `set_u8_be : Std::I64 -> Std::U8 -> Std::Array Std::U8 -> Std::Array Std::U8`

Encodes U8 into `array` at position `i` with big endian.

#### `set_u8_le : Std::I64 -> Std::U8 -> Std::Array Std::U8 -> Std::Array Std::U8`

Encodes U8 into `array` at position `i` with little endian.

### `namespace Minilib.Encoding.Binary::ByteBuffer`

#### `_marshal : (Std::I64 -> a -> Minilib.Encoding.Binary::ByteBuffer -> Minilib.Encoding.Binary::ByteBuffer) -> Std::I64 -> a -> Minilib.Encoding.Binary::ByteBuffer -> Minilib.Encoding.Binary::ByteBuffer`

(Internal function for `Marshal::marshal`)

#### `_unmarshal : (Std::I64 -> Minilib.Encoding.Binary::ByteBuffer -> a) -> Std::I64 -> Minilib.Encoding.Binary::ByteBuffer -> Std::Result Std::ErrMsg (a, Minilib.Encoding.Binary::ByteBuffer)`

(Internal function for `Unmarshal::unmarshal`)

#### `empty : Std::I64 -> Minilib.Encoding.Binary::ByteOrder -> Minilib.Encoding.Binary::ByteBuffer`

`ByteBuffer::empty(capacity, byte_order)` creates new byte buffer such that:
- The internal byte array is an empty array with capacity `capacity`
- The byte order is `byte_order`

#### `ensure_size : Std::I64 -> Minilib.Encoding.Binary::ByteBuffer -> Minilib.Encoding.Binary::ByteBuffer`

`buf.ensure_size(req_size)` ensures that the size of the byte buffer is at least `req_size`.
If not, appends zeros at the end of the byte buffer.

#### `fill : Std::I64 -> Std::U8 -> Minilib.Encoding.Binary::ByteOrder -> Minilib.Encoding.Binary::ByteBuffer`

`ByteBuffer::fill(size, value, byte_order)` creates new byte buffer such that:
- The internal byte array is initialized by size `size` and filled with `value`
- The byte order is `byte_order`

#### `from_u32_array : Std::Array Std::U32 -> Minilib.Encoding.Binary::ByteOrder -> Minilib.Encoding.Binary::ByteBuffer`

#### `get_bytes : Minilib.Encoding.Binary::ByteBuffer -> Std::Array Std::U8`

Gets the internal byte array.

#### `get_position : Minilib.Encoding.Binary::ByteBuffer -> Std::I64`

Gets the read/write position.

#### `get_size : Minilib.Encoding.Binary::ByteBuffer -> Std::I64`

Gets the size of internal byte array.

#### `get_u16 : Std::I64 -> Minilib.Encoding.Binary::ByteBuffer -> Std::U16`

Decodes U16 from the byte buffer at position `i`.

#### `get_u32 : Std::I64 -> Minilib.Encoding.Binary::ByteBuffer -> Std::U32`

Decodes U32 from the byte buffer at position `i`.

#### `get_u64 : Std::I64 -> Minilib.Encoding.Binary::ByteBuffer -> Std::U64`

Decodes U64 from the byte buffer at position `i`.

#### `get_u8 : Std::I64 -> Minilib.Encoding.Binary::ByteBuffer -> Std::U8`

Decodes U8 from the byte buffer at position `i`.

#### `make : Std::Array Std::U8 -> Minilib.Encoding.Binary::ByteOrder -> Minilib.Encoding.Binary::ByteBuffer`

`ByteBuffer::make(array, byte_order)` creates new byte buffer such that:
- The internal byte array is `array`
- The byte order is `byte_order`

#### `set_u16 : Std::I64 -> Std::U16 -> Minilib.Encoding.Binary::ByteBuffer -> Minilib.Encoding.Binary::ByteBuffer`

Encodes U16 into the byte buffer at position `i`.

#### `set_u32 : Std::I64 -> Std::U32 -> Minilib.Encoding.Binary::ByteBuffer -> Minilib.Encoding.Binary::ByteBuffer`

Encodes U32 into the byte buffer at position `i`.

#### `set_u64 : Std::I64 -> Std::U64 -> Minilib.Encoding.Binary::ByteBuffer -> Minilib.Encoding.Binary::ByteBuffer`

Encodes U64 into the byte buffer at position `i`.

#### `set_u8 : Std::I64 -> Std::U8 -> Minilib.Encoding.Binary::ByteBuffer -> Minilib.Encoding.Binary::ByteBuffer`

Encodes U8 into the byte buffer at position `i`.

#### `to_u32_array : Minilib.Encoding.Binary::ByteBuffer -> Std::Array Std::U32`

#### `to_u8_array : Minilib.Encoding.Binary::ByteBuffer -> Std::Array Std::U8`

### `namespace Minilib.Encoding.Binary::Marshal`

#### `marshal : [a : Minilib.Encoding.Binary::Marshal] a -> Minilib.Encoding.Binary::ByteBuffer -> Minilib.Encoding.Binary::ByteBuffer`

Encodes a value to the byte buffer.

### `namespace Minilib.Encoding.Binary::Unmarshal`

#### `unmarshal : [a : Minilib.Encoding.Binary::Unmarshal] Minilib.Encoding.Binary::ByteBuffer -> Std::Result Std::ErrMsg (a, Minilib.Encoding.Binary::ByteBuffer)`

Decodes a value from the byte buffer.