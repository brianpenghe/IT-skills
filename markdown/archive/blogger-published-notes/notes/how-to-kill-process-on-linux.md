---
title: 'How to kill process on Linux'
date: 2015-11-05T13:18:00.001-08:00
draft: false
url: /2015/11/how-to-kill-process-on-linux_5.html
---

> **Archived note — originally created: 2015-11-05 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


lsof +D RNA-SeQC     to list the running programs on this folder

I got

lsof: WARNING: can't stat() nfs file system /mmjggl/packrat/data00

      Output information may be incomplete.

COMMAND   PID USER   FD   TYPE DEVICE SIZE/OFF  NODE NAME

java    23583  phe   18r   REG   0,59 23365603 32063 RNA-SeQC/.nfs0000000000007d3f0000106d

java    23583  phe   35w   REG   0,59  4091782 32164 RNA-SeQC/ExpoNoTrim/highexpr/.nfs0000000000007da40000106e

kill 23583

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
