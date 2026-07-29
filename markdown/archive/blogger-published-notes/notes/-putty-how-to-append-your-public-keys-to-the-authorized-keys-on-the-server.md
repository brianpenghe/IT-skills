---
title: '[PUTTY]How to append your public keys to the authorized_keys on the server'
date: 2015-12-31T11:21:00.000-08:00
draft: false
url: /2015/12/puttyhow-to-append-your-public-keys-to.html
---

> **Archived note — originally created: 2015-12-31 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


after you generate your keys using PUTTYGEN (http://troubleshoo.blogspot.com/2015/12/windowshow-to-create-public-private-key.html) 
1\. you should use the computer that is already able to connect to the server to download your authorized\_keys file from the server. 
Mine is stored at ~/.ssh/authorized\_keys 

2\. Use a text editor to open the authorized\_keys 
 You should see all the keys stored there. The format is like this: 
```
ssh-dss AAAAB3NzaC1kc3MAAACBAN+NX/rmUkRW7Xn7faglC/pxqbVIohbcVOt41VThMYORtMQr 
QSqMZugxew2s9iX4qRowHWLBRci6404nSydLiDe1q6/NmpK+oQ8zD1yXekl+fruBAYeno7f6dM7c 
2swwwXY6knp4umXkLItxIUki6SXM0WfabJ8BwuNDyA8IrbFAAAAFQCynEN3MYXbs4AA7E/1I03jb 
B1rewAAAIAztzZUygrUI8XX6eE4zEHdTbv89AHYsAsf7fSAWnPxWc63dV0P5lCPNk58nze6+N+MD 
X7ZQADT6710fvbOmEFLciTwBGHHLxIV+1iTApJSsQp9T+pdkbFzBZ+mqQamZpSN1hC8fXe/Uty0D 
SbhnQ1qanwrOdKP1JV7DUgzehSfAAAAIEAwAyNYxUsGil46gZQea6sfhUnrBwyM6JnEbA6ogfGdS 
T2TDn1U5rfTV9UuNHzfoZ4CplVHclXyUPPhbKqcedpuRPJhHN/lp5MH7Q2tI/UxHvmePNHrXKk86 
XYt7RzKHjWbHRxf84GIyTlKa8yfNfFlf9oNXdtBXcsJjHIvNsBk= ThisIsAComment
```3\. you should use a texteditor to open your saved public key 
you should see something like this: 
\---- BEGIN SSH2 PUBLIC KEY----- 
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* 
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* 
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* 
\_\_\_ END SSH2 PUBLIC KEY --------- 

4\. copy the text/key that I labeled using \*\*\*\*\*, and paste onto a new line of the authorized\_keys file 
5\. update the file on the server. 

Now your public key is added to the server 

Read more for the public key format: https://wiki.mcs.anl.gov/IT/index.php/SSH\_Keys:authorized\_keys

#download #TroubleshootNotes #BloggerPublishedNonAcademicNotes
