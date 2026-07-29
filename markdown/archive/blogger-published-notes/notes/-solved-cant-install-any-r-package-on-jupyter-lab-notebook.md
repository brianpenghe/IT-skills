---
title: '[solved] Can''t install any R package on Jupyter Lab notebook'
date: 2021-04-12T02:58:00.003-07:00
draft: false
url: /2021/04/solved-cant-install-any-r-package-on.html
---

> **Archived note — originally created: 2021-04-12 — old (5–8 years) — verify carefully**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


 Interestingly I could install R packages from terminal sudo R

It turned out that the folder that Jupyter Lab R points to is different from what sudo R points to as well.

Eventually, to solve the problem, Martin wiped out my R installation directory. And probably it's a good idea for me not to install packages on sudo R but from notebook directly then.

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
