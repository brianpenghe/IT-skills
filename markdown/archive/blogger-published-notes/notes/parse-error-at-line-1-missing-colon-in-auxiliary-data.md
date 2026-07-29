---
title: 'Parse error at line 1: missing colon in auxiliary data'
date: 2014-07-25T11:37:00.000-07:00
draft: false
url: /2014/07/parse-error-at-line-1-missing-colon-in.html
---

> **Archived note — originally created: 2014-07-25 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


I had the same problem, but I could solve with two following command 

sed 's/\[ \\t\]\*$//g' samfile > clean.sam(same with Thomas) 
tr -d \\\\r < samfile > samfile.2

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
