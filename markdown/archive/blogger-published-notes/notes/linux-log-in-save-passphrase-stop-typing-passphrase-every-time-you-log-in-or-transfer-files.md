---
title: 'Linux log in save passphrase. Stop typing passphrase every time you log in or transfer files'
date: 2019-07-16T05:06:00.000-07:00
draft: false
url: /2019/07/linux-log-in-save-passphrase-stop.html
---

> **Archived note — originally created: 2019-07-16 — old (5–8 years) — verify carefully**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


Just edit this file: ~/.ssh/config, 
add these: 

```
Host * 
 UseKeychain yes
```reference: 
https://stackoverflow.com/q/10032461/3020740

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
