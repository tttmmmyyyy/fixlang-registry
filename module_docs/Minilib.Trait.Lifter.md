# `module Minilib.Trait.Lifter`

A trait which converts a value of a type to a value of another type.

## Types and aliases

### `namespace Minilib.Trait.Lifter`

#### `type LifterImpl from to = unbox struct { ...fields... }`

An empty structure for `Lifter` implementation.

## Traits and aliases

### `namespace Minilib.Trait.Lifter`

#### trait `lf : Lifter`

A trait which converts a value of a type to a value of another type.

##### associated type `LiftTo lf`

A type that the `lifter` converts to.

##### associated type `LiftFrom lf`

A type that the `lifter` converts from.

##### method `lifter : lf`

A singleton instance of the lifter.
NOTE: This instance is required to select the implementation of `Lifter` trait.

##### method `lift_from : Minilib.Trait.Lifter::Lifter::LiftFrom lf -> lf -> Minilib.Trait.Lifter::Lifter::LiftTo lf`

Converts a value of type `LiftFrom lf` to a value of type `LiftTo lf`.
NOTE: The second argument `lf` is ignored. It is required to select the implementation of `Lifter` trait.

## Trait implementations

### `impl [m : Std::Monad] Minilib.Trait.Lifter::LifterImpl (Minilib.Monad.Identity::Identity a) (m a) : Minilib.Trait.Lifter::Lifter`

A lifter implementation which lifts `Identity` monad to any monad.

### `impl [m : Minilib.Monad.IO::MonadIO] Minilib.Trait.Lifter::LifterImpl (Std::IO a) (m a) : Minilib.Trait.Lifter::Lifter`

A lifter implementation which lifts `IO` monad to a monad of `MonadIO`.

### `impl [m : Minilib.Monad.IO::MonadIOFail] Minilib.Trait.Lifter::LifterImpl (Std::IO::IOFail a) (m a) : Minilib.Trait.Lifter::Lifter`

A lifter implementation which lifts `IOFail` monad to a monad of `MonadIOFail`.

## Values

### `namespace Minilib.Trait.Lifter::Lifter`

#### `lift_from : [lf : Minilib.Trait.Lifter::Lifter] Minilib.Trait.Lifter::Lifter::LiftFrom lf -> lf -> Minilib.Trait.Lifter::Lifter::LiftTo lf`

Converts a value of type `LiftFrom lf` to a value of type `LiftTo lf`.
NOTE: The second argument `lf` is ignored. It is required to select the implementation of `Lifter` trait.

#### `lifter : [lf : Minilib.Trait.Lifter::Lifter] lf`

A singleton instance of the lifter.
NOTE: This instance is required to select the implementation of `Lifter` trait.