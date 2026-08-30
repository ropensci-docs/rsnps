# Changelog

## rsnps 0.6.0

CRAN release: 2023-06-23

#### MINOR IMPROVEMENTS

- allgensnp(): previously the dataframe returned contained duplicate
  “name” columns. Now the “name” column that contains the submitter’s
  name has been renamed “user_name” and the snp rsid name remains
  “name”. ([\#67](https://github.com/ropensci/rsnps/issues/67))
- allgensnp(): added a parameter “usersubset” which allows to download a
  subset of users for the particular rsid.
  ([\#167](https://github.com/ropensci/rsnps/issues/167))
- improved test coverage from 71 to 76% making use of {vcr} with some
  test fixtures.
- some typos and formatting improved
  ([\#167](https://github.com/ropensci/rsnps/issues/167))

#### BUG FIXES

- fix ncbi_snp_query(): fix so that it does not fail when rsid of SNP is
  no longer supported.
  ([\#157](https://github.com/ropensci/rsnps/issues/157))

## rsnps 0.5.0

#### NEW FEATURES

- ncbi_snp_query(): enable allele frequency for different reference
  populations, ncbi_snp_query() outputs now a tibble
  ([\#97](https://github.com/ropensci/rsnps/issues/97)).

#### MINOR IMPROVEMENTS

- ncbi_snp_query(): replace calls to RJSONIO with equivalent in jsonlite
  ([\#98](https://github.com/ropensci/rsnps/issues/98)).
- unit tests for ncbi_snp_query(): added a tolerance to any allele
  frequency checks.
- move vignette source to /vignettes and precompute using an R script.

#### DOCUMENTATION FIXES

- Updated vignette.

## rsnps 0.4.0

CRAN release: 2020-08-28

#### MAJOR IMPROVEMENTS

NCBI / dbSNP changed their API:

- Rewrote `ncbi_snp_query` to accommodate the new API
  ([\#86](https://github.com/ropensci/rsnps/issues/86),
  [\#88](https://github.com/ropensci/rsnps/issues/88)).
- Removed the functions `ncbi_snp_query2` an `ncbi_snp_summary`.

#### MINOR IMPROVEMENTS

- Reordered `ncbi_snp_query` dataframe output to have chromosome and bp
  beside each other
  ([\#70](https://github.com/ropensci/rsnps/issues/70)).
- Changed `ncbi_snp_query` parameter (`SNPs`) to lower case (`snps`).

#### DOCUMENTATION FIXES

- Restructured and fixed a typo in `README.Rmd` and added link to
  vignette ([\#63](https://github.com/ropensci/rsnps/issues/63)).
- Added info of two new maintainers to `DESCRIPTION`.
- Added relevant API links to vignette.

#### BUG FIXES

- Fixed the test for `allphenotypes` function by making it less specific
  ([\#72](https://github.com/ropensci/rsnps/issues/72)).

## rsnps 0.3.0

CRAN release: 2018-09-20

#### DEPRECATED AND DEFUNCT

- [`ld_search()`](https://docs.ropensci.org/rsnps/reference/ld_search-defunct.md)
  is now defunct. The Broad Institute has taken down the SNAP service
  behind the function.
  ([\#46](https://github.com/ropensci/rsnps/issues/46))
  ([\#53](https://github.com/ropensci/rsnps/issues/53))
  ([\#60](https://github.com/ropensci/rsnps/issues/60))

#### NEW FEATURES

- the three NCBI functions gain a new parameter `key` for passing in an
  NCBI Entrez API key. You can alternatively (and we encourage this)
  store your key as an environment variable and we’ll use that instead.
  The key allows you to have higher rate limits than without a key
  ([\#58](https://github.com/ropensci/rsnps/issues/58))
- gains new function
  [`ncbi_snp_summary()`](https://docs.ropensci.org/rsnps/reference/NCBI_snp_query-defunct.md)
  for summary data on a SNP
  ([\#31](https://github.com/ropensci/rsnps/issues/31))

#### MINOR IMPROVEMENTS

- http requests are now done using `crul` instead of `httr`
  ([\#44](https://github.com/ropensci/rsnps/issues/44))
- now using markdown formatted documentation
  ([\#56](https://github.com/ropensci/rsnps/issues/56))
- documented in
  [`ncbi_snp_query()`](https://docs.ropensci.org/rsnps/reference/ncbi_snp_query.md)
  that we can not change the assembly
  ([\#49](https://github.com/ropensci/rsnps/issues/49))

#### BUG FIXES

- fix to
  [`ncbi_snp_query2()`](https://docs.ropensci.org/rsnps/reference/NCBI_snp_query-defunct.md):
  when many IDs passed in, we were failing with a “URI too long”
  message. We now check how many Ids are passed in and do a POST request
  as needed ([\#39](https://github.com/ropensci/rsnps/issues/39))
- fixed problem in
  [`ncbi_snp_query()`](https://docs.ropensci.org/rsnps/reference/ncbi_snp_query.md)
  where it wasn’t pulling out correctly the gene name and BP position
  ([\#25](https://github.com/ropensci/rsnps/issues/25))

## rsnps 0.2.0

CRAN release: 2016-11-20

#### NEW FEATURES

- [`LDSearch()`](https://docs.ropensci.org/rsnps/reference/LDSearch-defunct.md)
  is now
  [`ld_search()`](https://docs.ropensci.org/rsnps/reference/ld_search-defunct.md),
  but
  [`LDSearch()`](https://docs.ropensci.org/rsnps/reference/LDSearch-defunct.md)
  still works until the next CRAN release when it will be defunct
  ([\#33](https://github.com/ropensci/rsnps/issues/33))
- [`NCBI_snp_query()`](https://docs.ropensci.org/rsnps/reference/NCBI_snp_query-defunct.md)
  is now
  [`ncbi_snp_query()`](https://docs.ropensci.org/rsnps/reference/ncbi_snp_query.md),
  but
  [`NCBI_snp_query()`](https://docs.ropensci.org/rsnps/reference/NCBI_snp_query-defunct.md)
  still works until the next CRAN release when it will be defunct
  ([\#33](https://github.com/ropensci/rsnps/issues/33))
- [`NCBI_snp_query2()`](https://docs.ropensci.org/rsnps/reference/NCBI_snp_query2-defunct.md)
  is now
  [`ncbi_snp_query2()`](https://docs.ropensci.org/rsnps/reference/NCBI_snp_query-defunct.md),
  but
  [`NCBI_snp_query2()`](https://docs.ropensci.org/rsnps/reference/NCBI_snp_query2-defunct.md)
  still works until the next CRAN release when it will be defunct
  ([\#33](https://github.com/ropensci/rsnps/issues/33))

#### MINOR IMPROVEMENTS

- Namespace all base R package function calls
  ([\#21](https://github.com/ropensci/rsnps/issues/21))
- Improve
  [`httr::content`](https://httr.r-lib.org/reference/content.html) call
  to parse to text, and `encoding = "UTF-8"`
  ([\#24](https://github.com/ropensci/rsnps/issues/24))
- Added tests for
  [`ld_search()`](https://docs.ropensci.org/rsnps/reference/ld_search-defunct.md)
  ([\#12](https://github.com/ropensci/rsnps/issues/12))
- Added tests for
  [`ncbi_snp_query()`](https://docs.ropensci.org/rsnps/reference/ncbi_snp_query.md)
  and
  [`ncbi_snp_query2()`](https://docs.ropensci.org/rsnps/reference/NCBI_snp_query-defunct.md)
  ([\#13](https://github.com/ropensci/rsnps/issues/13))
- Added ancestral allele output to
  [`ncbi_snp_query()`](https://docs.ropensci.org/rsnps/reference/ncbi_snp_query.md)
  ([\#23](https://github.com/ropensci/rsnps/issues/23))

#### BUG FIXES

- Fix to
  [`fetch_genotypes()`](https://docs.ropensci.org/rsnps/reference/fetch_genotypes.md),
  was failing sometimes when the commented metadata lines at top varied
  in length ([\#22](https://github.com/ropensci/rsnps/issues/22))
- Fix to
  [`ld_search()`](https://docs.ropensci.org/rsnps/reference/ld_search-defunct.md)
  ([\#32](https://github.com/ropensci/rsnps/issues/32))

## rsnps 0.1.6

CRAN release: 2015-03-03

#### MINOR IMPROVEMENTS

- All examples now in `\dontrun`.
  ([\#11](https://github.com/ropensci/rsnps/issues/11))
- Added additional tests for
  [`LDSearch()`](https://docs.ropensci.org/rsnps/reference/LDSearch-defunct.md)
  and
  [`NCBI_snp_query()`](https://docs.ropensci.org/rsnps/reference/NCBI_snp_query-defunct.md).
- Added a vignette.

#### BUG FIXES

- Bugs fixed in
  [`LDSearch()`](https://docs.ropensci.org/rsnps/reference/LDSearch-defunct.md),
  which were actually bugs in
  [`NCBI_snp_query()`](https://docs.ropensci.org/rsnps/reference/NCBI_snp_query-defunct.md).
  ([\#9](https://github.com/ropensci/rsnps/issues/9))
- Bug fixed in
  [`NCBI_snp_query()`](https://docs.ropensci.org/rsnps/reference/NCBI_snp_query-defunct.md)
  as chromosome might also be “X”.

## rsnps 0.1.0

CRAN release: 2014-02-21

#### NEW FEATURES

- Bug fixes to all openSNP functions.

## rsnps 0.0.5

CRAN release: 2013-11-13

#### NEW FEATURES

- released to CRAN
