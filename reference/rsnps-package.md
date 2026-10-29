# Get SNP (Single-Nucleotide Polymorphism) Data on the Web

This package gives you access to data from OpenSNP (https://opensnp.org)
via their API (https://opensnp.org/faq#api) and NCBI's dbSNP SNP
database (https://www.ncbi.nlm.nih.gov/snp).

## NCBI Authentication

This applies the function
[`ncbi_snp_query()`](https://docs.ropensci.org/rsnps/reference/ncbi_snp_query.md):

You can optionally use an API key, if you do it will allow higher rate
limits (more requests per time period)

To get an API key from NCBI you can login to create a key via your
account settings at https://www.ncbi.nlm.nih.gov/account/settings/

\#' Note: NCBI login is via with a 3rd party account (e.g. Google,
orcid, etc.). If you had an already existing NCBI account you can link
it with a 3rd party login and then you can retire your old NCBI login if
you haven't already), otherwise just \#' create a new account.

Once you are logged on to your NCBI account settings
(https://www.ncbi.nlm.nih.gov/account/settings/) you can go to the
section "API Key Management"

Here you can select "Create an API Key" (which will give you up to 10
requests per second, instead of the 3 per second without the API key.).

After generating your key, set an environment variable as `ENTREZ_KEY`
in .Renviron. This .Renviron file can be edited using
[`usethis::edit_r_environ()`](https://usethis.r-lib.org/reference/edit.html)
or by locating and creating/editing this file yourself.

`ENTREZ_KEY='youractualkeynotthisstring'`

Once the API is added to your .Renviron file you can then restart R for
this to take effect.

You can optionally pass in your API key to the key parameter in NCBI
functions in this package. However, it's much better from a security
perspective to set an environment variable.

## Author

Scott Chamberlain <myrmecocystus@gmail.com>

Kevin Ushey <kevinushey@gmail.com>

Hao Zhu <haozhu233@gmail.com>

Sina Rüeger <sina.rueeger@gmail.com>

Julia Gustavsen <j.gustavsen@gmail.com>
