---
title: 'linux bash: How to remove the first line of each file'
date: 2016-12-11T23:30:00.004-08:00
draft: false
url: /2016/12/linux-bash-how-to-remove-first-line-of.html
---

> **Archived note — originally created: 2016-12-11 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


sed -i -e "1d" $FILE 

or 

```
tail -n +2 "$FILE"
``` 
check http://stackoverflow.com/questions/339483/how-can-i-remove-the-first-line-of-a-text-file-using-bash-sed-script

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
