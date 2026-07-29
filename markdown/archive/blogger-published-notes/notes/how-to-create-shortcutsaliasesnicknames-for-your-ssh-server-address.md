---
title: 'How to create shortcuts/aliases/nicknames for your ssh server address'
date: 2018-03-25T19:51:00.001-07:00
draft: false
url: /2018/03/how-to-create-shortcutsaliasesnicknames.html
---

> **Archived note — originally created: 2018-03-25 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


1.   cd ~/.ssh 
2.   nano config 
       # this is to create a file named config 
3.   type your server nickname, address and username into this file and save. An example from https://scotch.io/tutorials/how-to-create-an-ssh-shortcut  
```
Host scotch 
 HostName scotch.io 
 User nick 

Host example2 
 HostName example.com 
 User root
```

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
