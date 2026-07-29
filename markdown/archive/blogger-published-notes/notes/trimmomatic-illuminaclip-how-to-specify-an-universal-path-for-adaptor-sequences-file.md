---
title: 'trimmomatic ILLUMINACLIP: how to specify an universal path for adaptor sequences file'
date: 2016-09-01T23:13:00.000-07:00
draft: false
url: /2016/09/trimmomatic-illuminaclip-how-to-specify.html
---

> **Archived note — originally created: 2016-09-01 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


A bug for ILLUMINACLIP 0.33: 
They always add a prefix of locations which is the current path,  before the file name you provide. Therefore it assumes that the adaptor file is in the current folder, which is not always true. 

In order to specify a universal location, you can just specify the full path and activate its full path read mode. e.g.  /usr/data/adaptors.fa 

ATTENTION: never use ~ as home because it's not recognized by trimmomatic 0.33

#Trimmomatic #TroubleshootNotes #BloggerPublishedNonAcademicNotes
