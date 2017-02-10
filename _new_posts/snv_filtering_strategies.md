Flag known germline variants by looking in dbSNP. I use a subset of dbSNP (> 1% minor allele frequency, mapping only once to reference assembly, and not flagged as "clinically associated"). You can get such a file for ANNOVAR (database name is snp137NonFlagged for the current dbSNP build), see http://www.openbioinformatics.org/annovar/annovar_download.html

Flag known somatic variants by looking in COSMIC. This usually finds well-described hotspot mutations (such as activating KRAS mutations), but overall will not find most of your true somatic variants (my guess). I usually take the whole of COSMIC, irrespective of tumor type.

Add other cancer sequencing studies (e.g. TCGA), as many of these are not yet in COSMIC currently. For TCGA, I use the MAF files available at https://tcga-data.nci.nih.gov/tcgafiles/ftp_auth/distro_ftpusers/anonymous/tumor/. Level 3 MAF files contain experimentally validated somatic mutations only. Level 2 MAF files contain also the unvalidated ones (and can contain germline variants).

Look at the variant allele frequency. If it's 100%, i.e. all reads show the variant, it's very likely germline (unless your tumor sample is 100% tumor cells and all tumor cells have the mutation). If it's below 10%, it can well be an artifact, see e.g. http://www.ncbi.nlm.nih.gov/pubmed/23303777

Check how all of the mismatches in your data (non-reference bases in the alignment) are distributed along the reads from 5' to 3'. If you have a much higher mismatch rate at the first/last bases of your reads, you might want to exclude these read positions.

Filter your variant list further, as it will likely contain a considerable amount of false positives. Table 1 of the VarScan paper http://www.ncbi.nlm.nih.gov/pubmed/22300766 is a good start (read pos, strand, variant read number and frequency, distance to 3', homopolymer, map quality and read length difference).


In Nature, 2013 paper following were removed,

cut -f8 ALL_mutations_removed_by_filters.txt | sort | uniq -c
     46 1000-GENOMES
     42 69-GENOMES-COMPLETE-GENOMICS-PANEL
     82 dbSNP-137
      4 GERMLINE-INDEL-FILTER
     18 GERMLINE-OTHER-CANCER-STUDIES
    185 NHLBI-ESP-6500
     72 SEQ-ARTIF-OR-RARE-SNP
     
Mutect filters,
http://www.nature.com/nbt/journal/v31/n3/fig_tab/nbt.2514_T1.html
http://gatkforums.broadinstitute.org/gatk/discussion/4464/how-mutect-filters-candidate-mutations

Clustered position: variations at almost the same position
Observed in Control: observed in matched normal/panel of normals
Proximal gap: nearby misaligned small insertion/deletion events (>=3 reads with insertions in 11-bp)
possible_contimations: cross-contamination from other samples. Not sure how it is calculated.
This filter rejects candidates with potential cross-patient contamination, controlled by --fraction_contamination.
In the CALLSTATS output file, the relevant columns are labeled t_lod_fstar and contaminant_lod.


This publication, ignored this filter,
biorxiv.org/highwire/filestream/12262/field_highwire_adjunct.../0/043612-1.pdf

## sequencing artefacts,
such as C > A/G > T artifacts (from FFPE)
http://core-genomics.blogspot.com/2014/08/ffpe-bane-of-next-generation-sequencing.html

deamination of cytosine bases converting them to uracil and generating thymines during PCR amplification

https://www.omicsonline.org/open-access/validation-of-next-generation-sequencing-cancer-panels-for-clinical-somatic-mutation-profiling-identification-of-source-of-variations-and-artifacts-using-ffpe-tissues-jngsa.1000109.php?aid=32889
> We also found very high C to T mutation calls associated with Illumina Cancer Panel using TruSeq library preparation protocol (but not with Ion Torrent using AmpliSeq protocol) when a less stringent filter set was used.

