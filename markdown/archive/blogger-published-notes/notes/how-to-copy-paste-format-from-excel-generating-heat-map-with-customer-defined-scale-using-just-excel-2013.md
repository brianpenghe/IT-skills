---
title: 'How to copy paste format from excel --- generating heat map with customer-defined scale using just excel 2013'
date: 2014-12-24T13:26:00.001-08:00
draft: false
url: /2014/12/how-to-copy-paste-format-from-excel.html
---

> **Archived note — originally created: 2014-12-24 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


This might sound silly but it is beneficial for those who doesn't know programming. 

Example task: generate a heat map of a matrix based on the values of log2(value + 1) 

1\. You create a new sheet and use formula to generate the matrix of log transformed value   value' = log2(value + 1) 

2\. highlight/select all the elements inside this new matrix, click conditional formatting button on excel 
3\. copy (ctrl + c) 
4\. paste it onto a ppt file with the formatting preserved 
5\. copy and past it back to the ORIGINAL(non log transformed) data matrix by choosing to paste format only 

And thus the heatmap is done, with numbers on it.

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
