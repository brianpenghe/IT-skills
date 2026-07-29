---
title: '[solved]Cufflinks prematurely stops when estimating abundance'
date: 2016-01-29T11:34:00.000-08:00
draft: false
url: /2016/01/solvedcufflinks-prematurely-stops-when.html
---

> **Archived note — originally created: 2016-01-29 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


The solution: 
If you are using a GTF file for input, check the longest transcript, it is probably long than the default max-bundle-length which is 3500000, which is apparently not long enough for some ENSEMBL annotations whose record reaches 4400000+. Therefore you could specify max-bundle-length as 4500000 or more and it works.

#Cufflinks #TroubleshootNotes #BloggerPublishedNonAcademicNotes
