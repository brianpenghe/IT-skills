---
title: 'printf: ` '': invalid format character'
date: 2017-04-08T23:50:00.002-07:00
draft: false
url: /2017/04/printf-invalid-format-character.html
---

> **Archived note — originally created: 2017-04-08 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


It may be caused by printing a % which is recognized by printf as format spec. 

Avoid using % by checking the string you direct to printf to see whether they contain %

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
