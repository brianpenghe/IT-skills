---
title: '[solved] how to replace a character with newline (\n) on Mac terminal / linux terminal'
date: 2017-03-10T21:58:00.001-08:00
draft: false
url: /2017/03/solved-how-to-replace-character-with.html
---

> **Archived note — originally created: 2017-03-10 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


```
sed 's/,/\ 
/g'
``````
But this way may not produce a linebreak recognizable by other commands
``````

``````
A better way:
``````
tr , '\n' <temp
```

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
