---
title: 'Windows 8.1 no connection -- Dropbox connection failure'
date: 2014-06-01T13:58:00.000-07:00
draft: false
url: /2014/06/windows-81-no-connection-dropbox.html
---

> **Archived note — originally created: 2014-06-01 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


The solution is : 
 use google DNS, enable public access of dropbox on windows firewall and restart. 

How to use google DNS 

Google Public DNS is the preferred DNS and is known for being fast, accurate and no restriction.

Step 1 – Navigate to Control Panel  >>  Network and Internet  >> Network and Sharing Center  >>  Change Adapter Settings.

Step 2 – Select the connection that you want to configure Google Public DNS.

For example: 
– To change the settings for an Ethernet connection, right-click Local Area Connection, and click Properties. 
– To change the settings for a wireless connection, right-click Wireless Network Connection, and click Properties.

![](http://thewindowsclub.thewindowsclubco.netdna-cdn.com/wp-content/uploads/2009/12/dnssettings-600x480.png)

Step 3 – Click on the Networking tab. Click on Internet Protocol Version 4 (TCP/IPv4) and then Properties.

Step 4 – Click on Advanced and then DNS tab.

If there is an existing IP address listed here, do write them down for future reference.

For Google Public DNS, select Use the following DNS server addresses:

Preferred DNS Server: 8.8.8.8

Alternate DNS Server: 8.8.4.4

Step 5 – Click OK and restart your network connection for changes to be applied.

You are now using Google Public DNS.

(original article: http://www.ipserverone.info/dns-2/change-dns-settings-to-google-dns-in-windows-7-8/)

#Preferred-DNS-Server #Alternate-DNS-Server #TroubleshootNotes #BloggerPublishedNonAcademicNotes
