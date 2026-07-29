---
title: 'Prevent your Mac terminal from Sleeping'
date: 2015-01-06T16:01:00.000-08:00
draft: false
url: /2015/01/prevent-your-mac-terminal-from-sleeping.html
---

> **Archived note — originally created: 2015-01-06 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


Portable Macs by default are set up so that they will sleep whenever you close the lid, unless they are plugged into an external monitor, keyboard, and mouse. But, sometimes you want your Mac to be doing work while the lid is closed when you are not in this situation. With a simple Terminal command, you can easily make your Mac stay awake so that apps will remain running while you carry your MacBook around.

# # # Caffeinate Your Mac

[![](http://www.maclife.com/files/u12635/caffeinate_1.png)](http://www.maclife.com/files/u12635/caffeinate_1.png)

To begin running the caffeinate command and prevent your Mac from sleeping, open the Terminal located in /Applications/Utilities, then type the following command:

```
caffeinate
```

While this command is running, you will be able to close the lid on your Mac and still have OS X and your apps running and performing their tasks just as you would if the lid were to remain open.

# # # Caffeinate Your Mac for a specified length of time

[![](http://www.maclife.com/files/u12635/caffeinate_2.png)](http://www.maclife.com/files/u12635/caffeinate_2.png)

What if you only wish to caffeinate your Mac for a specific number of seconds? The caffeinated command can do your bidding here, as well:

```
caffeinate -u -t 600
```

With the command above, replace "600" with the number of seconds that you wish the caffeinated command to run. Running this command as-is will cause your Mac to prevent sleeping for 10 minutes (600 seconds). 

Once starting this command, your Mac will be prevented from sleeping for the set amount of time, and will automatically terminate the caffeinate program afterwards, which will cause your Mac to go to sleep soon thereafter.

# # # Cancel the Caffeine

To make the caffeinate command stop running and return your Mac to normal using either of the methods above, simply return to the command line and press the Control + C keyboard combination.

# # # A Warning

You shouldn't keep your Mac running with the lid closed and place it inside of a bag. Doing so will cause heat to build up and could cause damage to your MacBook. 

_Cory Bohon is a freelance technology writer, indie Mac and iOS developer, and amateur photographer. [Follow this article's author on Twitter](http://twitter.com/coryb)._

#MACS2 #TroubleshootNotes #BloggerPublishedNonAcademicNotes
