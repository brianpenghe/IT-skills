---
title: 'linux shell script automatically truncate strings'
date: 2015-09-02T00:31:00.001-07:00
draft: false
url: /2015/09/linux-shell-script-automatically.html
---

> **Archived note — originally created: 2015-09-02 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


My issue is , whenever I print out some string, Linux will always break them into pieces in a weird way. Finally I figured out that each string in Linux has a maximum number of characters that can be contained. 

* max filename length: 255 bytes

Also, check whether there is space between two variable expansions. This is not good 
printf "non-"$local $guys >> test 

Also, when printing a mixture of things, start with a string. e.g. 

Reference: 
http://stackoverflow.com/questions/6571435/limit-on-file-name-length-in-bash

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
