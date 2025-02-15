# `module Minilib.Monad.Result`

A monad transformer that wraps `m (Result e a)`.

## Types and aliases

### `namespace Minilib.Monad.Result`

#### `type [m : *->*] ResultT e m a = unbox struct { ...fields... }`

A monad transformer that wraps `m (Result e a)`.
This represents an operation result (success or error).
`e` is a type of an error if the operation fails.
`m` is a type of an underlying monad.
`a` is a type of an operation result if operation is successful.

##### field `data : m (Std::Result e a)`

## Traits and aliases

## Trait implementations

### `impl [m : Std::Monad] Minilib.Monad.Result::ResultT Std::String m : Minilib.Monad.Error::MonadErrorIF`

### `impl Minilib.Monad.Result::ResultT e : Minilib.Monad.Trans::MonadTrans`

### `impl [m : Minilib.Monad.IO::MonadIOFail] Minilib.Monad.Result::ResultT e m : Minilib.Monad.IO::MonadIOFailIF`

### `impl [m : Minilib.Monad.IO::MonadIO] Minilib.Monad.Result::ResultT e m : Minilib.Monad.IO::MonadIOIF`

### `impl [m : Std::Functor] Minilib.Monad.Result::ResultT e m : Std::Functor`

### `impl [m : Std::Monad] Minilib.Monad.Result::ResultT e m : Std::Monad`

## Values

### `namespace Minilib.Monad.Result`

#### `result_t : m (Std::Result e a) -> Minilib.Monad.Result::ResultT e m a`

Creates a ResultT monad from an operation result.

#### `run_result_t : Minilib.Monad.Result::ResultT e m a -> m (Std::Result e a)`

Gets the operation result.