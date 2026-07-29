---
title: 'error: src refspec master does not match any. error: failed to push some refs to ''https://github.com/XXXX.git'''
date: 2016-04-21T14:49:00.003-07:00
draft: false
url: /2016/04/error-src-refspec-master-does-not-match.html
---

> **Archived note — originally created: 2016-04-21 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


error: src refspec master does not match any.

error: failed to push some refs to 'https://github.com/XXX.git'

That is the error message I got when trying to git push a newly created folder.

Then I realized that the repository got no file tracked although I git init'ed the folder.

After git add'ing the files in the folder, I git push'ed again and it worked.

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
