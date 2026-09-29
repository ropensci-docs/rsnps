# Get openSNP genotype data for all users at a particular snp.

Get openSNP genotype data for all users at a particular snp.

## Usage

``` r
allgensnp(snp = NA, usersubset = FALSE, ...)
```

## Arguments

- snp:

  (character) A SNP name

- usersubset:

  Get a subset of users, integer numbers, e.g. 1-8 (default: none)

- ...:

  Curl options passed on to
  [crul::HttpClient](https://docs.ropensci.org/crul/reference/HttpClient.html)

## Value

data.frame of genotypes for all users at a certain SNP

## See also

Other opensnp-fxns:
[`allphenotypes()`](https://docs.ropensci.org/rsnps/reference/allphenotypes.md),
[`annotations()`](https://docs.ropensci.org/rsnps/reference/annotations.md),
[`download_users()`](https://docs.ropensci.org/rsnps/reference/download_users.md),
[`fetch_genotypes()`](https://docs.ropensci.org/rsnps/reference/fetch_genotypes.md),
[`genotypes()`](https://docs.ropensci.org/rsnps/reference/genotypes.md),
[`phenotypes_byid()`](https://docs.ropensci.org/rsnps/reference/phenotypes_byid.md),
[`phenotypes()`](https://docs.ropensci.org/rsnps/reference/phenotypes.md),
[`users()`](https://docs.ropensci.org/rsnps/reference/users.md)

## Examples

``` r
if (FALSE) { # \dontrun{
x <- allgensnp(snp = "rs7412")
head(x)
} # }
```
