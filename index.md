# rsnps

[![R build
status](https://github.com/ropensci/rsnps/workflows/R-CMD-check/badge.svg)](https://github.com/ropensci/rsnps/actions)
[![Build
status](https://ci.appveyor.com/api/projects/status/d2lv98726u6t9ut5/branch/master)](https://ci.appveyor.com/project/sckott/rsnps/branch/master/)
[![Codecov test
coverage](https://codecov.io/gh/ropensci/rsnps/branch/master/graph/badge.svg)](https://app.codecov.io/gh/ropensci/rsnps?branch=master)
[![cran
version](https://www.r-pkg.org/badges/version/rsnps)](https://cran.r-project.org/package=rsnps)
[![rstudio mirror
downloads](https://cranlogs.r-pkg.org/badges/rsnps?color=E664A4)](https://github.com/r-hub/cranlogs.app)

This package gives you access to data from OpenSNP and NCBI’s dbSNP SNP
database.

## NOTE

`rsnps` used to be `ropensnp`

## Data sources

This set of functions/package accesses data from:

- openSNP.org
  - <https://opensnp.org>
  - See documentation on the openSNP API <https://opensnp.org/faq#api>
  - See blog post about their API
    <https://opensnp.wordpress.com/2012/01/18/some-progress-on-the-api-json-endpoints/>
  - Relevant functions:
    - [`allgensnp()`](https://docs.ropensci.org/rsnps/reference/allgensnp.md),
      [`allphenotypes()`](https://docs.ropensci.org/rsnps/reference/allphenotypes.md),
      [`annotations()`](https://docs.ropensci.org/rsnps/reference/annotations.md),
      [`download_users()`](https://docs.ropensci.org/rsnps/reference/download_users.md),
      [`fetch_genotypes()`](https://docs.ropensci.org/rsnps/reference/fetch_genotypes.md),
      [`genotypes()`](https://docs.ropensci.org/rsnps/reference/genotypes.md),
      [`phenotypes()`](https://docs.ropensci.org/rsnps/reference/phenotypes.md),
      [`phenotypes_byid()`](https://docs.ropensci.org/rsnps/reference/phenotypes_byid.md),
      [`users()`](https://docs.ropensci.org/rsnps/reference/users.md)
- NCBI’s dbSNP SNP database
  - See <https://www.ncbi.nlm.nih.gov/snp/> for more details
  - Relevant function:
    - [`ncbi_snp_query()`](https://docs.ropensci.org/rsnps/reference/ncbi_snp_query.md)

## Install

Install from CRAN

``` r

install.packages("rsnps")
```

Or dev version

``` r

install.packages("remotes")
remotes::install_github("ropensci/rsnps")
```

``` r

library("rsnps")
```

## Usage

### NCBI dbSNP data

``` r

snps <- c("rs332", "rs420358", "rs1837253", "rs1209415715", "rs111068718")
ncbi_snp_query(snps)
```

``` R
#> # A tibble: 4 × 16
#>   query        chromosome        bp class rsid    gene  alleles ancestral_allele
#>   <chr>        <chr>          <dbl> <chr> <chr>   <chr> <chr>   <chr>           
#> 1 rs332        7          117559593 del   rs1219… "CFT… TTT, d… TTT             
#> 2 rs420358     1           40341239 snv   rs4203… ""    A,C,G,T A               
#> 3 rs1837253    5          111066174 snv   rs1837… ""    T,C     T               
#> 4 rs1209415715 9           41782316 snv   rs1209… ""    T,A,C   T               
#> # ℹ 8 more variables: variation_allele <chr>, seqname <chr>, hgvs <chr>,
#> #   assembly <chr>, ref_seq <chr>, minor <chr>, maf <dbl>,
#> #   maf_population <list>
```

The
[`ncbi_snp_query()`](https://docs.ropensci.org/rsnps/reference/ncbi_snp_query.md)
function can be used with an NCBI API which gives access higher numbers
of API requests per second. More information about setting this up can
be found in the package help accessed via
[`?rsnps`](https://docs.ropensci.org/rsnps/reference/rsnps-package.md).

### openSNP data

[`genotypes()`](https://docs.ropensci.org/rsnps/reference/genotypes.md)
function

``` r

genotypes('rs9939609', userid='1,6,8', df=TRUE)
```

``` R
#>    snp_name snp_chromosome snp_position                 user_name user_id
#> 1 rs9939609             16     53786615 Bastian Greshake Tzovaras       1
#> 2 rs9939609             16     53786615              Nash Parovoz       6
#> 3 rs9939609             16     53786615         Samantha B. Clark       8
#>   genotype_id genotype
#> 1           9       AT
#> 2           5       AT
#> 3           2       TT
```

[`phenotypes()`](https://docs.ropensci.org/rsnps/reference/phenotypes.md)
function

``` r

out <- phenotypes(userid=1)
out$phenotypes$`Hair Type`
```

``` R
#> $phenotype_id
#> [1] 16
#> 
#> $variation
#> [1] "straight"
```

For more detail, see the [vignette: rsnps
tutorial](https://github.com/ropensci/rsnps/tree/master/vignettes).

## Meta

- Please [report any issues or
  bugs](https://github.com/ropensci/rsnps/issues/).
- License: MIT
- Get citation information for `rsnsps` in R doing
  `citation(package = 'rsnps')`
- Please note that this package is released with a [Contributor Code of
  Conduct](https://ropensci.org/code-of-conduct/). By contributing to
  this project, you agree to abide by its terms.
