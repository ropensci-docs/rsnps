# Get openSNP users.

Get openSNP users.

## Usage

``` r
users(df = FALSE, ...)
```

## Arguments

- df:

  Return data.frame (`TRUE`) or not (`FALSE`). Default: `FALSE`

- ...:

  Curl options passed on to
  [crul::HttpClient](https://docs.ropensci.org/crul/reference/HttpClient.html)

## Value

List of openSNP users, their ID numbers, and XX if available.

## See also

Other opensnp-fxns:
[`allgensnp()`](https://docs.ropensci.org/rsnps/reference/allgensnp.md),
[`allphenotypes()`](https://docs.ropensci.org/rsnps/reference/allphenotypes.md),
[`annotations()`](https://docs.ropensci.org/rsnps/reference/annotations.md),
[`download_users()`](https://docs.ropensci.org/rsnps/reference/download_users.md),
[`fetch_genotypes()`](https://docs.ropensci.org/rsnps/reference/fetch_genotypes.md),
[`genotypes()`](https://docs.ropensci.org/rsnps/reference/genotypes.md),
[`phenotypes_byid()`](https://docs.ropensci.org/rsnps/reference/phenotypes_byid.md),
[`phenotypes()`](https://docs.ropensci.org/rsnps/reference/phenotypes.md)

## Examples

``` r
if (FALSE) { # \dontrun{
# just the list
data <- users(df = FALSE)
data

# get a data.frame of the users data
data <- users(df = TRUE)
data[[1]] # users with links to genome data
data[[2]] # users without links to genome data
} # }
```
