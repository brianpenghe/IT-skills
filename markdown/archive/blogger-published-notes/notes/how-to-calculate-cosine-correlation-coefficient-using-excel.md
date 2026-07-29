---
title: 'how to calculate cosine correlation coefficient using Excel'
date: 2016-10-11T20:25:00.001-07:00
draft: false
url: /2016/10/how-to-calculate-cosine-correlation.html
---

> **Archived note — originally created: 2016-10-11 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


```
=power(SUMPRODUCT(A1:A3,B1:B3),2)/SUMSQ(A1:A3)/SUMSQ(B1:B3)
``````

``````
reference: http://stackoverflow.com/questions/22715120/excel-scalar-product-of-two-ranges
```

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
