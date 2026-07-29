---
title: 'HOw to check Tophat mapping stat / mapping rate'
date: 2017-04-18T19:53:00.001-07:00
draft: false
url: /2017/04/how-to-check-tophat-mapping-stat.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


In the log folder inside the output folder, 
look for bowtie.\*.log 

simplest way to know how many mapped: 
```
samtools view accepted\_hits.bam | cut -f1 | sort | uniq | wc -l
```

```
Actually,
``````
The first round : bowtie.left\_kept\_reads.m2g\_um.log
``````
The second round : bowtie.left\_kept\_reads.m2g\_um\_unmapped.log
```

#Bowtie #SAMtools #TopHat #TroubleshootNotes #BloggerPublishedNonAcademicNotes
