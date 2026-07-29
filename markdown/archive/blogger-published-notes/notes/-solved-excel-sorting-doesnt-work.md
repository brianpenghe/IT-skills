---
title: '[Solved][Excel] Sorting doesn''t work'
date: 2014-12-16T15:42:00.000-08:00
draft: false
url: /2014/12/excel-sorting-doesnt-work.html
---

> **Archived note — originally created: 2014-12-16 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


After doing custom sorting on excel, it's always a good idea to double check, because sometimes it doesn't work. 

Things to check: 
1\. Area to sort. The new excel 2013 will be "smart" enough to interpret your Ctrl + A as selecting the whole local area you are paying attention. So it may not include all the elements in the sheet, which will bring extra trouble 

2\. After sorting. It may not sort out the result you want, at least when you are using calculated values to sort and the formula are somewhat not beautiful to excel. 
When sorting doesn't work on calculated values(the results of formula dependent on other columns), tidy up the formula (better use C:C rather than C1 C2 C3...) and it should work, hopefully

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
