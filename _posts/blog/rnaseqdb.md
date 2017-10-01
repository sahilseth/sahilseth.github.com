

RNA-Seq data sets:

CCLE: 
array based: 
rnaseq based:
  hg19, gencode ~v25, processed using salmon:
  Uses ensembl v74: release-74
    https://ocg.cancer.gov/ctd2-data-project/translational-genomics-research-institute-quantified-cancer-cell-line-encyclopedia
    Translational Genomics Research Institute: Quantified Cancer Cell Line Encyclopedia (CCLE) RNA-seq Data
    Many applications analyze quantified transcript-level abundances to make inferences.  Having completed this computation 
    across the large sample set, the CTD2 Center at the Translational Genomics Research Institute presents the quantified data 
    in a straightforward, consolidated form for these types of analyses.
    
    **Experimental Approaches**
    After downloading RNA-seq data for 935 cell lines from the Cancer Cell Line Encyclopedia (link is external) (CCLE), 
    transcript-level abundance was quantified using Salmon1. All data were aligned using Salmon 0.4.2 using 
    Homo Sapiens GRCh37.74 (link is external) for reference. 
    Raw BAM files used to generate this data is avaliable at GDC. 
    The resulting 935 quantification files, named by sample ID, have 4 columns for ensemble gene ID, length, number of reads, 
    and transcripts per million (TPM). Other Salmon arguments were "--libType IU" (inward, unstranded).

TOIL (TCGA + GTEX):
https://xenabrowser.net/datapages/?host=https://toil.xenahubs.net

Pipeline Inputs

STAR, RSEM, and Kallisto indexes were all built with the same reference genome and annotation file.

Reference genome: HG38 (no alt analysis) with overlapping genes from the PAR locus removed (chrY:10,000-2,781,479 and chrY:56,887,902-57,217,415).
ftp://ftp.ncbi.nlm.nih.gov/genomes/archive/old_genbank/Eukaryotes/vertebrates_mammals/Homo_sapiens/GRCh38/seqs_for_alignment_pipelines
Annotation: Gencode V23 comprehensive annotation (CHR)
http://www.gencodegenes.org/releases/23.html)
Inputs were generated with the following commands

STAR
sudo docker run -v $(pwd):/data quay.io/ucsc_cgl/star --runThreadN 32 --runMode genomeGenerate --genomeDir /data/genomeDir --genomeFastaFiles hg38.fa --sjdbGTFfile gencode.v23.annotation.gtf
Kallisto
sudo docker run -v $(pwd):/data quay.io/ucsc_cgl/kallisto index -i hg38.gencodeV23.transcripts.idx transcriptome_hg38_gencodev23.fasta
RSEM
sudo docker run -v $(pwd):/data --entrypoint=rsem-prepare-reference jvivian/rsem -p 4 --gtf gencode.v23.annotation.gtf hg38.fa hg38



## RNASeq DB (MSKCC)

http://www.rna-seqblog.com/enabling-cross-study-analysis-of-rna-sequencing-data/
https://github.com/mskcc/RNAseqDB/tree/master/data
https://www.biorxiv.org/content/biorxiv/early/2017/08/04/110734.full.pdf

Provide the pipeline, and also data in various formats.
Use STAR+RSEM to process the data. HG19

Use SVASeq and combat to correct for batch effects.


## OSF:

https://osf.io/gqrz9/files/
TCGA+CCLE (using kallisto)
summarized here:
https://www.biorxiv.org/content/biorxiv/early/2016/07/12/063552.full.pdf

More details regarding the scripts:
https://osf.io/gqrz9/wiki/Script%20Descriptions/







END
