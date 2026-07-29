> **Archived note — originally created: 2019-08-16 — old (5–8 years) — verify carefully**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---

* 20221004 New update: just follow this https://support.microsoft.com/en-us/office/add-an-email-account-to-outlook-6e27792a-9267-4aa4-8bb6-c84ef146101b#PickTab=Outlook_for_Mac

---
title: 'How to set up Cambridge University email on Outlook'
date: 2019-08-16T15:47:00.001-07:00
draft: false
url: /2019/08/how-to-set-up-cambridge-university.html
---

I'm using my outlook (version 16.16.10) on my Mac (Mojave 10.14.3) 

Cambridge UIS didn't provide a working tutorial for me. So I'm writing down the correct version in case someone needs it: 

1\. Open outlook -> Tools --> Accounts 
2\. Click the + on bottom left -> new account 
3\. Type your XXX@cam.ac.uk email, click continue , then quickly click "choose the provider" 
4\. Select IMAP/POP . (Don't select Exchange or 365) 
5\. Then fill the form based on these instructions: 

* **Email address:** Your CRSid@cam.ac.uk email address – e.g. xyz123@cam.ac.uk
* **User name:** Your CRSid – e.g. xyz123
* **Password:** Your password for Hermes (this might not be the same as your Raven password)

* **Incoming Server:** imap.hermes.cam.ac.uk
* **Port:** 993
* **Security/Encryption:** SSL

* **Outgoing Server:** smtp.hermes.cam.ac.uk
* **Port:** 587
* **Security/Encryption:** STARTTLS （optional）

Then it's done!

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
