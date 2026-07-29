---
title: 'Find your IP Address on a Mac '
date: 2013-10-30T00:07:00.001-07:00
draft: false
url: /2013/10/find-your-ip-address-on-mac.html
---

> **Archived note — originally created: 2013-10-30 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


* Type the following command:

`ifconfig |grep inet`

* You will see something that looks like this:

`inet6 ::1 prefixlen 128 
inet6 fe80::1%lo0 prefixlen 64 scopeid 0x1 
inet 127.0.0.1 netmask 0xff000000 
inet6 fe80::fa1e:dfff:feea:d544%en1 prefixlen 64 scopeid 0x5 
inet 192.168.0.100 netmask 0xffffff00 broadcast 192.168.0.255`

* Your IP address is usually next to the last entry of ‘inet’ and in this case is 192.168.0.100, an IP address is always in the format of x.x.x.x but it will never be 127.0.0.1 because that is your machines loopback address. Because you can always ignore 127.0.0.1, this guarantees that your IP address will be the other IP between ‘inet’ and ‘netmask’

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
