---
title: 'linux: create 2D arrays of variables'
date: 2016-04-09T23:19:00.001-07:00
draft: false
url: /2016/04/linux-create-2d-arrays-of-variables.html
---

> **Archived note — originally created: 2016-04-09 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


declare -A barcode 
barcode\[0,0\]=hello 
echo ${barcode\[0,0\]}

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
