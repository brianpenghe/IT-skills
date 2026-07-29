---
title: 'Cufflink outputs FAILS'
date: 2017-04-18T19:54:00.001-07:00
draft: false
url: /2017/04/cufflink-outputs-fails.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


http://seqanswers.com/forums/showthread.php?t=14864 

[Cole Trapnell](http://seqanswers.com/forums/member.php?u=1564) 
A bit more on what FAIL means, and how it can happen. We use FAIL for genes that actually throw a numerical exception during isoform abundance calculation. In Cufflinks and Cuffdiff, there's a couple of calculations that require us to build matrices with either a row per transcript and a column per read (more or less) or a square matrix with a row and column for each transcript. Some of these matrices need to be invertible or positive definite or have other properties in order for the next steps in the algorithm to succeed. However, sometimes (due to things like round-off error) they aren't. Other times, missing data causes trouble. Oddly enough, this is actually more likely to happen the more reads you get overall, because you can see that isoforms are present, but you don't actually have enough data to calculate those abundances. This is the effect you were observing above. So since we can't be sure about the values (and in fact, were we to go ahead and do the calculation anyways, they could be \*wildly\* off in theory, or even negative), we set them to zero and move on.  

In order to make differential expression estimates more conservative, version 1.1.0 really ramped up the checks that are done before these steps so we don't end up reporting false positives that are due to numerical exceptions. However, users (like yourselves) have been pretty frustrated by those changes, so I've spent the last few weeks going back and streamlining the overall algorithm to actually eliminate pieces that require the matrices to have some of those properties. The main offender was our "importance sampling" procedure, which tries to give us a sense (for each gene) for the accuracy for the maximum likelihood estimate of isoform abundances. This procedure was originally meant to improve the robustness of the estimate when one or more isoforms were close to zero, but in practice, we found that it actually hurts as often as it helps. Moreover, this procedure would often FAIL genes, so I removed it altogether. I've compensated on the differential expression side with some other statistical improvements and fixes, and the result is globally more accurate differential analysis (both in terms of fewer FAILs and fewer false positives than 1.1.0).  

The upcoming version 1.2.0 should drastically reduce the number of FAIL genes, though there will still be some. If we can't calculate an MLE to begin with, or if for some reason the confidence interval calculation fails, a gene will be marked as FAIL. 

Hope this sheds light on things.

#Cufflinks #TroubleshootNotes #BloggerPublishedNonAcademicNotes
