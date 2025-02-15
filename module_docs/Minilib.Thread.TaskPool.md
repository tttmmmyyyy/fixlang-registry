# `module Minilib.Thread.TaskPool`

A task pool that can be used parallel computation.

A task pool creates IOTasks and starts them.
Each task waits for request until shutdown.
When the task receives the request, it performs the request as a computation.
When the task pool is shutdown, all tasks are stopped.
Computations are never performed after shutdown.

## Types and aliases

### `namespace Minilib.Thread.TaskPool`

#### `type TaskPool = unbox struct { ...fields... }`

A task pool that manages a collection of IOTasks.

##### field `chan : Minilib.Thread.Channel::Channel Minilib.Thread.Future::FutureToken`

##### field `tasks : Std::Array (AsyncTask::AsyncIOTask::IOTask ())`

## Traits and aliases

## Trait implementations

## Values

### `namespace Minilib.Thread.TaskPool`

#### `_task_func : Minilib.Thread.Channel::Channel Minilib.Thread.Future::FutureToken -> Std::IO ()`

The task function of the taskpool.

#### `cancel_all_pendings_futures : Minilib.Thread.TaskPool::TaskPool -> Std::IO ()`

Cancel all pending futures and clears the queue.

#### `is_shutdown : Minilib.Thread.TaskPool::TaskPool -> Std::IO Std::Bool`

Checks whether the taskpool has been shutdown.

#### `make : Std::I64 -> Std::IO Minilib.Thread.TaskPool::TaskPool`

`TaskPool::make(task_count)` creates a TaskPool.

#### `register_future : Minilib.Thread.Future::FutureToken -> Minilib.Thread.TaskPool::TaskPool -> Std::IO::IOFail ()`

Register a future.
It sends a future token to the channel.

#### `shutdown : Minilib.Thread.TaskPool::TaskPool -> Std::IO Minilib.Thread.TaskPool::TaskPool`

Shutdowns a taskpool.