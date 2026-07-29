---
title: 'How to do arithmetic calculations using linux terminal'
date: 2016-02-07T23:50:00.003-08:00
draft: false
url: /2016/02/how-to-do-arithmetic-calculations-using.html
---

> **Archived note — originally created: 2016-02-07 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


Pipe the expression to bc 

```
echo "$a / ( $b - 34 )" | bc -l
``````

``````
Reference: http://stackoverflow.com/questions/15015809/floating-point-results-in-bash-integer-division
```

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
