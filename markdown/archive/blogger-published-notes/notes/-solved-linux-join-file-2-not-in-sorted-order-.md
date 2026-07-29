---
title: '[solved] linux join : “File 2 not in sorted order”'
date: 2016-10-19T13:34:00.000-07:00
draft: false
url: /2016/10/solved-linux-join-file-2-not-in-sorted.html
---

> **Archived note — originally created: 2016-10-19 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


Solution: 
using `LANG=en_EN sort -k 1,1 <myfile> ...` then `LANG=en_EN join ...` 

Note: 
Don't use -k 1d,1 for sorting strings such as gene names. 
Always join using ENSEMBL IDs' 

Cause: 
sort -k 1d,1 and join probably have different default orders especially when dealing with strings containing special characters, like '-'

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
