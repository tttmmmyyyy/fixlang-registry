# `module Minilib.Functor.Pair`

## Types and aliases

### `namespace Minilib.Functor.Pair`

#### `type PairL r l = unbox struct { ...fields... }`

A functor on the left component. This is a swapped version of `Tuple2`.

##### field `data : (l, r)`

#### `type [f : *->*] PairLT r f l = unbox struct { ...fields... }`

A functor on the left component with an underlying functor.

##### field `data : f (l, r)`

#### `type PairR l r = unbox struct { ...fields... }`

A functor on the right component. This is same as `Tuple2`.

##### field `data : (l, r)`

#### `type [f : *->*] PairRT l f r = unbox struct { ...fields... }`

A functor on the right component with an underlying functor.

##### field `data : f (l, r)`

## Traits and aliases

## Trait implementations

### `impl Minilib.Functor.Pair::PairL r : Std::Functor`

### `impl [f : Std::Functor] Minilib.Functor.Pair::PairLT r f : Std::Functor`

### `impl Minilib.Functor.Pair::PairR l : Std::Functor`

### `impl [f : Std::Functor] Minilib.Functor.Pair::PairRT l f : Std::Functor`

## Values

### `namespace Minilib.Functor.Pair::PairL`

#### `get : Minilib.Functor.Pair::PairL r l -> (l, r)`

#### `make : (l, r) -> Minilib.Functor.Pair::PairL r l`

### `namespace Minilib.Functor.Pair::PairLT`

#### `get : Minilib.Functor.Pair::PairLT r f l -> f (l, r)`

#### `make : f (l, r) -> Minilib.Functor.Pair::PairLT r f l`

### `namespace Minilib.Functor.Pair::PairR`

#### `get : Minilib.Functor.Pair::PairR l r -> (l, r)`

#### `make : (l, r) -> Minilib.Functor.Pair::PairR l r`

### `namespace Minilib.Functor.Pair::PairRT`

#### `get : Minilib.Functor.Pair::PairRT l f r -> f (l, r)`

#### `make : f (l, r) -> Minilib.Functor.Pair::PairRT l f r`