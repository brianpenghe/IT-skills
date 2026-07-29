---
title: 'UCSC genome browser string hidden error troubleshoot'
date: 2017-04-18T15:39:00.002-07:00
draft: false
url: /2017/04/ucsc-genome-browser-string-hidden-error.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


**Error It appears that you are directly uploading binary data in an unrecognized format** 

**This is what I got when I tried to paste in this track directly from excel:** 

track type=bigWig name= ES\_CTCF.unique.bamPlus.bigWig description= ES\_CTCF.unique.bamPlus.bigWig visibility=full color=255,100,0 bigDataUrl=http://woldlab.caltech.edu/~phe/ES\_CTCF.unique.bamPlus.bigWig

But when you copy and paste it from blogger it will work.

It turns out that genome browser is able to keep the original format in the excel which generates errors. 

By pasting from excel to blogger the original buggy stuff has been removed somehow.

To have a generate solution to this type of error there is a tool to compare subtle differences of two strings

http://www.textdiff.com/

[![](https://3.bp.blogspot.com/-HhdB_oEFvB0/U5OWTSHDThI/AAAAAAAABTY/A6cB-xmx4RI/s1600/Screen+Shot+2014-06-07+at+3.46.20+PM.png)](http://3.bp.blogspot.com/-HhdB_oEFvB0/U5OWTSHDThI/AAAAAAAABTY/A6cB-xmx4RI/s1600/Screen+Shot+2014-06-07+at+3.46.20+PM.png)

Above is what I got. The red and the green indicate the differences. Although they look the same, they do have formatting differences or something else different that is hard to tell by eye.

Anyway, the best way to copy paste from excel to genome browser may be adding an intermediate step at blogger XD

#Caltech #UCSC-Genome-Browser #TroubleshootNotes #BloggerPublishedNonAcademicNotes
