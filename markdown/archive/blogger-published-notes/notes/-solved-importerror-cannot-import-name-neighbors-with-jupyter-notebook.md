---
title: '[solved]ImportError: cannot import name ''neighbors'' with Jupyter notebook'
date: 2019-03-14T09:03:00.000-07:00
draft: false
url: /2019/03/solvedimporterror-cannot-import-name.html
---

> **Archived note — originally created: 2019-03-14 — old (5–8 years) — verify carefully**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


import scanpy as sc

/usr/local/lib/python3.6/dist-packages/scanpy/preprocessing/init.py in <module>() 7 from .\_combat import combat 8 ----> 9 from ..neighbors import neighbors

ImportError: cannot import name 'neighbors'

I came across that error and found the cause:

I upgraded scanpy while jupyter was still running.

Solution: restart jupyter notebook

#Scanpy #Python #TroubleshootNotes #BloggerPublishedNonAcademicNotes
