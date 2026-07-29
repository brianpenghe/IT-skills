---
title: 'R Error: ''\U'' used without hex digits in character string starting "C:\U"'
date: 2015-11-05T13:35:00.003-08:00
draft: false
url: /2015/11/r-error-u-used-without-hex-digits-in.html
---

> **Archived note — originally created: 2015-11-05 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


replace all the `\` with `\\`.

it's trying to escape the next character in this case the `U` so to insert a `\` you need to insert an escaped `\` which is `\\`

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
