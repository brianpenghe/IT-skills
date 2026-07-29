---
title: '"No package ''gtextutils'' found" even after you installed it '
date: 2015-11-05T13:38:00.001-08:00
draft: false
url: /2015/11/no-package-gtextutils-found-even-after.html
---

> **Archived note — originally created: 2015-11-05 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


然後我才恍然大悟....原來說明頁面一開始就叫我直接打一行字

```
 **\# export PKG\_CONFIG\_PATH=/usr/local/lib/pkgconfig:$PKG\_CONFIG\_PATH**
```

```
打完再進行Fastx-toolkit的./configure
``````
OK了....就這麼簡單....我看了快一小時....哀哀....初學者淡淡的哀傷 
```

```
zz from 
``````

[小安的隨意筆記](http://hwouhwou.blogspot.com/)
===========================================

```

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
