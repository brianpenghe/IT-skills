---
title: '[imagej]how to count dots on an image'
date: 2016-09-07T21:13:00.003-07:00
draft: false
url: /2016/09/imagejhow-to-count-dots-on-image.html
---

> **Archived note — originally created: 2016-09-07 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


Two steps: 
1\. using a threshold to convert your image into binary form (positive + negative) 

_Image  ▶ Adjust  ▶ Threshold_.  
check "dark background" 
Drag the bars so that the thresholds let the particles/dots stand out while leaving no background smears there 

2\. If your dots have overlapping groups, force them to separate: 
_Process  ▶ Binary  ▶ Watershed_. 

3. Analyze Particles 
size: 0-infinity or leave blank 
More stringent: 10-infinity  
_Analyze  ▶ Analyze particles_ 
_Show:  -> Eclipse_ 
_check display results and summarize_ 
_reference:_ 
_http://imagej.net/Particle\_Analysis_

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
