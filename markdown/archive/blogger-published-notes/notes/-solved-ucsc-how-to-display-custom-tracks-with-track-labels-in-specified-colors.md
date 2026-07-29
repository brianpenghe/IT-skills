---
title: '[Solved][UCSC]How to display custom tracks with track labels in specified colors'
date: 2017-08-19T17:25:00.000-07:00
draft: false
url: /2017/08/solveducschow-to-display-custom-tracks.html
---

> **Archived note — originally created: 2017-08-19 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


Copied this from UCSC: 

```
browser position chr22:1000-10000 
browser hide all 
track name="BED track" description="BED format custom track example" visibility=2 
color=0,128,0 useScore=1 
chr22 1000 5000 itemA 960 + 1100 4700 0 2 1567,1488, 0,2512 
chr22 2000 7000 itemB 200 - 2200 6950 0 4 433,100,550,1500 0,500,2000,3500 
```

Click [here](https://genome.ucsc.edu/cgi-bin/hgTracks?org=human&position=chr22&hgt.customText=http://genome.ucsc.edu/goldenPath/help/examples/ct_example3.txt) to view this track in the Genome Browser.

#UCSC-Genome-Browser #TroubleshootNotes #BloggerPublishedNonAcademicNotes
