---
title: 'Try ''rm ./-.tmp.0001.bam'' to remove the file ‘-.tmp.0001.bam’. Try ''rm --help'' for more information'
date: 2016-02-28T11:17:00.002-08:00
draft: false
url: /2016/02/try-rm-tmp0001bam-to-remove-file.html
---

> **Archived note — originally created: 2016-02-28 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


This is because the file I want to remove starts with an '-' in its name. 

**To remove a file whose name starts with a '-', for example '-foo',** 
**use one of these commands:** 
**  rm -- -foo** 
**  rm ./-foo**

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
