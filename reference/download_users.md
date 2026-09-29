# Download openSNP user files.

Download openSNP user files.

## Usage

``` r
download_users(name = NULL, id = NULL, dir = "~/", ...)
```

## Arguments

- name:

  User name

- id:

  User id

- dir:

  Directory to save file to

- ...:

  Curl options passed on to
  [crul::HttpClient](https://docs.ropensci.org/crul/reference/HttpClient.html)

## Value

File downloaded to directory you specify (or default), nothing returned
in R.

## See also

Other opensnp-fxns:
[`allgensnp()`](https://docs.ropensci.org/rsnps/reference/allgensnp.md),
[`allphenotypes()`](https://docs.ropensci.org/rsnps/reference/allphenotypes.md),
[`annotations()`](https://docs.ropensci.org/rsnps/reference/annotations.md),
[`fetch_genotypes()`](https://docs.ropensci.org/rsnps/reference/fetch_genotypes.md),
[`genotypes()`](https://docs.ropensci.org/rsnps/reference/genotypes.md),
[`phenotypes_byid()`](https://docs.ropensci.org/rsnps/reference/phenotypes_byid.md),
[`phenotypes()`](https://docs.ropensci.org/rsnps/reference/phenotypes.md),
[`users()`](https://docs.ropensci.org/rsnps/reference/users.md)

## Examples

``` r
if (FALSE) { # \dontrun{
# Download a single user file, by id
download_users(id = 14)

# Download a single user file, by user name
download_users(name = "kevinmcc")

# Download many user files
lapply(c(14, 22), function(x) download_users(id = x))
read_users(id = 14, nrows = 5)
} # }
```
