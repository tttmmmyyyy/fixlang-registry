# `module Minilib.Math.BigInt`

Arbitrary-precision integer.

## Types and aliases

### `namespace Minilib.Math.BigInt`

#### `type BigInt = unbox struct { ...fields... }`

Arbitrary-precision integer.

##### field `sign : Std::I64`

##### field `nat : Std::Array Std::U32`

## Traits and aliases

## Trait implementations

### `impl Minilib.Math.BigInt::BigInt : Minilib.Math.Types::DivMod`

`divmod(a,b)` returns `(a/b, a%b)`.
NOTE: -8 / 3 == -2 and -8 % 3 == -2, as with the Fix language.

### `impl Minilib.Math.BigInt::BigInt : Minilib.Math.Types::One`

### `impl Minilib.Math.BigInt::BigInt : Std::Add`

### `impl Minilib.Math.BigInt::BigInt : Std::Div`

NOTE: -8 / 3 == -2, as with the Fix language.

### `impl Minilib.Math.BigInt::BigInt : Std::Eq`

Checks two BigInts are equal.

### `impl Minilib.Math.BigInt::BigInt : Std::FromBytes`

### `impl Minilib.Math.BigInt::BigInt : Std::FromString`

Converts BigInt from a decimal string.

### `impl Minilib.Math.BigInt::BigInt : Std::LessThan`

Compares two BigInts.

### `impl Minilib.Math.BigInt::BigInt : Std::LessThanOrEq`

Compares two BigInts.

### `impl Minilib.Math.BigInt::BigInt : Std::Mul`

### `impl Minilib.Math.BigInt::BigInt : Std::Neg`

### `impl Minilib.Math.BigInt::BigInt : Std::Rem`

NOTE: -8 % 3 == -2, as with the Fix language.

### `impl Minilib.Math.BigInt::BigInt : Std::Sub`

### `impl Minilib.Math.BigInt::BigInt : Std::ToBytes`

NOTE: Unneeded zeros might be placed at the beginning

### `impl Minilib.Math.BigInt::BigInt : Std::ToString`

Converts BigInt to a decimal string.

### `impl Minilib.Math.BigInt::BigInt : Std::Zero`

## Values

### `namespace Minilib.Math.BigInt`

#### `_bitand_I64 : Std::I64 -> Minilib.Math.BigInt::BigInt -> Std::I64`

`a._bitand_I64(i64)` returns bitwise-AND of `a` and `i64`.
`i64` must be a positive number and less than BigNat::_base.

#### `abs : Minilib.Math.BigInt::BigInt -> Minilib.Math.BigInt::BigInt`

`a.abs` returns the absolute value of `a`.

#### `bit_length : Minilib.Math.BigInt::BigInt -> Std::U64`

Returns the bit length of `a.@nat`, ie. one plus the bit position of most significant `1`.
Returns 0 if `a` is zero.

#### `cmp : Minilib.Math.BigInt::BigInt -> Minilib.Math.BigInt::BigInt -> Std::I64`

`BigInt::cmp(a,b)` returns 1 if `a > b`, -1 if `a < b`, 0 if `a == b`.

#### `divmod_by_two : Minilib.Math.BigInt::BigInt -> (Minilib.Math.BigInt::BigInt, Minilib.Math.BigInt::BigInt)`

`BigInt::divmod_by_two(a)` returns `(a/2, a%2)`.

#### `from_I64 : Std::I64 -> Minilib.Math.BigInt::BigInt`

`BigInt::from_I64(i64)` creates new BigInt object from `i64`.

#### `from_U64 : Std::U64 -> Minilib.Math.BigInt::BigInt`

`BigInt::from_U64(u64)` creates new BigInt object from `u64`.

#### `generate_bigint : [m : Minilib.Monad.Random::MonadRandom] Std::I64 -> m Minilib.Math.BigInt::BigInt`

`generate_bigint(bit_length)` generates a random BigInt of the specified bit length.

#### `generate_bigint_range : [m : Minilib.Monad.Random::MonadRandom] Minilib.Math.BigInt::BigInt -> Minilib.Math.BigInt::BigInt -> m Minilib.Math.BigInt::BigInt`

`generate_bigint_range(begin, end)` generates a random BigInt `r` such that `begin <= r && r < end`.

#### `is_even : Minilib.Math.BigInt::BigInt -> Std::Bool`

`a.is_even` returns true iff `a` is an even number.

#### `is_negative : Minilib.Math.BigInt::BigInt -> Std::Bool`

`a.is_negative` returns true iff `a` is a negative number.

#### `is_odd : Minilib.Math.BigInt::BigInt -> Std::Bool`

`a.is_odd` returns true iff `a` is an odd number.

#### `is_positive : Minilib.Math.BigInt::BigInt -> Std::Bool`

`a.is_positive` returns true iff `a` is a positive number.

#### `is_zero : Minilib.Math.BigInt::BigInt -> Std::Bool`

`a.is_zero` returns true iff `a` is zero.

#### `make : Std::I64 -> Std::Array Std::U32 -> Minilib.Math.BigInt::BigInt`

`BigInt::make(sign, nat)` creates new BigInt object.

#### `repeat_by_BigInt : (a -> a -> a) -> a -> a -> Minilib.Math.BigInt::BigInt -> a`

`repeat_by_BigInt(op, x, a, n)` calculates `x.op(a).op(a)...` for `n` times.
`op` is an associative binary operation.

#### `shift_left : Std::U64 -> Minilib.Math.BigInt::BigInt -> Minilib.Math.BigInt::BigInt`

Shifts `@nat` to left. NOTE `@sign` does not affect at all.

#### `shift_right : Std::U64 -> Minilib.Math.BigInt::BigInt -> Minilib.Math.BigInt::BigInt`

Shifts `@nat` to right. NOTE `@sign` does not affect at all.

#### `to_I64 : Minilib.Math.BigInt::BigInt -> Std::I64`

Converts BigInt to I64. If overflow, it produces unexpected result.

#### `two : Minilib.Math.BigInt::BigInt`

BigInt constant representing 2.