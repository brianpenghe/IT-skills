---
title: 'Team viewer Stuck at initializing display parameters'
date: 2019-06-04T05:51:00.004-07:00
draft: false
url: /2019/06/team-viewer-stuck-at-initializing.html
---

> **Archived note — originally created: 2019-06-04 — old (5–8 years) — verify carefully**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


When I tried to remote-control my other computer, the connection was established but the pop-up screen was stuck with the pending message "initializing display parameters". This didn't occur earlier. So it must have been runtime errors instead of wrong settings. 

The solution: 
Use task manager on PC or Activity Monitor(search that app and open it) on Mac and stop all the TeamViewer processes on the computer you are using to control other computers. Restart the software, wait till it's ready, connet, and it might work. 

This solution is actually Method 6 of an article. More scenarios can be find there: 
[https://appuals.com/fix-teamviewer-stuck-on-initializing-display-parameters/](https://appuals.com/fix-teamviewer-stuck-on-initializing-display-parameters/)

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
