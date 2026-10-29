# Get all openSNP phenotypes, their variations, and how many users have data available for a given phenotype.

Either return data.frame with all results, or output a list, then call
the characteristic by id (parameter = "id") or name (parameter =
"characteristic").

## Usage

``` r
allphenotypes(df = FALSE, ...)
```

## Arguments

- df:

  Return a data.frame of all data. The column known_variations can take
  multiple values, so the other columns id, characteristic, and
  number_of_users are replicated in the data.frame. Default: `FALSE`

- ...:

  Curl options passed on to
  [crul::HttpClient](https://docs.ropensci.org/crul/reference/HttpClient.html)

## Value

data.frame of results, or list if `df=FALSE`

## See also

Other opensnp-fxns:
[`allgensnp()`](https://docs.ropensci.org/rsnps/reference/allgensnp.md),
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
# Get all data
allphenotypes(df = TRUE)

# Output a list, then call the characterisitc of interest by 'id' or
# 'characteristic'
datalist <- allphenotypes()
names(datalist) # get list of all characteristics you can call
datalist[["ADHD"]] # get data.frame for 'ADHD'
datalist[c("mouth size", "SAT Writing")] # get data.frame for 'ADHD'
} # }
```
