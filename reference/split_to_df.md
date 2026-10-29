# Split a Vector of Strings Following a Regular Structure

This function takes a vector of strings following a regular structure,
and converts that vector into a `data.frame`, split on that delimiter. A
nice wrapper to [`strsplit()`](https://rdrr.io/r/base/strsplit.html),
essentially

- the primary bonus is the automatic coercion to a `data.frame`.

## Usage

``` r
split_to_df(x, sep, fixed = FALSE, perl = TRUE, useBytes = FALSE, names = NULL)
```

## Arguments

- x:

  a vector of strings.

- sep:

  the delimiter / [regex](https://rdrr.io/r/base/regex.html) you wish to
  split your strings on.

- fixed:

  logical. If `TRUE`, we match `sep` exactly; otherwise, we use regular
  expressions. Has priority over `perl`.

- perl:

  logical. Should perl-compatible regexps be used?

- useBytes:

  logical. If `TRUE`, matching is done byte-by-byte rather than
  character-by-character.

- names:

  optional: a vector of names to pass to the returned `data.frame`.

## See also

[`strsplit()`](https://rdrr.io/r/base/strsplit.html)
