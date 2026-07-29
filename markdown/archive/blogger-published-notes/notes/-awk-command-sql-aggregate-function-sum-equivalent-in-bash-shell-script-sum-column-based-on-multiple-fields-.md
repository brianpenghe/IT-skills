---
title: '[awk command] SQL aggregate function ''sum'' equivalent in bash shell script (sum column based on multiple fields)'
date: 2017-03-29T14:47:00.001-07:00
draft: false
url: /2017/03/awk-command-sql-aggregate-function-sum.html
---

> **Archived note — originally created: 2017-03-29 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


```
awk '{array[$1]+=$3} END { for (i in array) {print i"," array[i]}}' datas.csv
``````
This function aggregates the rows with similar [$1","$2] combinations 
``````
and output the sum
``````

``````

``````
e.g Say-Tar DNA-FISH 35
``````
 Say-Tar C2C12 24
``````
 Say-Tar C2C12 3
``````
 Georgi Gro-seq 5
``````
 Georgi ChIP-seq 7
``````
 Brian iPSC 24
``````

``````
Then the output should be 
``````
Say-Tar, DNA-FISH, 35
``````
Say-Tar, C2C12, 27
``````
Georgi, Gro-seq, 5
``````
Georgi, ChIP-seq, 7
``````
Brian, iPSC, 24 
```

#ChIP-seq #TroubleshootNotes #BloggerPublishedNonAcademicNotes
