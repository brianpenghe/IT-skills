---
title: 'R: read.table vs. read.delim'
date: 2017-07-18T12:18:00.003-07:00
draft: false
url: /2017/07/r-readtable-vs-readdelim.html
---

> **Archived note — originally created: 2017-07-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


Read.delim is a special case of read.table 

more to read here: 

In addition to reading help pages when you are unsure of what a function does, you can also examine the function's actual code. For example, entering `read.delim` reveals that the function contains the following code:

```
> read.delimfunction (file, header = TRUE, sep = "\t", quote = "\"", dec = ".", fill = TRUE, comment.char = "", ...) read.table(file = file, header = header, sep = sep, quote = quote, dec = dec, fill = fill, comment.char = comment.char, ...)
```

Thus, `read.delim()` is simply a wrapper function for `read.table()` with default argument values that are convenient when reading in tab-separated data. It is exactly the same as calling:

```
read.table(file, header = TRUE, sep = "\t", quote = "\"", dec = ".", fill = TRUE, comment.char = "")
``````

``````

``````
Reference: https://stackoverflow.com/questions/10599708/difference-between-read-table-and-read-delim-functions
```

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
