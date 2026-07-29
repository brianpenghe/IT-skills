---
title: '[Solved] Git merge: Already up-to-date'
date: 2015-11-01T17:24:00.000-08:00
draft: false
url: /2015/11/solved-git-merge-already-up-to-date.html
---

> **Archived note — originally created: 2015-11-01 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


git checkout Feature1 
git merge master 

This didn't work for me 

Because I didn't clearly understand the concept of merging. 

Merging requires you to have progress on both branches, while my master branch only had a root. 
Therefore, the solution: 
git checkout master 
then added a space or so to modify the script. 
git checkout Feature1 
git merge master 

This worked! 

"there are some caveats that probably explain why you don't see anything: 

\- if you checked out Branch1 out of master, and didn't do anything, 
  then there's nothing to merge. 

\- if you checked out Branch1 out of master, then did something, 
  and merged master into it, then again there's nothing to do. 

\- if you checked out Branch1 out of master, then did something on it, 
  then merged it back into master (by checking out master and merging Branch1), 
  then it will be "fast forwarded", because they have not diverged, 
  so there won't be any "merge commit". " ---- Filippidis I. 

more information: https://www.atlassian.com/git/tutorials/merging-vs-rebasing/workflow-walkthrough

#Feature1 #Branch1 #TroubleshootNotes #BloggerPublishedNonAcademicNotes
