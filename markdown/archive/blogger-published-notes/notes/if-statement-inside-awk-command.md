---
title: 'if statement inside awk command'
date: 2017-11-08T13:55:00.002-08:00
draft: false
url: /2017/11/if-statement-inside-awk-command.html
---

> **Archived note — originally created: 2017-11-08 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


```
awk -F',' '{ if($1=='"$accountNum"') { print $3.$2 } }' Accounts
``````

``````
reference: https://unix.stackexchange.com/questions/145623/awk-with-if-statements
```

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
