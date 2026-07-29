---
title: '[Solved] Windows 10 Uninstall Candy Crush Saga'
date: 2015-12-26T21:39:00.001-08:00
draft: false
url: /2015/12/solved-windows-10-uninstall-candy-crush.html
---

> **Archived note — originally created: 2015-12-26 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


1\. in the search box type Powershell to enter the windows powershell (the terminal) 
2\. In the powershell window type the following command line: 

Get-AppxPackage -Name king.com.CandyCrushSaga 

3\. In your window you should see the details of your installed CandyCrushSaga. Mine is : 

Name              : king.com.CandyCrushSaga 
Publisher         : CN=F80C3B33-B9E8-4F23-AB15-B97C700EFF2F 
Architecture      : X86 
ResourceId        : 
Version           : 1.668.0.0 
PackageFullName   : **king.com.CandyCrushSaga\_......** 
InstallLocation   : C:\\Program 
..... 
..... 
...... 

4\. Use your mouse to highlight the package name to the right of "PackageFullName" and use ctrl + C to copy it 

5\. type Remove-AppxPackage, space and paste (ctrl + v) the package name you just copied. 
Mine command was: 
Remove-AppxPackage king.com.CandyCrushSaga\_1.668....................fvs32 

Reference: 
www.winbeta.org/news/how-to-remove-candy-crush-saga-from-windows-10

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
