---
title: 'Condor task Held "H". Why?'
date: 2017-04-18T19:37:00.000-07:00
draft: false
url: /2017/04/condor-task-held-h-why.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


Do "condor\_q -long 44337 and look for HoldReason.  In this case: 

HoldReason = "Error from slot1@XXX.caltech.edu: Failed to open '/..shell.0.out' as standard output: No such file or directory (errno 2)"

#Caltech #TroubleshootNotes #BloggerPublishedNonAcademicNotes
