Successfully completed.

Resource usage summary:

    CPU time :                                   2.18 sec.
    Max Memory :                                 330 MB
    Average Memory :                             295.00 MB
    Total Requested Memory :                     16385.00 MB
    Delta Memory :                               16055.00 MB
    Max Swap :                                   10620 MB
    Max Processes :                              4
    Max Threads :                                33

```
The output (if any) follows:

BGN at 2015-08-07 13:38:08
[Fri Aug 07 13:38:08 CDT 2015] net.sf.picard.sam.MergeSamFiles INPUT=[CCCT_00392_NoIndex_L001_R1_001.bam, CCCT_00392_NoIndex_L001_R1_002.bam, CCCT_00392_NoIndex_L001_R1_003.bam, CCCT_00392_NoIndex_L001_R1_004.bam, CCCT_00392_NoIndex_L001_R1_005.bam, CCCT_00392_NoIndex_L001_R1_006.bam, CCCT_00392_NoIndex_L001_R1_007.bam, CCCT_00392_NoIndex_L001_R1_008.bam, CCCT_00392_NoIndex_L001_R1_009.bam, CCCT_00392_NoIndex_L001_R1_010.bam, CCCT_00392_NoIndex_L001_R1_011.bam, CCCT_00392_NoIndex_L001_R1_012.bam, CCCT_00392_NoIndex_L001_R1_013.bam, CCCT_00392_NoIndex_L001_R1_014.bam, CCCT_00392_NoIndex_L001_R1_015.bam, CCCT_00392_NoIndex_L001_R1_016.bam, CCCT_00392_NoIndex_L001_R1_017.bam, CCCT_00392_NoIndex_L001_R1_018.bam, CCCT_00392_NoIndex_L001_R1_019.bam, CCCT_00392_NoIndex_L001_R1_020.bam, CCCT_00392_NoIndex_L001_R1_021.bam, CCCT_00392_NoIndex_L001_R1_022.bam, CCCT_00392_NoIndex_L001_R1_023.bam, CCCT_00392_NoIndex_L001_R1_024.bam, CCCT_00392_NoIndex_L001_R1_025.bam, CCCT_00392_NoIndex_L001_R1_026.bam, CCCT_00392_NoIndex_L001_R1_027.bam, CCCT_00392_NoIndex_L001_R1_028.bam, CCCT_00392_NoIndex_L001_R1_029.bam, CCCT_00392_NoIndex_L001_R1_030.bam, CCCT_00392_NoIndex_L001_R1_031.bam, CCCT_00392_NoIndex_L001_R1_032.bam, CCCT_00392_NoIndex_L001_R1_033.bam, CCCT_00392_NoIndex_L001_R1_034.bam, CCCT_00392_NoIndex_L001_R1_035.bam, CCCT_00392_NoIndex_L001_R1_036.bam, CCCT_00392_NoIndex_L001_R1_037.bam, CCCT_00392_NoIndex_L001_R1_038.bam, CCCT_00392_NoIndex_L001_R1_039.bam, CCCT_00392_NoIndex_L001_R1_040.bam, CCCT_00392_NoIndex_L001_R1_041.bam, CCCT_00392_NoIndex_L001_R1_042.bam] OUTPUT=TH-PM198-CCCT.00392_PM198_rg.sorted.bam ASSUME_SORTED=true USE_THREADING=true VALIDATION_STRINGENCY=LENIENT CREATE_INDEX=true    SORT_ORDER=coordinate MERGE_SEQUENCE_DICTIONARIES=false TMP_DIR=tmp/sseth VERBOSITY=INFO QUIET=false COMPRESSION_LEVEL=5 MAX_RECORDS_IN_RAM=500000 CREATE_MD5_FILE=false
INFO	2015-08-07 13:38:31	MergeSamFiles	Input files are in same order as output so sorting to temp directory is not needed.
INFO	2015-08-07 13:39:12	MergeSamFiles	Finished reading inputs.
[Fri Aug 07 13:39:14 CDT 2015] net.sf.picard.sam.MergeSamFiles done. Elapsed time: 1.10 minutes.
Runtime.totalMemory()=2058027008
END at 2015-08-07 13:39:14
```

## repeating the same works:

```
BGN at Mon Aug 10 14:39:16 CDT 2015
[Mon Aug 10 14:39:16 CDT 2015] net.sf.picard.sam.MergeSamFiles INPUT=[CCCT_00392_NoIndex_L001_R1_001.bam, CCCT_00392_NoIndex_L001_R1_002.bam, CCCT_00392_NoIndex_L001_R1_003.bam, CCCT_00392_NoIndex_L001_R1_004.bam, CCCT_00392_NoIndex_L001_R1_005.bam, CCCT_00392_NoIndex_L001_R1_006.bam, CCCT_00392_NoIndex_L001_R1_007.bam, CCCT_00392_NoIndex_L001_R1_008.bam, CCCT_00392_NoIndex_L001_R1_009.bam, CCCT_00392_NoIndex_L001_R1_010.bam, CCCT_00392_NoIndex_L001_R1_011.bam, CCCT_00392_NoIndex_L001_R1_012.bam, CCCT_00392_NoIndex_L001_R1_013.bam, CCCT_00392_NoIndex_L001_R1_014.bam, CCCT_00392_NoIndex_L001_R1_015.bam, CCCT_00392_NoIndex_L001_R1_016.bam, CCCT_00392_NoIndex_L001_R1_017.bam, CCCT_00392_NoIndex_L001_R1_018.bam, CCCT_00392_NoIndex_L001_R1_019.bam, CCCT_00392_NoIndex_L001_R1_020.bam, CCCT_00392_NoIndex_L001_R1_021.bam, CCCT_00392_NoIndex_L001_R1_022.bam, CCCT_00392_NoIndex_L001_R1_023.bam, CCCT_00392_NoIndex_L001_R1_024.bam, CCCT_00392_NoIndex_L001_R1_025.bam, CCCT_00392_NoIndex_L001_R1_026.bam, CCCT_00392_NoIndex_L001_R1_027.bam, CCCT_00392_NoIndex_L001_R1_028.bam, CCCT_00392_NoIndex_L001_R1_029.bam, CCCT_00392_NoIndex_L001_R1_030.bam, CCCT_00392_NoIndex_L001_R1_031.bam, CCCT_00392_NoIndex_L001_R1_032.bam, CCCT_00392_NoIndex_L001_R1_033.bam, CCCT_00392_NoIndex_L001_R1_034.bam, CCCT_00392_NoIndex_L001_R1_035.bam, CCCT_00392_NoIndex_L001_R1_036.bam, CCCT_00392_NoIndex_L001_R1_037.bam, CCCT_00392_NoIndex_L001_R1_038.bam, CCCT_00392_NoIndex_L001_R1_039.bam, CCCT_00392_NoIndex_L001_R1_040.bam, CCCT_00392_NoIndex_L001_R1_041.bam, CCCT_00392_NoIndex_L001_R1_042.bam] OUTPUT=TH-PM198-CCCT.00392_PM198_rg.sorted.bam ASSUME_SORTED=true USE_THREADING=true VALIDATION_STRINGENCY=LENIENT CREATE_INDEX=true    SORT_ORDER=coordinate MERGE_SEQUENCE_DICTIONARIES=false TMP_DIR=tmp/sseth VERBOSITY=INFO QUIET=false COMPRESSION_LEVEL=5 MAX_RECORDS_IN_RAM=500000 CREATE_MD5_FILE=false
INFO	2015-08-10 14:39:19	MergeSamFiles	Input files are in same order as output so sorting to temp directory is not needed.
INFO	2015-08-10 14:39:23	MergeSamFiles	1000000 records processed.
INFO	2015-08-10 14:39:26	MergeSamFiles	2000000 records processed.
INFO	2015-08-10 14:39:29	MergeSamFiles	3000000 records processed.
INFO	2015-08-10 14:39:33	MergeSamFiles	4000000 records processed.
INFO	2015-08-10 14:39:36	MergeSamFiles	5000000 records processed.
INFO	2015-08-10 14:39:40	MergeSamFiles	6000000 records processed.
INFO	2015-08-10 14:39:43	MergeSamFiles	7000000 records processed.
```


```
Successfully completed.

Resource usage summary:

    CPU time :                                   812.43 sec.
    Max Memory :                                 2908 MB
    Average Memory :                             2653.60 MB
    Total Requested Memory :                     16385.00 MB
    Delta Memory :                               13477.00 MB
    Max Swap :                                   10620 MB
    Max Processes :                              4
    Max Threads :                                34
```