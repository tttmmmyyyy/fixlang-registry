# `module Minilib.Crypto.AES`

Advanced Encryption Standard (AES)

Implemented from specification of FIPS 197:
https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.197-upd1.pdf
https://doi.org/10.6028/NIST.FIPS.197-upd1

## Types and aliases

### `namespace Minilib.Crypto.AES`

#### `type AES = unbox struct { ...fields... }`

##### field `key_length : Std::I64`

##### field `key : Std::Array Std::U8`

##### field `w : Std::Array Std::U32`

##### field `c01 : Std::U64`

##### field `c23 : Std::U64`

## Traits and aliases

## Trait implementations

## Values

### `namespace Minilib.Crypto.AES::AES`

#### `_add_round_key : Std::Array Std::U32 -> Std::I64 -> Minilib.Crypto.AES::AES -> Minilib.Crypto.AES::AES`

5.1.4 ADDROUNDKEY()

#### `_cipher : Std::Array Std::U8 -> Std::Array Std::U32 -> Minilib.Crypto.AES::AES -> Std::Array Std::U8`

5.1 CIPHER()

#### `_empty : Std::I64 -> Minilib.Crypto.AES::AES`

#### `_get_number_of_rounds : Minilib.Crypto.AES::AES -> Std::I64`

5. Algorithm Specifcations

#### `_get_output : Minilib.Crypto.AES::AES -> Std::Array Std::U8`

#### `_inv_cipher : Std::Array Std::U8 -> Std::Array Std::U32 -> Minilib.Crypto.AES::AES -> Std::Array Std::U8`

5.3 INVCIPHER()

#### `_inv_mix_column : Std::U32 -> Std::I64 -> Std::U32 -> Std::U32`

#### `_inv_mix_columns : Minilib.Crypto.AES::AES -> Minilib.Crypto.AES::AES`

5.3.3 INVMIXCOLUMNS()

#### `_inv_sbox_table : Std::Array Std::U8`

#### `_inv_shift_rows : Minilib.Crypto.AES::AES -> Minilib.Crypto.AES::AES`

5.3.1 INVSHIFTROWS()

#### `_inv_sub_bytes : Minilib.Crypto.AES::AES -> Minilib.Crypto.AES::AES`

5.3.2 INVSUBBYTES()

#### `_key_expansion : Std::Array Std::U8 -> Minilib.Crypto.AES::AES -> Std::Array Std::U32`

5.2 KEYEXPANSION()

#### `_mix_column : Std::U32 -> Std::I64 -> Std::U32 -> Std::U32`

#### `_mix_columns : Minilib.Crypto.AES::AES -> Minilib.Crypto.AES::AES`

5.1.3 MIXCOLUMNS()

#### `_rcon : Std::I64 -> Std::U32`

#### `_rcon_table : Std::Array Std::U8`

#### `_rot_word : Std::U32 -> Std::U32`

#### `_rotr : Std::U8 -> Std::U8 -> Std::U8`

rotate right

#### `_sbox : Std::U8 -> Std::U8`

SBOX

#### `_sbox_table : Std::Array Std::U8`

#### `_set_input : Std::Array Std::U8 -> Minilib.Crypto.AES::AES -> Minilib.Crypto.AES::AES`

#### `_shift_rows : Minilib.Crypto.AES::AES -> Minilib.Crypto.AES::AES`

5.1.2 SHIFTROWS()

#### `_sub_bytes : Minilib.Crypto.AES::AES -> Minilib.Crypto.AES::AES`

5.1.1 SUBBYTES()

#### `_sub_u64 : Std::Array Std::U8 -> Std::U64 -> Std::U64 -> Std::U64 -> Std::U64`

#### `_sub_word : Std::U32 -> Std::U32`

#### `decrypt_block : Std::Array Std::U8 -> Minilib.Crypto.AES::AES -> Std::Array Std::U8`

`aes.decrypt_block(ciphertext)` decrypts a block of ciphertext to a block of plaintext.
`ciphertext` must be a byte array of 128 bits (= 16 bytes).

#### `encrypt_block : Std::Array Std::U8 -> Minilib.Crypto.AES::AES -> Std::Array Std::U8`

`aes.encrypt_block(plaintext)` encrypts a block of plaintext to a block of ciphertext.
`plaintext` must be a byte array of 128 bits (= 16 bytes).

#### `make : Std::Array Std::U8 -> Minilib.Crypto.AES::AES`

`AES::make(key)` creates an AES cipher.
`key` must be a byte array of 128 bits (= 16 bytes), 192 bits (= 24 bytes), or
256 bits (= 32 bytes).

### `namespace Minilib.Crypto.AES::GF8`

#### `_add_gf8 : Std::U8 -> Std::U8 -> Std::U8`

4.1 Addition in GF(2^8)

#### `_inv_gf8 : Std::U8 -> Std::U8`

4.4 Multiplicative Inverses in GF(2^8)

#### `_mul_gf8 : Std::U8 -> Std::U8 -> Std::U8`

4.2 Multiplication in GF(2^8)

#### `_mul_gf8_slow : Std::U8 -> Std::U8 -> Std::U8`

#### `_mul_gf8_table : Std::Array Std::U8`

#### `_pow_gf8 : Std::U8 -> Std::U8 -> Std::U8`

`a._pow_gf8(n)` calculates `a ^ n`.

#### `_xtimes : Std::U8 -> Std::U8`