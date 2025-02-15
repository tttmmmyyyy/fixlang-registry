# `module Minilib.Monad.Writer`

Writer monad.

For details, see [blog post: The Reader and Writer Monads and Comonads](https://www.olivierverdier.com/posts/2014/12/31/reader-writer-monad-comonad/).

## Types and aliases

### `namespace Minilib.Monad.Writer`

#### `type Writer = Minilib.Monad.Writer::WriterT e Minilib.Monad.Identity::Identity`

#### `type [m : *->*] WriterT e m a = unbox struct { ...fields... }`

Writer monad wraps a pair of an environment and a value.
`e` is a type of an environment.
`m` is a type of an underlyind monad.
`a` is a type of a value.

##### field `data : m (e, a)`

## Traits and aliases

### `namespace Minilib.Monad.Writer`

#### trait `[wm : *->*] wm : MonadWriterIF`

A trait for generic writer monads that manages the internal environment.

##### associated type `EnvType wm`

The type of the environment.

##### method `tell : Minilib.Monad.Writer::MonadWriterIF::EnvType wm -> wm ()`

Tells specified value to the internal environment.

##### method `listen : wm a -> wm (Minilib.Monad.Writer::MonadWriterIF::EnvType wm, a)`

Listens the internal environment.

##### method `pass : wm (Minilib.Monad.Writer::MonadWriterIF::EnvType wm -> Minilib.Monad.Writer::MonadWriterIF::EnvType wm, a) -> wm a`

Provide a writer transformer which changes internals of the written object.

## Trait implementations

### `impl [e : Minilib.Trait.Monoid::Monoid] Minilib.Monad.Writer::WriterT e : Minilib.Monad.Trans::MonadTrans`

### `impl [e : Minilib.Trait.Monoid::Monoid, m : Minilib.Monad.Error::MonadError] Minilib.Monad.Writer::WriterT e m : Minilib.Monad.Error::MonadErrorIF`

### `impl [m : Minilib.Monad.IO::MonadIOFail, e : Minilib.Trait.Monoid::Monoid] Minilib.Monad.Writer::WriterT e m : Minilib.Monad.IO::MonadIOFailIF`

### `impl [m : Minilib.Monad.IO::MonadIO, e : Minilib.Trait.Monoid::Monoid] Minilib.Monad.Writer::WriterT e m : Minilib.Monad.IO::MonadIOIF`

### `impl [e : Minilib.Trait.Monoid::Monoid, m : Std::Monad] Minilib.Monad.Writer::WriterT e m : Minilib.Monad.Writer::MonadWriterIF`

### `impl [m : Std::Monad] Minilib.Monad.Writer::WriterT e m : Std::Functor`

### `impl [e : Minilib.Trait.Monoid::Monoid, m : Std::Monad] Minilib.Monad.Writer::WriterT e m : Std::Monad`

## Values

### `namespace Minilib.Monad.Writer`

#### `get_env : Minilib.Monad.Writer::Writer e a -> e`

Gets the envirionment from a writer monad.

#### `get_env_t : [m : Std::Monad] Minilib.Monad.Writer::WriterT e m a -> m e`

Gets the envirionment from a generic writer monad.

#### `get_value : Minilib.Monad.Writer::Writer e a -> a`

Gets the value from a writer monad.

#### `get_value_t : [m : Std::Monad] Minilib.Monad.Writer::WriterT e m a -> m a`

Gets the value from a generic writer monad.

#### `map_writer_t : [m : Std::Monad, n : Std::Monad] (m (e, a) -> n (e1, b)) -> Minilib.Monad.Writer::WriterT e m a -> Minilib.Monad.Writer::WriterT e1 n b`

Maps an underlying monad and a value using the specified function.

#### `run_writer : Minilib.Monad.Writer::Writer e a -> (e, a)`

Runs a writer monad to get an enviroment and a value.

#### `run_writer_t : [m : Std::Monad] Minilib.Monad.Writer::WriterT e m a -> m (e, a)`

Runs a generic writer monad to get an enviroment and a value.

#### `write : [e : Minilib.Trait.Monoid::Monoid, m : Std::Monad] e -> Minilib.Monad.Writer::WriterT e m ()`

Creates a writer monad that appends to the environment.

#### `writer : e -> a -> Minilib.Monad.Writer::Writer e a`

Creates a writer monad from an enviroment and a value.

#### `writer_t : [m : Std::Monad] m (e, a) -> Minilib.Monad.Writer::WriterT e m a`

Creates a generic writer monad from an enviroment and a value.

### `namespace Minilib.Monad.Writer::MonadWriterIF`

#### `listen : [wm : Minilib.Monad.Writer::MonadWriterIF] wm a -> wm (Minilib.Monad.Writer::MonadWriterIF::EnvType wm, a)`

Listens the internal environment.

#### `pass : [wm : Minilib.Monad.Writer::MonadWriterIF] wm (Minilib.Monad.Writer::MonadWriterIF::EnvType wm -> Minilib.Monad.Writer::MonadWriterIF::EnvType wm, a) -> wm a`

Provide a writer transformer which changes internals of the written object.

#### `tell : [wm : Minilib.Monad.Writer::MonadWriterIF] Minilib.Monad.Writer::MonadWriterIF::EnvType wm -> wm ()`

Tells specified value to the internal environment.