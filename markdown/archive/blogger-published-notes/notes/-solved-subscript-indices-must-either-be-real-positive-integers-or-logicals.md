---
title: '[solved]Subscript indices must either be real positive integers or logicals'
date: 2017-03-27T11:49:00.001-07:00
draft: false
url: /2017/03/solvedsubscript-indices-must-either-be.html
---

> **Archived note — originally created: 2017-03-27 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


I got this error when using the function size() 

Because I defined a variable named "size" that overwrote this function 

Matlab had better name the function GetSize() since "size" is a common name for customer variables 

So the solution is: copy out the variable content (size2=size;)  and right click to delete your variable named "size"

#MATLAB #TroubleshootNotes #BloggerPublishedNonAcademicNotes
