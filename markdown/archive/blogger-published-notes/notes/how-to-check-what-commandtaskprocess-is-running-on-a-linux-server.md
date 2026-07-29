---
title: 'How to check what command/task/process is running on a linux server'
date: 2015-11-17T22:39:00.001-08:00
draft: false
url: /2015/11/how-to-check-what-commandtaskprocess-is.html
---

> **Archived note — originally created: 2015-11-17 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


$ ps -ewwo pid,args | grep \[s\]sh 

Source: http://www.cyberciti.biz/faq/unix-linux-determine-whether-process-is-running/ 

Output:

```
5341 /usr/sbin/sshd 
 5864 /usr/bin/ssh-agent x-session-manager 
 6289 ssh oldbox 
 7126 ssh admin@core.r1.vsnl.router 

```

Where,

* **ps** : Command name
* **\-ewwo pid,args** : -e option force to select all running processes. -o option is used to specify user-defined format. In our case we are forcing to display only program pid and its arguments. Finally -w option specifies wide output. Use this option twice for unlimited width.
* **grep \[s\]sh** : We are just filtering out sshd string

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
