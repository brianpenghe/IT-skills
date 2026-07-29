---
title: 'redirect wget output to stdout'
date: 2015-11-05T13:01:00.001-08:00
draft: false
url: /2015/11/redirect-wget-output-to-stdout.html
---

> **Archived note — originally created: 2015-11-05 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


`wget -O - http://whatever.com/page.php > /dev/null`

or, if you want to redirect standard error output also:

`wget -O - http://whatever.com/page.php > /dev/null 2>&1`

or, for codegolf :-)

`wget -O-`

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
