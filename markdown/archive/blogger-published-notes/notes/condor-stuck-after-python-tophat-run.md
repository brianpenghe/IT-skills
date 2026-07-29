---
title: 'Condor stuck after python tophat run'
date: 2017-04-18T19:48:00.001-07:00
draft: false
url: /2017/04/condor-stuck-after-python-tophat-run.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


Condor was running tophat commands four by four 
After all my 14 commands finished, it began to run bowtie commands 2 by 2 without letting later submitted commands run, which takes infinite time. 

Solution: Stop all the bowtie commands being run and resubmit

#Bowtie #TopHat #Python #TroubleshootNotes #BloggerPublishedNonAcademicNotes
