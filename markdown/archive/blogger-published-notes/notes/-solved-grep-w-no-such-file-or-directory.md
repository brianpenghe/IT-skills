---
title: '[solved]grep -w: no such file or directory'
date: 2019-07-23T14:24:00.001-07:00
draft: false
url: /2019/07/solvedgrep-w-no-such-file-or-directory.html
---

> **Archived note — originally created: 2019-07-23 — old (5–8 years) — verify carefully**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


I mistakenly put grep -f -w <query key file> <query file> 

The grep command has to put query key file immediately after -f 
So the correct command is: 
grep -w -f <query key file> <query file>

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
