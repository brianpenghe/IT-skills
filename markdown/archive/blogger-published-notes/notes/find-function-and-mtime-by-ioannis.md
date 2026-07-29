---
title: 'find function and -mtime --- by Ioannis'
date: 2014-07-06T18:34:00.000-07:00
draft: false
url: /2014/07/find-function-and-mtime-by-ioannis.html
---

> **Archived note — originally created: 2014-07-06 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


If an important txt seems to be misplaced and you can't find it after an hour of searching here and there:

find ~/ -mtime -7 -print | grep txt

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
