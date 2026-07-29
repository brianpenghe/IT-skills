---
title: '[Solved]GitHub: fatal: Reference has invalid format: ''refs/remotes/origin/...'''''
date: 2016-05-08T21:04:00.001-07:00
draft: false
url: /2016/05/solvedgithub-fatal-reference-has.html
---

> **Archived note — originally created: 2016-05-08 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


I got this error when I tried to git push. 

The cause: I got conflicted version files due to dropbox, in the repo I was working on. 

When this happens you should : 
cd ./.git 

and see what files stored there have a duplicated file and remove it and do some renaming if necessary.

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
