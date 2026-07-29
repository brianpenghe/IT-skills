---
title: 'Hypergeometric probability explained in multiple ways that are all equivalent'
date: 2017-04-03T14:09:00.000-07:00
draft: false
url: /2017/04/hypergeometric-probability-explained-in.html
---

> **Archived note — originally created: 2017-04-03 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


1\. Definition: 
Mitch is doing a large scale of lncRNA genes that are involved in cancer. We know there are altogether M lncRNA genes, N of which are on his screen list and God who knows everything knows that K out of M lncRNA genes are what God designed for cancer. Assuming Mitch's screen is correctly done. Now the number (x) of genes related to cancer screened by Mitch should follow a hypergeometric distribution. 

2\. On Mitch's side (Mitch doesn't know God's design) 
The probability of getting x hits from the list of N genes from a pool of M genes has to meet these conditions 
    x genes chosen from K cancer genes 
    N-x genes chosen from M-K non-cancer genes 
    altogether N genes chosen from M genes 
so the probability should be C(k,x)\*C(M-K,N-x)/C(M,N) 

3\. On God's side (God didn't know Mitch's screening list when he chose the cancer genes to be cancer-causing) 
The probability of getting x hits from the list of K cancer genes from a pool of M genes has to meet these conditions 
   x Mitch cancer genes chosen from K cancer genes 
   K-x Non-Mitch cancer genes were among the M-N non-Mitch-screen genes 
   altogether K cancer genes chosen from M genes 
so the probability should be C(N,x)\*C(M-N,K-x)/C(M,K) 

4\. These two probability formula are equivalent (equal). In other words, God and Mitch, both not aware of each other's act, have a mathematicallly symmetric position. 
   (To prove this you can just expand the combinations into factorials)

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
