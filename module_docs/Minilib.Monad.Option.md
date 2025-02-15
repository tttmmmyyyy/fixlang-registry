# `module Minilib.Monad.Option`

A monad transformer that wraps `m (Option a)`.

## Types and aliases

### `namespace Minilib.Monad.Option`

#### `type [m : *->*] OptionT m a = unbox struct { ...fields... }`

A monad transformer that wraps `m (Option a)`.
This represents an optional value which may or may not exist.
`m` is a type of an underlying monad.
`a` is a type of a value.

##### field `data : m (Std::Option a)`

## Traits and aliases

## Trait implementations

### `impl Minilib.Monad.Option::OptionT : Minilib.Monad.Trans::MonadTrans`

### `impl [m : Minilib.Monad.Error::MonadError] Minilib.Monad.Option::OptionT m : Minilib.Monad.Error::MonadErrorIF`

### `impl [m : Minilib.Monad.IO::MonadIOFail] Minilib.Monad.Option::OptionT m : Minilib.Monad.IO::MonadIOFailIF`

### `impl [m : Minilib.Monad.IO::MonadIO] Minilib.Monad.Option::OptionT m : Minilib.Monad.IO::MonadIOIF`

### `impl [m : Std::Functor] Minilib.Monad.Option::OptionT m : Std::Functor`

### `impl [m : Std::Monad] Minilib.Monad.Option::OptionT m : Std::Monad`

## Values

### `namespace Minilib.Monad.Option`

#### `lift_option : [m : Std::Monad] Std::Option a -> Minilib.Monad.Option::OptionT m a`

Lifts an optional value to an `OptionT` monad.

#### `option_t : m (Std::Option a) -> Minilib.Monad.Option::OptionT m a`

Creates an OptionT monad from an optional value.

#### `run_option_t : Minilib.Monad.Option::OptionT m a -> m (Std::Option a)`

Gets the optional value.