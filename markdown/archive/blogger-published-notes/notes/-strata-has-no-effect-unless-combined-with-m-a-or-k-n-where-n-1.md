---
title: '--strata has no effect unless combined with -m, -a, or -k N where N > 1'
date: 2016-03-06T15:50:00.003-08:00
draft: false
url: /2016/03/strata-has-no-effect-unless-combined.html
---

> **Archived note — originally created: 2016-03-06 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


This bowtie indicates that your used --strata without specifying -m

By default, -m is infinite, allowing infinite numbers of alignments per read if exist

However, --strata is a strategy which only works when -m is specified.

So you either remove --strata, or specify an -m, like 10000

#Bowtie #TroubleshootNotes #BloggerPublishedNonAcademicNotes
