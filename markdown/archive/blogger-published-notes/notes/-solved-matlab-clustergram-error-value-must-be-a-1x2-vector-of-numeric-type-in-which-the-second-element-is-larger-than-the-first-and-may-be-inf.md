---
title: '[Solved]Matlab Clustergram error: Value must be a 1x2 vector of numeric type in which the second element is larger than the first and may be Inf'
date: 2019-03-14T15:11:00.000-07:00
draft: false
url: /2019/03/solvedmatlab-clustergram-error-value.html
---

> **Archived note — originally created: 2019-03-14 — old (5–8 years) — verify carefully**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---

```matlab

I was calling clustergram() and got these errors: 

```
Error using clustergram>computeDendrogram (line 1279) 
Encountered error while computing hierarchical clusters: 
Value must be a 1x2 vector of numeric type in which the 
second element is larger than the first and may be Inf 
Error in clustergram/computeClusters (line 909) 
        \[Z1, H1, ~, perm1\] = computeDendrogram(data,... 
Error in clustergram (line 413) 
        computeClusters(obj); 

The cause was: I accidentally gave it a 1Xn vector for clustering 
Why I got a 1Xn vector? 
Because I was using table2array to concert a variable that was already an array

#MATLAB #TroubleshootNotes #BloggerPublishedNonAcademicNotes
