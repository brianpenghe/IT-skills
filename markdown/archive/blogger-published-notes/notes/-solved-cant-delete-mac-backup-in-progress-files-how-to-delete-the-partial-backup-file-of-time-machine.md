---
title: '[Solved]Can''t delete Mac backup in progress files: how to delete the partial backup file of Time Machine'
date: 2019-02-21T20:46:00.003-08:00
draft: false
url: /2019/02/solvedcant-delete-mac-backup-in.html
---

> **Archived note — originally created: 2019-02-21 — old (5–8 years) — verify carefully**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


A big mistake people usually make is to manually delete a backup that Time Machine has created or has been trying to create. Once you delete it, it will be moved to the trash and get stuck there. You can't empty the trash or put it back. 

One solution is to use Admin permission to completely delete it:

cd /Volumes/(backup drive name)/.Trashes/

sudo ls 501/

sudo rm -rf 501/Backups.backupdb/

More information is here:

http://osxdaily.com/2013/08/12/delete-time-machine-backups-empty-trash/

Correct way to delete old backup: 
[https://www.makeuseof.com/tag/delete-old-time-machine-backups/](https://www.makeuseof.com/tag/delete-old-time-machine-backups/)

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
