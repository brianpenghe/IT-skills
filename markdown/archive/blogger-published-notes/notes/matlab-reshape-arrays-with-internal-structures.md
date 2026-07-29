---
title: 'Matlab reshape arrays with internal structures'
date: 2018-05-23T14:51:00.004-07:00
draft: false
url: /2018/05/matlab-reshape-arrays-with-internal.html
---

> **Archived note — originally created: 2018-05-23 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


I have an array like this: 

    {1×2 cell} 
    {1×2 cell} 
    {1×2 cell} 
    {1×2 cell} 
    {1×2 cell} 
    {1×2 cell} 
    {1×2 cell} 
    {1×2 cell} 
    {1×2 cell} 
    {1×2 cell} 

But I want to turn it into a 10X2 array. 

The way to do it is 
\[cellfun(@(x) x{1},array,'UniformOutput',false) cellfun(@(x) x{2},array,'UniformOutput',false)\];

#MATLAB #TroubleshootNotes #BloggerPublishedNonAcademicNotes
