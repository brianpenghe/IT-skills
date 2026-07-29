---
title: 'Matlab Cellfun Arrayfun take multiple inputs'
date: 2018-05-23T14:32:00.003-07:00
draft: false
url: /2018/05/matlab-cellfun-arrayfun-take-multiple.html
---

> **Archived note — originally created: 2018-05-23 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


This is done by defining a function 

```
arrayfun(@(z) plus(z, k), x)
```

#MATLAB #TroubleshootNotes #BloggerPublishedNonAcademicNotes
