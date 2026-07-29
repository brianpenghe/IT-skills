---
title: 'How to log on server using PUTTY without typing username everytime'
date: 2015-12-31T10:56:00.004-08:00
draft: false
url: /2015/12/how-to-log-on-server-using-putty.html
---

> **Archived note — originally created: 2015-12-31 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


ref: https://www.howtoforge.com/ssh\_key\_based\_logins\_putty

In PuTTY, you can create profiles for connections to your various SSH servers, so you don't have to type in the settings again when you want to connect to a certain server again.

Let's create a profile for our 192.168.0.100 server. Start PuTTY by double-clicking its executable file. You are now in the category Session (see the tree on the left side of the screenshot). Enter 192.168.0.100 under Host Name (or IP address), enter 22 under Port and select SSH under Protocol:

[![](https://www.howtoforge.com/images/ssh_key_based_logins_putty/2.png)](https://www.howtoforge.com/images/ssh_key_based_logins_putty/big/2.png)

Then go to Connection -> Data and specify the username with that you want to log in to your SSH server under Auto-login username. In this article I use root:

[![](https://www.howtoforge.com/images/ssh_key_based_logins_putty/3.png)](https://www.howtoforge.com/images/ssh_key_based_logins_putty/big/3.png)

Then go to Session again. Under Saved Sessions enter a name for the profile, e.g. 192.168.0.100 or any other string that lets you remember for which server the profile is. Then click on Save:

[![](https://www.howtoforge.com/images/ssh_key_based_logins_putty/4.png)](https://www.howtoforge.com/images/ssh_key_based_logins_putty/big/4.png)

The next time you use PuTTY, you can simply select the appropriate profile from the Saved Sessions textarea, click on Load and then Open.

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
