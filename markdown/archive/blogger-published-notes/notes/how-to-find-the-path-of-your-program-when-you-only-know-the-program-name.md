---
title: 'How to find the path of your program when you only know the program name'
date: 2015-09-05T16:56:00.004-07:00
draft: false
url: /2015/09/how-to-find-path-of-your-program-when.html
---

> **Archived note — originally created: 2015-09-05 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


"If it is in your path, then you can run either `type git` or `which git`. The `which` command has had problems getting the proper path (confusion between environment and dot files). For `type`, you can get just the path with the `-p` argument.

If it is not in your path, then it's best to look for it with `locate -b git` It will find anything named 'git'. It'll be a long list, so might be good to qualify it with `locate -b git | fgrep -w bin`."

reference:

http://unix.stackexchange.com/questions/28555/how-to-find-applications-path-from-command-line

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
