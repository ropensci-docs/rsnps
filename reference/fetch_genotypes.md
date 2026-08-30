# Download openSNP genotype data for a user

Download openSNP genotype data for a user

## Usage

``` r
fetch_genotypes(url, rows = 100, filepath = NULL, quiet = TRUE, ...)
```

## Arguments

- url:

  (character) URL for the download. See example below of function use.

- rows:

  (integer) Number of rows to read in. Useful for getting a glimpse of
  the data. Negative and other invalid values are ignored, giving back
  all data. Default: 100

- filepath:

  (character) If none is given the file is saved to a temporary file,
  which will be lost after your session is closed. Save to a file if you
  want to access it later.

- quiet:

  (logical) Should download progress be suppressed. Default: `TRUE`

- ...:

  Further args passed on to
  [`download.file()`](https://rdrr.io/r/utils/download.file.html)

## Value

data.frame for a single user, with four columns:

- rsid (character)

- chromosome (integer)

- position (integer)

- genotype (character)

## Details

Beware, not setting the rows parameter means that you download the
entire file, which can be large (e.g., 15MB), and so take a while to
download depending on your connection speed. Therefore, rows is set to
10 by default to sort of protect the user.

Internally, we use
[`download.file()`](https://rdrr.io/r/utils/download.file.html) to
download each file, then
[`read.table()`](https://rdrr.io/r/utils/read.table.html) to read the
file to a data.frame.

## See also

Other opensnp-fxns:
[`allgensnp()`](https://docs.ropensci.org/rsnps/reference/allgensnp.md),
[`allphenotypes()`](https://docs.ropensci.org/rsnps/reference/allphenotypes.md),
[`annotations()`](https://docs.ropensci.org/rsnps/reference/annotations.md),
[`download_users()`](https://docs.ropensci.org/rsnps/reference/download_users.md),
[`genotypes()`](https://docs.ropensci.org/rsnps/reference/genotypes.md),
[`phenotypes_byid()`](https://docs.ropensci.org/rsnps/reference/phenotypes_byid.md),
[`phenotypes()`](https://docs.ropensci.org/rsnps/reference/phenotypes.md),
[`users()`](https://docs.ropensci.org/rsnps/reference/users.md)

## Examples

``` r
if (FALSE) { # \dontrun{
# get a data.frame of the users data
data <- users(df = TRUE)
head(data[[1]]) # users with links to genome data
mydata <- fetch_genotypes(
  url = data[[1]][1, "genotypes.download_url"],
  file = "~/myfile.txt"
)

# see some data right away
mydata

# Or read in data later separately
read.table("~/myfile.txt", nrows = 10)
} # }
```
