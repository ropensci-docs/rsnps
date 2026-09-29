# Read in openSNP user files from local storage.

Beware, these tables can be large. Check your RAM before executing. Or
possibly read in a subset of the data. This function reads in the whole
kitten kaboodle.

## Usage

``` r
read_users(name = NULL, id = NULL, path = NULL, ...)
```

## Arguments

- name:

  User name

- id:

  User id

- path:

  Path to file to read from.

- ...:

  Parameters passed on to
  [`read.table()`](https://rdrr.io/r/utils/read.table.html)

## Value

A data.frame.

## Details

If you specify a name or id, this function reads environment variables
written in the function download_users, and then searches against those
variables for the path to the file saved. Alternatively, you can supply
the path.

## Examples

``` r
if (FALSE) { # \dontrun{
# dat <- read_users(name = "kevinmcc")
# head(dat)
# dat <- read_users(id = 285)
} # }
```
