---
title: 'Xtrafinder fails to work on Mac OS X El Capitan due to integrity protection | how to open folders in tabs'
date: 2016-05-05T21:57:00.003-07:00
draft: false
url: /2016/05/xtrafinder-fails-to-work-on-mac-os-x-el.html
---

> **Archived note — originally created: 2016-05-05 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


Two solutions to open folders in tabs: 
1\. disable the integrity protection: 

```
1\. Boot to Recovery OS by restarting your machine and holding down the Command and R keys at startup. 
2\. Launch Terminal from the Utilities menu. 
3\. Enter the following command: csrutil enable --without debug 
Reboot your computer.
``````
more : http://www.trankynam.com/xtrafinder/sip.html
``````

``````

``````
2\. Use Finder's tab feature:
``````

``````
Go to Finder:
``````
Finder -> preferences --> check the box for "Open folders in tabs instead of new windows"
``````

``````
When you open a folder, please press command key and double click on the folder.
``````

```

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
