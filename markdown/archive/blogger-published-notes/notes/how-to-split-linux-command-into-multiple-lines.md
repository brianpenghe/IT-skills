---
title: 'how to split linux command into multiple lines: '
date: 2016-02-01T14:37:00.003-08:00
draft: false
url: /2016/02/how-to-split-linux-command-into.html
---

> **Archived note — originally created: 2016-02-01 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


```
ls -l \\ 
 --reverse \\ 
 --human-readable \\ 
 --full-time 

```

Using the backslash in this way allows us to embed newlines in our command. Note that for this trick to work, the newline must be typed immediately after the backslash. If you put a space after the backslash, the space will be ignored, not the newline. 

(copied from http://linuxcommand.org/wss0060.php)

Troubleshoot:

avoid whitespaces disturbing the backslash, as mentioned here:

http://stackoverflow.com/questions/18599711/how-can-i-split-a-bash-command-over-multiple-lines-when-using-an-if-statement

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
