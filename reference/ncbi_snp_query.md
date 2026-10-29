# Query NCBI's refSNP for information on a set of SNPs via the API

This function queries NCBI's refSNP for information related to the
latest dbSNP build and latest reference genome for information on the
vector of snps submitted.

## Usage

``` r
ncbi_snp_query(snps)
```

## Arguments

- snps:

  (character) A vector of SNPs (rs numbers).

## Value

A dataframe with columns:

- query: The rs ID that was queried.

- chromosome: The chromosome that the marker lies on.

- bp: The chromosomal position, in base pairs, of the marker, as aligned
  with the current genome used by dbSNP. we add 1 to the base pair
  position in the BP column in the output data.frame to agree with what
  the dbSNP website has.

- rsid: Reference SNP cluster ID. If the rs ID queried has been merged,
  the up-to-date name of the ID is returned here, and a warning is
  issued.

- class: The rsid's 'class'. See
  <https://www.ncbi.nlm.nih.gov/projects/SNP/snp_legend.cgi?legend=snpClass>
  for more details.

- gene: If the rsid lies within a gene (either within the exon or
  introns of a gene), the name of that gene is returned here; otherwise,
  `NA`. Note that the gene may not be returned if the rsid lies too far
  upstream or downstream of the particular gene of interest.

- alleles: The alleles associated with the SNP if it is a SNV;
  otherwise, if it is an INDEL, microsatellite, or other kind of
  polymorphism the relevant information will be available here.

- minor: The allele for which the MAF is computed, given it is an SNV;
  otherwise, `NA`.

- maf: The minor allele frequency of the SNP, given it is an SNV. This
  is drawn from the current global reference population used by NCBI
  (GnomAD).

- ancestral_allele: allele as described in the current assembly

- variation_allele: difference to the current assembly

- seqname - Chromosome RefSeq reference.

- hgvs - full hgvs notation for variant

- assembly - which assembly was used for the annotations

- ref_seq - sequence in reference assembly

- maf_population - dataframe of all minor allele frequencies reported,
  with columns study, reference allele, alternative allele (minor) and
  minor allele frequency.

## Details

This function currently pulling data for Assembly 38 - in particular
note that if you think the BP position is wrong, that you may be hoping
for the BP position for a different Assembly.

Note that you are limited in the to a max of one query per second and
concurrent queries are not allowed. If users want to set curl options
when querying for the SNPs they can do so by using
httr::set_config/httr::with_config

## References

<https://www.ncbi.nlm.nih.gov/projects/SNP/>

<https://pubmed.ncbi.nlm.nih.gov/31738401/> SPDI model

## Examples

``` r
if (FALSE) { # \dontrun{
## an example with both merged SNPs, non-SNV SNPs, regular SNPs,
## SNPs not found, microsatellite
SNPs <- c("rs332", "rs420358", "rs1837253", "rs1209415715", "rs111068718")
ncbi_snp_query(SNPs)
# ncbi_snp_query("123456") ##invalid: must prefix with 'rs'
ncbi_snp_query("rs420358")
ncbi_snp_query("rs332") # warning that its merged into another, try that
ncbi_snp_query("rs121909001")
ncbi_snp_query("rs1837253")
ncbi_snp_query("rs1209415715")
ncbi_snp_query("rs111068718")
ncbi_snp_query(snps = "rs9970807")

ncbi_snp_query("rs121909001")
ncbi_snp_query("rs121909001", verbose = TRUE)
} # }
```
