# Get all openSNP phenotypes, their variations, and how many users have data available for a given phenotype.

Either return data.frame with all results, or output a list, then call
the characteristic by id (parameter = "id") or name (parameter =
"characteristic").

## Usage

``` r
annotations(
  snp = NA,
  output = c("all", "plos", "mendeley", "snpedia", "metadata"),
  ...
)
```

## Arguments

- snp:

  SNP name.

- output:

  Name the source or sources you want annotations from (options are:
  'plos', 'mendeley', 'snpedia', 'metadata'). 'metadata' gives the
  metadata for the response.

- ...:

  Curl options passed on to
  [crul::HttpClient](https://docs.ropensci.org/crul/reference/HttpClient.html)

## Value

data.frame of results

## See also

Other opensnp-fxns:
[`allgensnp()`](https://docs.ropensci.org/rsnps/reference/allgensnp.md),
[`allphenotypes()`](https://docs.ropensci.org/rsnps/reference/allphenotypes.md),
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
## get just the metadata
annotations(snp = "rs7903146", output = "metadata")

## just from plos
annotations(snp = "rs7903146", output = "plos")

## just from snpedia
annotations(snp = "rs7903146", output = "snpedia")

## get all annotations
annotations(snp = "rs7903146", output = "all")
} # }
```
