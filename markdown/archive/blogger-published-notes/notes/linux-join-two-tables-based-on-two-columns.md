---
title: 'linux join two tables based on two columns'
date: 2016-11-18T11:58:00.000-08:00
draft: false
url: /2016/11/linux-join-two-tables-based-on-two.html
---

> **Archived note — originally created: 2016-11-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


```
join -j 2 -o 1.1,1.2,1.3,2.3 file1 file2
```

**Important**: this assumes your files are sorted (as in your example) according to the SNP name. If they are not, sort them first:

```
join -j 2 -o 1.1,1.2,1.3,2.3 <(sort -k2 file1) <(sort -k2 file2)
``` 

reference: 
http://unix.stackexchange.com/questions/113898/how-to-merge-two-files-based-on-the-matching-of-two-columns

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
