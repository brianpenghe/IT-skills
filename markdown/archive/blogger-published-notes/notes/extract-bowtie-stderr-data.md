---
title: 'Extract Bowtie Stderr data'
date: 2015-11-05T13:37:00.007-08:00
draft: false
url: /2015/11/extract-bowtie-stderr-data.html
---

> **Archived note — originally created: 2015-11-05 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


awk -F ":" '{print $2}' \*.fq\_stderr

#Bowtie #TroubleshootNotes #BloggerPublishedNonAcademicNotes
