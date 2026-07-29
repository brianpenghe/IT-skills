---
title: 'How to selectively save standard err messages / skip progress bars'
date: 2016-01-29T13:47:00.000-08:00
draft: false
url: /2016/01/how-to-selectively-save-standard-err.html
---

> **Archived note — originally created: 2016-01-29 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


One way is look for the flags of the program you use, there should have a quiet version. 
If it doesn't work, you could do this: 

$ find . -name "my.txt" 2>&1 | grep -v "Permission denied"

The above command will suppress only "Permission denied" warning message, and show any other warning or error messages unfiltered.

reference: 

http://xmodulo.com/how-to-suppress-warning-or-error-messages-in-find-command.html

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
