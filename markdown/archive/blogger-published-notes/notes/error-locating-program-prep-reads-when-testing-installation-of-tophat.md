---
title: 'Error locating program: prep_reads when testing installation of tophat '
date: 2017-04-18T15:56:00.001-07:00
draft: false
url: /2017/04/error-locating-program-prepreads-when.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


\[Wed Oct  5 20:55:25 2011\] Preparing output location ./tophat\_out/ 
\[Wed Oct  5 20:55:25 2011\] Checking for Bowtie index files 
\[Wed Oct  5 20:55:25 2011\] Checking for reference FASTA file 
\[Wed Oct  5 20:55:25 2011\] Checking for Bowtie 
    Bowtie version:             0.12.5.0 
\[Wed Oct  5 20:55:25 2011\] Checking for Samtools 
    Samtools Version: 0.1.17 
\[Wed Oct  5 20:55:25 2011\] Checking reads 
    min read length: 75bp, max read length: 75bp 
    format:         fastq 
    quality scale:     phred33 (default) 
Error locating program:  prep\_reads 

I solved this problem simply by using the /path/to/install/bin/ as the current directory and putting all the excutables into this directory and run the data on this very directory!!! sounds stupid but it worked!!!

#Samtools-Version #Bowtie #SAMtools #TopHat #TroubleshootNotes #BloggerPublishedNonAcademicNotes
