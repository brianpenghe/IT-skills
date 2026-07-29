---
title: 'Matlab cell2mat: empty matrix 0-by-152'
date: 2016-10-20T13:23:00.002-07:00
draft: false
url: /2016/10/matlab-cell2mat-empty-matrix-0-by-152.html
---

> **Archived note — originally created: 2016-10-20 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


When I read a matrix using textscan and then tried converting it to a matrix, I got an empty matrix. 

No solutions provided by Google when I searched. 

My solution: 
The input file had an extra empty line. Remove that line/linebreak char, and then repeat the importing process. 

Now it works.

#MATLAB #TroubleshootNotes #BloggerPublishedNonAcademicNotes
