---
title: '[solved]There is a problem with your sound card. Spotify can''t play music. Especially when you use external audio devices'
date: 2014-10-30T20:37:00.000-07:00
draft: false
url: /2014/10/solvedthere-is-problem-with-your-sound.html
---

> **Archived note — originally created: 2014-10-30 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


**On Spotify's forum the solution is:**

Here is how I fixed the problem with my Dell laptop:

Go to Control Panel and navigate your way to Device Manager.

Expand Sound, Video and game controllers.

My problem was with the IDT High Definition Audio CODEC.  (Yours may be another device name.)  Even though the driver was up to date and the card works fine for other things (such as pandora), I had to uninstall the device.

Right click your device and click Uninstall.  Click OK when it asks you if you are sure.

Now right click on the Sound, video and game controllers label and click 'scan for hardware changes'.  It should detect your hardware and automatically install the drivers.

If you have trouble re-installing your drivers, go to your computer manufacturers website and download the drivers and install them that way.

But what really SOLVED the problem was:

After tried what's described above, I force quit the spotify using task manager (right click the bottom bar)

And restart it.

#download #TroubleshootNotes #BloggerPublishedNonAcademicNotes
