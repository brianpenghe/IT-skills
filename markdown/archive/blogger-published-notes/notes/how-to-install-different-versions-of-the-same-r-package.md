---
title: 'how to install different versions of the same R package'
date: 2019-06-01T16:57:00.002-07:00
draft: false
url: /2019/06/how-to-install-different-versions-of.html
---

> **Archived note — originally created: 2019-06-01 — old (5–8 years) — verify carefully**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


Use devtools: 

devtools::dev\_mode(path='~/tools/Seurat3/') 
devtools::install\_github(repo = "satijalab/seurat", ref = "release/3.0")

#Seurat #TroubleshootNotes #BloggerPublishedNonAcademicNotes
