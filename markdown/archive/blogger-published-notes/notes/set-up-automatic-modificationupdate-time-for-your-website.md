---
title: 'set up automatic modification/update time for your website'
date: 2018-05-19T15:46:00.002-07:00
draft: false
url: /2018/05/set-up-automatic-modificationupdate.html
---

> **Archived note — originally created: 2018-05-19 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


If you want to make the "last updated" info on your website automatically generated, you may use these codes: 

> the script tag should look like <script type="text/javascript"> 
> 
> also it is preferable to use the dom to insert content into the page, not document.write. 
> 
> in the head: 
> 
> PHP:
> 
> `<script type="text/javascript">onload = function(){ 
>     document.getElementById("lastModified").innerHTML = "Page last changed " + document.lastModified.split(" ")[0]; 
> }</script>`
> 
> later on in the body: 
> 
> 
> HTML:
> 
> ```
> <span id="lastModified"></span>
> ```
> 
> good read: [http://www.quirksmode.org/js/lastmod.html](http://www.quirksmode.org/js/lastmod.html)

These are copied from here: https://forums.techguy.org/threads/how-can-i-get-an-automatic-last-updated-in-my-web-page.693929/

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
