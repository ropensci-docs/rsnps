# Get openSNP phenotype data for one or multiple users.

Get openSNP phenotype data for one or multiple users.

## Usage

``` r
phenotypes(userid = NA, df = FALSE, ...)
```

## Arguments

- userid:

  ID of openSNP user.

- df:

  Return data.frame (`TRUE`) or not (`FALSE`). Default: `FALSE`

- ...:

  Curl options passed on to
  [crul::HttpClient](https://docs.ropensci.org/crul/reference/HttpClient.html)

## Value

List of phenotypes for specified user(s).

## See also

Other opensnp-fxns:
[`allgensnp()`](https://docs.ropensci.org/rsnps/reference/allgensnp.md),
[`allphenotypes()`](https://docs.ropensci.org/rsnps/reference/allphenotypes.md),
[`annotations()`](https://docs.ropensci.org/rsnps/reference/annotations.md),
[`download_users()`](https://docs.ropensci.org/rsnps/reference/download_users.md),
[`fetch_genotypes()`](https://docs.ropensci.org/rsnps/reference/fetch_genotypes.md),
[`genotypes()`](https://docs.ropensci.org/rsnps/reference/genotypes.md),
[`phenotypes_byid()`](https://docs.ropensci.org/rsnps/reference/phenotypes_byid.md),
[`users()`](https://docs.ropensci.org/rsnps/reference/users.md)

## Examples

``` r
if (FALSE) { # \dontrun{
phenotypes(userid = 1)
phenotypes(userid = "1,6,8", df = TRUE)
phenotypes(userid = "1-8", df = TRUE)

# coerce to data.frame
library(plyr)
df <- ldply(phenotypes(userid = "1-8", df = TRUE))
head(df)
tail(df)

# pass on curl options
phenotypes(1, verbose = TRUE)
} # }
```
