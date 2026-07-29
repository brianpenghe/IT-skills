---
title: 'install samtools on Ubuntu(gcc -c -g -Wall -O2 -D_FILE_OFFSET_BITS=64 -D_LARGEFILE64_SOURCE -D_USE_KNETFILE -D_CURSES_LIB=1 -I. bgzf.c -o bgzf.o In file included from bgzf.c:36:0: bgzf.h:29:18: fatal error: zlib.h: No such file or directory compilation ) '
date: 2017-04-18T15:43:00.003-07:00
draft: false
url: /2017/04/install-samtools-on-ubuntugcc-c-g-wall.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


I just found a way to solve this problem: 

http://ubuntuforums.org/showthread.php?t=1632027 

To put it simple, 
First:  sudo apt-get update 
Second:  sudo apt-get install zlib1g-dev libncurses5-dev 
Third: make  #this is the step to restart the samtools installation 

Done!

#SAMtools #TroubleshootNotes #BloggerPublishedNonAcademicNotes
