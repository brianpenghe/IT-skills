---
title: 'How to save figures produced in R'
date: 2019-05-08T08:56:00.000-07:00
draft: false
url: /2019/05/how-to-save-figures-produced-in-r.html
---

> **Archived note — originally created: 2019-05-08 — old (5–8 years) — verify carefully**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


If it's produced by ggplot or any programs that use it, you can use this function: 
ggsave(filename, plot=last\_plot(), device = "eps", path="./Figures", scale=1,dpi = 300)

#R #TroubleshootNotes #BloggerPublishedNonAcademicNotes
