---
title: '***ERROR: Unrecognized parameter: IntersectBed [how to concatenate a string to a file name][bash]'
date: 2017-04-18T16:01:00.001-07:00
draft: false
url: /2017/04/error-unrecognized-parameter.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


for bed in filenam\*.bed

       do 

                 for deb in location/\*${bed:3}

\[don't use double quote to avoid error\]

solved by John Furgason

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
