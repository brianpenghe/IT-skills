---
title: 'linux: can''t grep/join txt file due to weird parsing'
date: 2017-01-01T13:11:00.002-08:00
draft: false
url: /2017/01/linux-cant-grepjoin-txt-file-due-to.html
---

> **Archived note — originally created: 2017-01-01 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


It's probably due to special windows characters hidden in your txt file created on Windows 

One way to tell is: 

wc $(head -1 _yourtxtfile_) 

to see from the error message whether your first line contains anything like '$'\\r' 

If yes, you can remove them on Linux by using: 
awk '{ sub("\\r$", "");print $1}'  _yourtxtfile_

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
