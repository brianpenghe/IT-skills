---
title: '[SOLVEDD] shell script printf triple quotes escape or not escape tutorial'
date: 2015-10-28T14:04:00.001-07:00
draft: false
url: /2015/10/solvedd-shell-script-printf-triple.html
---

> **Archived note — originally created: 2015-10-28 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


Literally or comprehensively? Try these: 

declare -i k=0

printf '''

\\$k

'''

printf '''

'$k'

'

printf '''

\\$k

'''

printf '''

"$k"

'

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
