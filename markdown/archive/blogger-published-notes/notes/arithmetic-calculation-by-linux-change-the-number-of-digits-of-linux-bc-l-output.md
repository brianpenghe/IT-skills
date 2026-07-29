---
title: 'arithmetic calculation by Linux ; change the number of digits of linux bc -l output'
date: 2016-02-12T14:48:00.001-08:00
draft: false
url: /2016/02/arithmetic-calculation-by-linux-change.html
---

> **Archived note — originally created: 2016-02-12 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


```
echo 'scale=2; (2.777 - 1.4744)/1' | bc 1.30
``````

``````

``````
reference: http://stackoverflow.com/questions/13963265/bc-is-ignoring-scale-option
```

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
