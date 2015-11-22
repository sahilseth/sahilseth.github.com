At times mutect dies with JAVA error.

```
##### ERROR ------------------------------------------------------------------------------------------
##### ERROR A USER ERROR has occurred (version 3.1-0-g72492bb):
##### ERROR
##### ERROR This means that one or more arguments or inputs in your command are incorrect.
##### ERROR The error message below tells you what is the problem.
##### ERROR
##### ERROR If the problem is an invalid argument, please check the online documentation guide
##### ERROR (or rerun your command with --help) to view allowable command-line arguments for this tool.
##### ERROR
##### ERROR Visit our website and forum for extensive documentation and answers to
##### ERROR commonly asked questions http://www.broadinstitute.org/gatk
##### ERROR
##### ERROR Please do NOT post this error to the GATK forum unless you have really tried to fix it yourself.
##### ERROR
##### ERROR MESSAGE: There was a failure because you did not provide enough memory to run this program.  See the -Xmx JVM argument to adjust the maximum heap size provided to Java
```

Cher 14 and 21 died in a RNA-Seq samples from ION-torrent data. 


For sample 691, it gets stuck at: chr14:50053421. Possibly too many reads here. This was a issue when using defrac. When we use dcov 1000 (default), memory usage is better.

The sample had 1.6M depth at this location.

```
samtools view $bam chr14:50053421 | wc -l
16, 579, 589
```