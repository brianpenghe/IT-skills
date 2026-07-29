---
title: '[Solved] Application Blocked by Java Security'
date: 2016-05-12T14:36:00.004-07:00
draft: false
url: /2016/05/solved-application-blocked-by-java.html
---

> **Archived note — originally created: 2016-05-12 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


_For security, applications must now meet the requirements for the Hig or very High security settings, or be part of the Exception Site List, to be allowed to run_ 
_Reasons: Your security settings have blocked a self-signed application from running_ 

These were the Java messages I got when using IE on Windows 8.2 

The solution: 

**_Startmenu_**_ >>**Java** >>**Configure Java** >> **Security** >> **Edit site list** >> **copy and paste your website link** >> **restart your browser**_ 
_**or**_ 
_**search the java configure, open it and add your website address to the exception list, restart your browser**_

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
