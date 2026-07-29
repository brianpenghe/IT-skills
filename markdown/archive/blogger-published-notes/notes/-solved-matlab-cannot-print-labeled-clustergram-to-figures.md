---
title: '[Solved][Matlab]cannot print labeled clustergram to figures'
date: 2017-03-14T13:41:00.001-07:00
draft: false
url: /2017/03/solvedmatlabcannot-print-labeled.html
---

> **Archived note — originally created: 2017-03-14 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


When I was exporting the clustergram to figure, I got a blank image and saw these error codes: 

Index exceeds matrix dimensions. 

Error in clustergram/plot (line 82) 
                    obj.DendroRowLineColor(obj.RowGroups, :),... 

The solution: 

1\. File -> Export Setup... 
2\. Rendering -> make sure Custom color is checked and color is 'w' -> Apply to Figure 
3\. Export and save

#MATLAB #TroubleshootNotes #BloggerPublishedNonAcademicNotes
