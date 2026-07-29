---
title: '[Solved] Error reading _ebwt[] array'
date: 2016-05-10T22:25:00.000-07:00
draft: false
url: /2016/05/solved-error-reading-ebwt-array.html
---

> **Archived note — originally created: 2016-05-10 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


I was running Tophat2 which calls bowtie2 
I got this error: 

\[2016-05-10 14:51:40\] Reading known junctions from GTF file

\[2016-05-10 14:51:51\] Preparing reads

         left reads: min. length=34, max. length=34, 1745 kept reads (1 discarded)

        right reads: min. length=24, max. length=24, 1746 kept reads (0 discarded)

\[2016-05-10 14:51:51\] Using pre-built transcriptome data..

\[2016-05-10 14:52:06\] Mapping left\_kept\_reads to transcriptome Mus\_musculus.NCBIM37.67.filtered with Bowtie2

\[2016-05-10 14:52:18\] Mapping right\_kept\_reads to transcriptome Mus\_musculus.NCBIM37.67.filtered with Bowtie2

\[2016-05-10 14:52:30\] Resuming TopHat pipeline with unmapped reads

Warning: you have only one segment per read.

        If the read length is greater than or equal to 45bp,

        we strongly recommend that you decrease --segment-length to about half the read length because TopHat will work better with multiple segments

\[2016-05-10 14:52:30\] Mapping left\_kept\_reads.m2g\_um to genome mm9-single-cell-NIST-fixed-spikes with Bowtie2

        \[FAILED\]

Error running bowtie:

Error reading \_ebwt\[\] array: 278873280, 873486272

Error: Encountered internal Bowtie 2 exception (#1)

Command: /woldlab/castor/proj/programs/bowtie2-2.1.0/bowtie2-align --wrapper basic-0 -k 200 -D 15 -R 2 -N 0 -L 20 -i S,1,1.25 --gbar 4 --mp 6,2 --np 1 --rdg 5,3 --rfg 5,3 --score-min C,-14,0 -p 4 --sam-no-hd -x /woldlab/castor/proj/genome/bowtie2-indexes/mm9-single-cell-NIST-fixed-spikes -

bowtie2-align exited with value 1

I rebuilt the bowtie2 index in a separate folder and used the newly built index.

It worked!

#Tophat2 #Bowtie2 #Bowtie #TopHat #single-cell #TroubleshootNotes #BloggerPublishedNonAcademicNotes
