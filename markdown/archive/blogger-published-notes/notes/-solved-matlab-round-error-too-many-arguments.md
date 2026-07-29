---
title: '[solved]Matlab round() error: too many arguments'
date: 2016-11-17T15:04:00.000-08:00
draft: false
url: /2016/11/solvedmatlab-round-error-too-many.html
---

> **Archived note — originally created: 2016-11-17 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


round(pi,3) 
is an example given by mathwork, which doesn't always work because older versions (probably before 2014b) don't support two digits. 

But that's fine, a way to work around that is: 

round(pi\*1000)/1000

#MATLAB #TroubleshootNotes #BloggerPublishedNonAcademicNotes
