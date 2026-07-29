---
title: 'Randomly shuffle intervals'
date: 2017-04-18T15:52:00.001-07:00
draft: false
url: /2017/04/randomly-shuffle-intervals.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


```
$ cat A.bed 
chr1 0 100 a1 1 + 
chr1 0 1000 a2 2 - 

$ cat my.genome 
chr1 10000 
chr2 8000 
chr3 5000 
chr4 2000 

$ bedtools shuffle -i A.bed -g my.genome -chrom \-noOverlapping 

chr1 9560 9660 a1 1 + 
chr1 7258 8258 a2 2 -
``` 

more : 
http://bedtools.readthedocs.org/en/latest/content/tools/shuffle.html

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
