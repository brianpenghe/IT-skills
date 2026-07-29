---
title: 'How to combine columns into a table [Linux]'
date: 2016-02-15T21:57:00.001-08:00
draft: false
url: /2016/02/how-to-combine-columns-into-table-linux.html
---

> **Archived note — originally created: 2016-02-15 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


```
paste file1 file2 | column -s $'\t' -t
``````

``````

``````
reference: http://unix.stackexchange.com/questions/16443/combine-text-files-column-wise
```

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
