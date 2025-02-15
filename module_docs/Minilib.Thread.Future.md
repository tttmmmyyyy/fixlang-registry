# `module Minilib.Thread.Future`

A computation that is performed in a TaskPool in parallel.

## Types and aliases

### `namespace Minilib.Thread.Future`

#### `type Future a = unbox struct { ...fields... }`

A computation that is performed in a TaskPool in parallel.

##### field `var_state : AsyncTask::Var::Var Minilib.Thread.Future::FutureState`

##### field `var_result : AsyncTask::Var::Var (Std::Option a)`

#### `type FutureState = unbox union { ...variants... }`

A state of a future.

##### variant `pending : ()`

##### variant `running : ()`

##### variant `completed : ()`

##### variant `canceled : ()`

#### `type FutureToken = unbox struct { ...fields... }`

[nofixdoc]
A token of a future for the taskpool.
Since the taskpool has no type variable, it cannot perform `IO a`.
So the future token has `IO ()`.

##### field `var_state : AsyncTask::Var::Var Minilib.Thread.Future::FutureState`

##### field `io_unit : Std::IO ()`

## Traits and aliases

## Trait implementations

## Values

### `namespace Minilib.Thread.Future`

#### `get : Minilib.Thread.Future::Future a -> Std::IO::IOFail a`

Gets the result of the Future.
It waits for future state to be either completed or canceled.

#### `make : Minilib.Thread.TaskPool::TaskPool -> Std::IO a -> Std::IO::IOFail (Minilib.Thread.Future::Future a)`

`Future::make(task_pool, io) creates a Future.
`io` is performed in the task pool.
If the task pool has been shutdown, an error is thrown.

### `namespace Minilib.Thread.Future::FutureToken`

#### `make : AsyncTask::Var::Var Minilib.Thread.Future::FutureState -> Std::IO () -> Minilib.Thread.Future::FutureToken`

#### `set_state : Minilib.Thread.Future::FutureState -> Minilib.Thread.Future::FutureToken -> Std::IO ()`