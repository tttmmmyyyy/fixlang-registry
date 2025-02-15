# `module Minilib.App.Clap`

Command line argument parser.
Inspired by [`clap` crate of Rust](https://docs.rs/clap/3.2.0/clap/index.html).

## Types and aliases

### `namespace Minilib.App.Clap`

#### `type Arg = unbox struct { ...fields... }`

A structure that defines arguments.
Arguments can be either optional or positional arguments.
If either `short` or `long` is set, it becomes an optional argument.
Otherwise, it is a positional argument.

##### field `id : Std::String`

##### field `short : Std::U8`

##### field `long : Std::String`

##### field `required : Std::Bool`

##### field `takes_value : Std::Bool`

##### field `multiple_values : Std::Bool`

##### field `default_value : Std::Option Std::String`

##### field `value_name : Std::String`

##### field `help : Std::String`

##### field `action : Minilib.App.Clap::ArgAction::ArgAction`

#### `type ArgMatches = box struct { ...fields... }`

A structure representing the result of parsing command line arguments.

##### field `subcommand : Std::Option (Std::String, Minilib.App.Clap::ArgMatches)`

##### field `map : HashMap::HashMap Std::String (Std::Array Std::String)`

#### `type Command = box struct { ...fields... }`

A structure representing a command (ie. application).

##### field `name : Std::String`

##### field `bin_name : Std::String`

##### field `display_name : Std::String`

##### field `subcommand_path : Std::String`

##### field `version : Std::String`

##### field `author : Std::String`

##### field `about : Std::String`

##### field `subcommands : Std::Array Minilib.App.Clap::Command`

##### field `args : Std::Array Minilib.App.Clap::Arg`

##### field `help_template : Minilib.App.Clap::HelpTemplate`

##### field `version_template : Minilib.App.Clap::HelpTemplate`

#### `type HelpTemplate = unbox struct { ...fields... }`

##### field `data : Std::String`

### `namespace Minilib.App.Clap::ArgAction`

#### `type ArgAction = unbox union { ...variants... }`

The action taken when the argument is parsed.

##### variant `set : ()`

##### variant `append : ()`

##### variant `set_true : ()`

##### variant `set_false : ()`

##### variant `increment : ()`

##### variant `help : ()`

##### variant `version : ()`

### `namespace Minilib.App.Clap::ArgParser`

#### `type ArgParser = unbox struct { ...fields... }`

##### field `command : Minilib.App.Clap::Command`

##### field `remaining_args : Std::Iterator::DynIterator Minilib.App.Clap::Arg`

##### field `matches : Minilib.App.Clap::ArgMatches`

##### field `inputs : Std::Iterator::DynIterator Std::String`

##### field `positional_only : Std::Bool`

## Traits and aliases

## Trait implementations

### `impl Minilib.App.Clap::Arg : Std::ToString`

## Values

### `namespace Minilib.App.Clap::Arg`

#### `_is_option : Minilib.App.Clap::Arg -> Std::Bool`

#### `_is_positional : Minilib.App.Clap::Arg -> Std::Bool`

#### `_long_to_string : Minilib.App.Clap::Arg -> Std::String`

#### `_option_matches : Std::String -> Minilib.App.Clap::Arg -> Std::Bool`

#### `_positional_to_string : Minilib.App.Clap::Arg -> Std::String`

#### `_short_to_string : Minilib.App.Clap::Arg -> Std::String`

#### `default_value : Std::String -> Minilib.App.Clap::Arg -> Minilib.App.Clap::Arg`

Sets `@default_value`.

#### `help : Std::String -> Minilib.App.Clap::Arg -> Minilib.App.Clap::Arg`

Sets `@help`.

#### `long : Std::String -> Minilib.App.Clap::Arg -> Minilib.App.Clap::Arg`

Sets `@long`.

#### `new : Std::String -> Minilib.App.Clap::Arg`

Creates new argument.

#### `required : Minilib.App.Clap::Arg -> Minilib.App.Clap::Arg`

Sets `@required` to true.

#### `short : Std::U8 -> Minilib.App.Clap::Arg -> Minilib.App.Clap::Arg`

Sets `@short`.

#### `takes_multiple_values : Minilib.App.Clap::Arg -> Minilib.App.Clap::Arg`

Sets `@takes_value` to true, `@multiple_values` to true, and `@action` to `append()`.

#### `takes_value : Minilib.App.Clap::Arg -> Minilib.App.Clap::Arg`

Sets `@takes_value` to true, and `@action` to `set()`.

#### `value_name : Std::String -> Minilib.App.Clap::Arg -> Minilib.App.Clap::Arg`

Sets `@value_name`.

### `namespace Minilib.App.Clap::ArgMatches`

#### `_mod_values : Std::String -> (Std::Array Std::String -> Std::Array Std::String) -> Minilib.App.Clap::ArgMatches -> Minilib.App.Clap::ArgMatches`

#### `_set_values : Std::String -> Std::Array Std::String -> Minilib.App.Clap::ArgMatches -> Minilib.App.Clap::ArgMatches`

#### `empty : Minilib.App.Clap::ArgMatches`

An empty `ArgMatches` structure.

#### `get_many : Std::String -> Minilib.App.Clap::ArgMatches -> Std::Option (Std::Array Std::String)`

Gets the array of argument values with the specified ID.

#### `get_one : Std::String -> Minilib.App.Clap::ArgMatches -> Std::Option Std::String`

Gets the value of the argument with the specified ID.

#### `subcommand : Minilib.App.Clap::ArgMatches -> Std::Option (Std::String, Minilib.App.Clap::ArgMatches)`

### `namespace Minilib.App.Clap::ArgParser`

#### `_increment_value : Minilib.App.Clap::Arg -> Minilib.App.Clap::ArgParser::ArgParser -> Std::Result Std::ErrMsg Minilib.App.Clap::ArgParser::ArgParser`

Increments the value as an integer.

#### `_perform_action : Minilib.App.Clap::Arg -> Minilib.App.Clap::ArgParser::ArgParser -> Std::Result Std::ErrMsg Minilib.App.Clap::ArgParser::ArgParser`

Performs the action set in `arg`.

#### `_process_option_arg : Minilib.App.Clap::ArgParser::ArgParser -> Std::Result Std::ErrMsg Minilib.App.Clap::ArgParser::ArgParser`

Treats the current input as an optional argument.

#### `_process_positional_arg : Minilib.App.Clap::ArgParser::ArgParser -> Std::Result Std::ErrMsg Minilib.App.Clap::ArgParser::ArgParser`

Treats the current input as a positional argument.

#### `_remove_arg : Minilib.App.Clap::Arg -> Minilib.App.Clap::ArgParser::ArgParser -> Minilib.App.Clap::ArgParser::ArgParser`

Remove `arg` from the remaining args.

#### `_set_or_append_value : Minilib.App.Clap::Arg -> Minilib.App.Clap::ArgParser::ArgParser -> Std::Result Std::ErrMsg Minilib.App.Clap::ArgParser::ArgParser`

Takes the current input as a value and performs a `set` or `append` action.

#### `advance : Minilib.App.Clap::ArgParser::ArgParser -> Std::Result Std::ErrMsg (Std::String, Minilib.App.Clap::ArgParser::ArgParser)`

Proceed to next input.

#### `append_value : Minilib.App.Clap::Arg -> Std::String -> Minilib.App.Clap::ArgParser::ArgParser -> Minilib.App.Clap::ArgParser::ArgParser`

Adds a value to the array of values in `arg`.

#### `check_required_args_present : Minilib.App.Clap::ArgParser::ArgParser -> Std::Result Std::ErrMsg Minilib.App.Clap::ArgParser::ArgParser`

Check whether the required argument values are set. Reports an error if the value is not set.

#### `get_input : Minilib.App.Clap::ArgParser::ArgParser -> Std::Result Std::ErrMsg Std::String`

Get the current input.

#### `make : Std::Array Std::String -> Minilib.App.Clap::Command -> Minilib.App.Clap::ArgParser::ArgParser`

Creates an `ArgParser` based on the input array and command.

#### `no_inputs : Minilib.App.Clap::ArgParser::ArgParser -> Std::Bool`

Returns True if there are no more inputs. Returns False if there is more input.

#### `parse_args : Minilib.App.Clap::ArgParser::ArgParser -> Std::Result Std::ErrMsg Minilib.App.Clap::ArgParser::ArgParser`

Parse the actual command line argument array and set the value of `Arg`.

#### `set_default_if_not_present : Minilib.App.Clap::ArgParser::ArgParser -> Std::Result Std::ErrMsg Minilib.App.Clap::ArgParser::ArgParser`

If no value is set for the argument, set the default value.

#### `set_value : Minilib.App.Clap::Arg -> Std::String -> Minilib.App.Clap::ArgParser::ArgParser -> Minilib.App.Clap::ArgParser::ArgParser`

Set the value to `arg`.

### `namespace Minilib.App.Clap::Command`

#### `_default_args : Std::Array Minilib.App.Clap::Arg`

#### `_get_submatches_from : Std::Array Std::String -> Minilib.App.Clap::Command -> Std::Result Std::ErrMsg (Std::String, Minilib.App.Clap::ArgMatches)`

#### `about : Std::String -> Minilib.App.Clap::Command -> Minilib.App.Clap::Command`

Sets the description about the command.

#### `arg : Minilib.App.Clap::Arg -> Minilib.App.Clap::Command -> Minilib.App.Clap::Command`

Add an argument definition to the command.

#### `author : Std::String -> Minilib.App.Clap::Command -> Minilib.App.Clap::Command`

Sets the author of the command.

#### `bin_name : Std::String -> Minilib.App.Clap::Command -> Minilib.App.Clap::Command`

Sets the name of the executable binary of the command.

#### `display_name : Std::String -> Minilib.App.Clap::Command -> Minilib.App.Clap::Command`

Sets the display name of the command.

#### `get_matches : Minilib.App.Clap::Command -> Std::IO::IOFail Minilib.App.Clap::ArgMatches`

Parse command line arguments based on `IO::get_args`.
If `--help` or `--version` is specified, the help string or version string will be returned as `throw`.

#### `get_matches_from : Std::Array Std::String -> Minilib.App.Clap::Command -> Std::Result Std::ErrMsg Minilib.App.Clap::ArgMatches`

Parses command line arguments based on the specified input array.
If `--help` or `--version` is specified, the help string or version string will be returned as the error message.

#### `name : Std::String -> Minilib.App.Clap::Command -> Minilib.App.Clap::Command`

Sets the name of the command.

#### `new : Std::String -> Minilib.App.Clap::Command`

Creates a command structure by specifying the command name.

#### `render_help : Minilib.App.Clap::Command -> Std::String`

Generates a help string based on the help template.

#### `render_version : Minilib.App.Clap::Command -> Std::String`

Generates a version string based on the version template.

#### `subcommand : Minilib.App.Clap::Command -> Minilib.App.Clap::Command -> Minilib.App.Clap::Command`

Add a subcommand to the command.

#### `version : Std::String -> Minilib.App.Clap::Command -> Minilib.App.Clap::Command`

Sets the version of the command.

### `namespace Minilib.App.Clap::HelpTemplate`

#### `_default_help : Minilib.App.Clap::HelpTemplate`

#### `_default_version : Minilib.App.Clap::HelpTemplate`

#### `_format_all_args : Minilib.App.Clap::Command -> Minilib.App.Clap::HelpTemplate -> Std::String`

#### `_format_arg : Minilib.App.Clap::Arg -> Std::String`

#### `_format_option : Minilib.App.Clap::Arg -> Std::String`

#### `_format_subcommand : Minilib.App.Clap::Command -> Std::String`

#### `_format_usage : Minilib.App.Clap::Command -> Minilib.App.Clap::HelpTemplate -> Std::String`

#### `format : Minilib.App.Clap::Command -> Minilib.App.Clap::HelpTemplate -> Std::String`

#### `new : Std::String -> Minilib.App.Clap::HelpTemplate`