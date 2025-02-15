# `module Minilib.Text.SimpleParser`

Simple text parser. Customizable by monadic operations.
- Stream of characters
- Basic parsers such as character matching
- Create complex parsers with composition

## Types and aliases

### `namespace Minilib.Text.SimpleParser`

#### `type Char = Std::U8`

The type of characters. Currently only UTF-8 string is supported.

#### `type ParseResult = Std::Result Std::ErrMsg (a, Minilib.Text.SimpleParser::Stream::Stream)`

Result type that returns a value of an arbitrary type and a stream.

#### `type Parser a = unbox struct { ...fields... }`

A structure with a function that receive a stream, parse it, and
return the parsed result and the next stream position.

##### field `_parser : Minilib.Text.SimpleParser::Stream::Stream -> Minilib.Text.SimpleParser::ParseResult a`

### `namespace Minilib.Text.SimpleParser::Stream`

#### `type Stream = unbox struct { ...fields... }`

A character iterator that stores the file name, line number, column number,
and offset from the beginning of the file.

##### field `filename : Std::String`

##### field `line : Std::I64`

##### field `column : Std::I64`

##### field `position : Std::I64`

##### field `iter : Std::Iterator::DynIterator Minilib.Text.SimpleParser::Char`

## Traits and aliases

## Trait implementations

### `impl Minilib.Text.SimpleParser::Parser : Std::Functor`

### `impl Minilib.Text.SimpleParser::Parser : Std::Monad`

### `impl Minilib.Text.SimpleParser::Stream::Stream : Std::FromString`

Creates a stream from a string.

### `impl Minilib.Text.SimpleParser::Stream::Stream : Std::ToString`

Converts a stream to a string, for example `"Stream(pos=1001)"`

## Values

### `namespace Minilib.Text.SimpleParser`

#### `_NotMatch : Std::ErrMsg`

A special error message that represents the parser is not matched.

#### `parser : (Minilib.Text.SimpleParser::Stream::Stream -> Minilib.Text.SimpleParser::ParseResult a) -> Minilib.Text.SimpleParser::Parser a`

A function that creates a Parser structure based on the parsing function.

### `namespace Minilib.Text.SimpleParser::Parser`

#### `debug : [a : Std::ToString] Std::String -> Minilib.Text.SimpleParser::Parser a -> Minilib.Text.SimpleParser::Parser a`

Prints the parser result.

#### `error_parser : Std::String -> Minilib.Text.SimpleParser::Parser a`

Raises the specified string as an error.

#### `filter : (a -> Std::Bool) -> Minilib.Text.SimpleParser::Parser a -> Minilib.Text.SimpleParser::Parser a`

Checks whether the parsed result of the specified Parser satisfies the specified conditions.
Raises a `_NotMatch` error if the specified condition is not met.

#### `get_stream : Minilib.Text.SimpleParser::Parser Minilib.Text.SimpleParser::Stream::Stream`

Returns the current stream position.

#### `if_exists : Minilib.Text.SimpleParser::Parser a -> Minilib.Text.SimpleParser::Parser (Std::Option a)`

`p.if_exists` returns `some(x)` if `p` returns `x` as a parse result,
or `none()` if `p` does not match.

#### `map_result : (a -> Std::Result Std::ErrMsg b) -> Minilib.Text.SimpleParser::Parser a -> Minilib.Text.SimpleParser::Parser b`

`parser.map_result(f)` maps the parser result with `f`, possibly reports
an error message.

#### `match_any_char : Minilib.Text.SimpleParser::Parser Minilib.Text.SimpleParser::Char`

Matches any single character. The parsed result is
a single matched character.
If the match fails (eg. the end of stream), a `_NotMatch` error is raised.

#### `match_char : Minilib.Text.SimpleParser::Char -> Minilib.Text.SimpleParser::Parser ()`

Matches a single character specified by the argument.
The parsed result is nothing.
If the match fails, a `_NotMatch` error is raised.

#### `match_char_class : (Minilib.Text.SimpleParser::Char -> Std::Bool) -> Minilib.Text.SimpleParser::Parser Minilib.Text.SimpleParser::Char`

Matches a character satisfying the specified condition.

#### `match_char_if_exists : Std::U8 -> Minilib.Text.SimpleParser::Parser (Std::Option Std::U8)`

Matches a single character if it exists.
The parsed result is `some(c)` if it exists,
`none()` if it does not exist.

#### `match_empty_str : Minilib.Text.SimpleParser::Parser Std::String`

Matches a zero-length string.

#### `match_end_of_stream : Minilib.Text.SimpleParser::Parser ()`

Matches zero-length string at the end of stream.

#### `match_integer : Minilib.Text.SimpleParser::Parser Std::I64`

Matches an integer.

#### `match_one_of_char : Std::String -> Minilib.Text.SimpleParser::Parser Std::String`

Matches a character which is included in the specified string.
The parsed result is a string consisting of the single matched character.
If the match fails, a `_NotMatch` error is raised.

#### `match_str : Std::String -> Minilib.Text.SimpleParser::Parser ()`

Matches a string specified by the argument.
The parsed result is nothing.
If the match fails, a `_NotMatch` error is raised.

#### `match_str_class : (Minilib.Text.SimpleParser::Char -> Std::Bool) -> Minilib.Text.SimpleParser::Parser Std::String`

Matches a zero-or-more-length string. Each character should satisfy the specified condition.

#### `match_str_class_digit : Minilib.Text.SimpleParser::Parser Std::String`

Matches a zero-or-more-length string of digit characters.

#### `match_str_class_lower : Minilib.Text.SimpleParser::Parser Std::String`

Matches a zero-or-more-length string of lowercase characters.

#### `match_str_class_whitespace : Minilib.Text.SimpleParser::Parser Std::String`

Matches a zero-or-more-length string of whitespace characters.

#### `not_match : Minilib.Text.SimpleParser::Parser a`

Raises a `_NotMatch` error.

#### `one_or_more : Minilib.Text.SimpleParser::Parser a -> Minilib.Text.SimpleParser::Parser (Std::Array a)`

Same as `zero_or_more`, but raises a _NotMatch error
if the array length is zero.

#### `or_else : Minilib.Text.SimpleParser::Parser a -> Minilib.Text.SimpleParser::Parser a -> Minilib.Text.SimpleParser::Parser a`

If the first Parser raises a `_NotMatch` error, tries the second Parser.
Note that `pa1.or_else(pa2)` is interpreted as `or_else(pa2, pa1)`,
and  that `pa1.or_else $ pa2` is interpreted as `or_else(pa1, pa2)`.

#### `or_elseF : Minilib.Text.SimpleParser::Parser a -> Minilib.Text.SimpleParser::Parser a -> Minilib.Text.SimpleParser::Parser a`

Flipped version of `or_else`.
`pa1.or_elseF $ pa2` is equivalent to `pa1.or_else(pa2)`.

#### `or_error : Std::String -> Minilib.Text.SimpleParser::Parser a -> Minilib.Text.SimpleParser::Parser a`

If the Parser reports any error (including `_NotMatch`),
raises the specified string as an error.

#### `repeat : Minilib.Text.SimpleParser::Parser a -> Minilib.Text.SimpleParser::Parser (Std::Array a)`

Repeats matches as many as possible. The parse result is
an array of successful matches.
If a _NotMatch error is raised, returns as success.
If an error other than _NotMatch is raised, reports that error.

#### `run_parser : Minilib.Text.SimpleParser::Stream::Stream -> Minilib.Text.SimpleParser::Parser a -> Minilib.Text.SimpleParser::ParseResult a`

Apply a stream to a parsing function and return the parsed result.

#### `run_parser_str : Std::String -> Minilib.Text.SimpleParser::Parser a -> Minilib.Text.SimpleParser::ParseResult a`

Create a stream from a string, then apply a stream to a parsing function
and return the parsed result.

#### `unit : Minilib.Text.SimpleParser::Parser ()`

Match zero-length string.

#### `zero_or_more : Minilib.Text.SimpleParser::Parser a -> Minilib.Text.SimpleParser::Parser (Std::Array a)`

Synonym for `repeat`.

### `namespace Minilib.Text.SimpleParser::Stream`

#### `advance : Minilib.Text.SimpleParser::Stream::Stream -> Std::Option (Minilib.Text.SimpleParser::Char, Minilib.Text.SimpleParser::Stream::Stream)`

`stream.advance` gets next character and increment the stream position.

#### `empty : Minilib.Text.SimpleParser::Stream::Stream`

An empty Stream.

#### `error : Std::String -> Minilib.Text.SimpleParser::Stream::Stream -> Std::Result Std::ErrMsg a`

`stream.error(str)` reports an error along with where it occurred.

#### `make : Std::String -> Minilib.Text.SimpleParser::Stream::Stream`

Creates a stream from specified string.

#### `read_all : Minilib.Text.SimpleParser::Stream::Stream -> (Std::Array Minilib.Text.SimpleParser::Char, Minilib.Text.SimpleParser::Stream::Stream)`

`stream.read_all` reads all characters to the end of stream.

#### `read_string : Std::I64 -> Minilib.Text.SimpleParser::Stream::Stream -> Std::String`

`stream.read_string(n)` reads at most `n` characters and convert them to a string.

#### `read_string_between : Minilib.Text.SimpleParser::Stream::Stream -> Minilib.Text.SimpleParser::Stream::Stream -> Std::String`

`start_stream.read_string_between(end_stream)` reads characters from `start_stream` to `end_stream`
 and convert them to a string.