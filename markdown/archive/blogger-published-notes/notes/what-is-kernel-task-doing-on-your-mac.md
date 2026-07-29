---
title: 'What is Kernel_task doing on your Mac'
date: 2015-01-06T23:43:00.001-08:00
draft: false
url: /2015/01/what-is-kerneltask-doing-on-your-mac.html
---

> **Archived note — originally created: 2015-01-06 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


"Ultimately there is not much you can do to affect how kernel\_task runs"  

reference: 
http://www.cnet.com/news/kerneltask-taking-up-ram-in-os-x/ 

Kernel\_task taking up RAM in OS X
==================================

In OS X you may find the process "kernel\_task" taking up a large amount of RAM. Here is why this is happening and what you can do about it.

* by [Topher Kessler](http://www.cnet.com/profiles/tkessler/)
* August 12, 2011 3:56 PM PDT

* [

 comments

 0](http://www.cnet.com/news/kerneltask-taking-up-ram-in-os-x/#comments) 
* [

 facebook

 ](https://www.blogger.com/null) 
* [

 twitter

 ](https://www.blogger.com/null) 
* [

 linkedin

 ](https://www.blogger.com/null) 
* [

 googleplus

 ](https://www.blogger.com/null) 
* more

 more +

![](http://cnet2.cbsistatic.com/hub/i/r/2011/08/12/74b0eb85-fdb7-11e2-8c7c-d4ae52e62bcc/resize/620x/de1d7579affd1aed18c5a3717ec3946c/FinderIconX.png)

If you launch the Activity Monitor utility on your Mac, you will be able to see what processes are running and what system resources they are using. As expected, some processes will take up more RAM and CPU time than others. Seeing this in Activity Monitor can be handy for figuring out which tasks are taking up an unexpected amount of CPU or RAM. One regular culprit for using a lot of RAM is Safari, but in addition you will see another process called "kernel\_task" that also will regularly use a few hundred megabytes of real RAM and seem to increase its RAM footprint with system usage.

The kernel in OS X is the software architecture that is responsible for handling resources that processes and programs need. These include the management of multitasking scheduling, virtual memory, system input and output, and various communication routines between processes. In addition, the kernel can be modified and given enhanced functionality by loading kernel extensions (kexts) to supply system-level management of features like Bluetooth and Wi-Fi, graphics processors, third-party hardware, access to peripheral devices, and special filesystem support. In essence, the kernel is responsible for running your hardware and making the hardware resources available to applications and system services.

[![Activity Monitor](http://www.cnet.com/news/kerneltask-taking-up-ram-in-os-x/)](http://i.i.cbsi.com/cnwk.1d/i/tim/2011/08/12/Kernel_Task.png)

Beside Safari and some other applications, the process "kernel\_task" may take up a large amount of system memory (click for larger view).

When the system starts up, even though you may have kernel extensions loaded, not all of the services are active. The system may be ready to use them, but will not load them fully until needed. Therefore, if you initially start up your system and check Activity Monitor, you may see the kernel\_task process taking up a relatively small amount of RAM. When you then start using your system and activating features like your iSight camera, Wi-Fi services, switching GPUs, and using external devices, then the kernel\_task will make use of the resources for these devices and will grow in size.

For instance, on my [MacBook Pro](http://www.cnet.com/products/apple-macbook-pro-with-retina-display-2013-15-inch-screen/) running OS X 10.7 Lion, an initial boot will show the kernel\_task process taking up 330-340MB of RAM. The task will idle with this level of RAM until you decide to do something with your system, so if I open a few applications (Word, Pages, iCal, [Safari](http://download.cnet.com/mac/browsers/), Preview, etc.) then the amount of RAM used by the kernel\_task increases to around 370MB. At this point the system has loaded and interacted with some services these programs need (networking, authentication, firewall, graphics, and user input), so the kernel\_task has increased its RAM footprint to accommodate those tasks being active. If the programs are quit, the kernel\_task does not relinquish the new RAM it's using, since the system services are still active even though the programs themselves are not. On subsequent launches of these programs; however, the RAM footprint does not increase any further.

As with running applications, general use of the system will also increase kernel\_task RAM usage. For instance, enabling Bluetooth and Wi-Fi will bump it up about 3-4MB, browsing the filesystem will boost it around 25-30MB, and enabling the onboard GPU (which uses system memory for video RAM) will initially give around a 20-25MB increase in RAM usage, but this will rise further as you perform tasks like playing 3D games, or watch large movie files when using this GPU.

While some of the kernel\_task services will not unload when you quit the processes that have started them, others will, especially if they are managing hardware in the system. For instance, on systems with multiple GPUs, if you use the onboard GPU, then you will see an increase in RAM usage by the kernel\_task, but unlike some applications services, if you switch graphics processing back to the dedicated GPU, then the kernel\_task will relinquish the RAM it was using for video memory. Likewise, if you have activated your iSight camera with a program like Photo Booth, then the kernel\_task will use another 8-10MB of RAM, which will be relinquished when Photo Booth is shut down.

Ultimately there is not much you can do to affect how kernel\_task runs and manages the system. If you see the kernel\_task process taking up a large amount of RAM on your system, there are a few options to reduce the RAM other than restarting your system. The first is to disable any hardware devices you may have attached to your system, such as external monitors, hard drives, or third-party audio or video interfaces. In addition, you can disable services like Wi-Fi and Bluetooth if you are not using them, and switch to using discrete graphics instead of the onboard GPU. The second thing you can do is quit programs and system services that use kernel extensions, such as the aforementioned Photo Booth, or graphics processing programs and games, especially if you are running with the integrated graphics card.

#download #TroubleshootNotes #BloggerPublishedNonAcademicNotes
