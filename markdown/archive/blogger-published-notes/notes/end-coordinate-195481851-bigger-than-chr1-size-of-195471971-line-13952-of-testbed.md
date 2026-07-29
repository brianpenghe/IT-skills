---
title: 'End coordinate 195481851 bigger than chr1 size of 195471971 line 13952 of test.bed'
date: 2016-09-30T18:30:00.002-07:00
draft: false
url: /2016/09/end-coordinate-195481851-bigger-than.html
---

> **Archived note — originally created: 2016-09-30 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


This error can be a serious one. Don't simply use the clipping solution suggested by some online threads. 

Possible causes and solutions: 
1\. You mapped your reads to mm9 but used mm10 sizes to feed the bigBed generation script 

Solution: use mm9 size file to redo the generation or map your reads to mm10 

2\. The program you used upstream extended the fragments and they exceeded the end 

Solution: use bedClip for bed files and use -clip option for bedgraph files

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
