# Get all openSNP known variations and all users sharing that phenotype for one phenotype(-ID).

Get all openSNP known variations and all users sharing that phenotype
for one phenotype(-ID).

## Usage

``` r
phenotypes_byid(
  phenotypeid = NA,
  return_ = c("description", "knownvars", "users"),
  ...
)
```

## Arguments

- phenotypeid:

  ID of openSNP phenotype.

- return\_:

  Return data.frame (`TRUE`) or not (`FALSE`). Default: `FALSE`

- ...:

  Curl options passed on to
  [crul::HttpClient](https://docs.ropensci.org/crul/reference/HttpClient.html)

## Value

List of description of phenotype, list of known variants, or data.frame
of variants for each user with that phenotype.

## See also

Other opensnp-fxns:
[`allgensnp()`](https://docs.ropensci.org/rsnps/reference/allgensnp.md),
[`allphenotypes()`](https://docs.ropensci.org/rsnps/reference/allphenotypes.md),
[`annotations()`](https://docs.ropensci.org/rsnps/reference/annotations.md),
[`download_users()`](https://docs.ropensci.org/rsnps/reference/download_users.md),
[`fetch_genotypes()`](https://docs.ropensci.org/rsnps/reference/fetch_genotypes.md),
[`genotypes()`](https://docs.ropensci.org/rsnps/reference/genotypes.md),
[`phenotypes()`](https://docs.ropensci.org/rsnps/reference/phenotypes.md),
[`users()`](https://docs.ropensci.org/rsnps/reference/users.md)

## Examples

``` r
if (FALSE) { # \dontrun{
phenotypes_byid(phenotypeid = 12, return_ = "desc")
phenotypes_byid(phenotypeid = 12, return_ = "knownvars")
phenotypes_byid(phenotypeid = 12, return_ = "users")

# pass on curl options
phenotypes_byid(phenotypeid = 12, return_ = "desc", verbose = TRUE)
} # }
```
