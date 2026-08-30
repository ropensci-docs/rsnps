# Get openSNP genotype data for one or multiple users.

Get openSNP genotype data for one or multiple users.

## Usage

``` r
genotypes(snp = NA, userid = NA, df = FALSE, ...)
```

## Arguments

- snp:

  SNP name.

- userid:

  ID of openSNP user.

- df:

  Return data.frame (`TRUE`) or not (`FALSE`). Default: `FALSE`

- ...:

  Curl options passed on to
  [crul::HttpClient](https://docs.ropensci.org/crul/reference/HttpClient.html)\]

## Value

List (or data.frame) of genotypes for specified user(s) at a certain
SNP.

## See also

Other opensnp-fxns:
[`allgensnp()`](https://docs.ropensci.org/rsnps/reference/allgensnp.md),
[`allphenotypes()`](https://docs.ropensci.org/rsnps/reference/allphenotypes.md),
[`annotations()`](https://docs.ropensci.org/rsnps/reference/annotations.md),
[`download_users()`](https://docs.ropensci.org/rsnps/reference/download_users.md),
[`fetch_genotypes()`](https://docs.ropensci.org/rsnps/reference/fetch_genotypes.md),
[`phenotypes_byid()`](https://docs.ropensci.org/rsnps/reference/phenotypes_byid.md),
[`phenotypes()`](https://docs.ropensci.org/rsnps/reference/phenotypes.md),
[`users()`](https://docs.ropensci.org/rsnps/reference/users.md)

## Examples

``` r
if (FALSE) { # \dontrun{
genotypes(snp = "rs9939609", userid = 1)
genotypes("rs9939609", userid = "1,6,8", df = TRUE)
genotypes("rs9939609", userid = "1-2", df = FALSE)
} # }
```
