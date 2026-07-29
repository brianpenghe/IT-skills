---
title: '[solved] No module error in python when trying to import nltk package'
date: 2015-01-20T15:44:00.002-08:00
draft: false
url: /2015/01/solved-no-module-error-in-python-when.html
---

> **Archived note — originally created: 2015-01-20 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


Try changing the `PYTHONPATH`environment variable. If you are using BASH the below should work. Other Linux shells will be slightly different in how they assign environment variables.

```
export PYTHONPATH=$PYTHONPATH:/usr/local/lib/python2.7/site-packages
```

#Python #Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
