# `module Minilib.Monad.Error`

Definition of `MonadErrorIF` trait which can report errors.

## Types and aliases

## Traits and aliases

### `namespace Minilib.Monad.Error`

#### trait `[m : *->*] m : MonadErrorIF`

A trait for monads which can report errors.

##### method `error : Std::String -> m a`

`error(e)` throws an error.

##### method `catch : (Std::String -> m a) -> m a -> m a`

`ma.catch(handler)` catches any error that is thrown during the computation of `ma`.

## Trait implementations

### `impl Std::IO::IOFail : Minilib.Monad.Error::MonadErrorIF`

### `impl Std::Result Std::String : Minilib.Monad.Error::MonadErrorIF`

## Values

### `namespace Minilib.Monad.Error`

#### `from_result_t : [m : Minilib.Monad.Error::MonadError] Std::Result Std::ErrMsg a -> m a`

Synonym of `lift_result`.

#### `lift_result : [m : Minilib.Monad.Error::MonadError] Std::Result Std::ErrMsg a -> m a`

Lifts an operation result to a monad.

#### `to_result_t : [m : Minilib.Monad.Error::MonadError] m a -> m (Std::Result Std::ErrMsg a)`

Converts to an operation result.

### `namespace Minilib.Monad.Error::MonadErrorIF`

#### `catch : [m : Minilib.Monad.Error::MonadErrorIF] (Std::ErrMsg -> m a) -> m a -> m a`

`ma.catch(handler)` catches any error that is thrown during the computation of `ma`.

#### `error : [m : Minilib.Monad.Error::MonadErrorIF] Std::ErrMsg -> m a`

`error(e)` throws an error.