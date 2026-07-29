---
title: 'Git: fastforward --- Define your finished branch to be master branch'
date: 2016-02-14T23:04:00.000-08:00
draft: false
url: /2016/02/git-fastforward-define-your-finished.html
---

> **Archived note — originally created: 2016-02-14 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


![Hotfix branch based on `master`.](https://git-scm.com/book/en/v2/book/03-git-branching/images/basic-branching-4.png)

Figure 3-13. Hotfix branch based on `master`

You can run your tests, make sure the hotfix is what you want, and merge it back into your `master`branch to deploy to production. You do this with the `git merge` command:[](https://www.blogger.com/null)

```
`$` git checkout master 
`$` git merge hotfix 
`Updating f42c576..3a0874c` 
`Fast-forward` 
 `index.html | 2 ++` 
 `1 file changed, 2 insertions(+)`
```

You’ll notice the phrase “fast-forward” in that merge. Because the commit pointed to by the branch you merged in was directly upstream of the commit you’re on, Git simply moves the pointer forward. To phrase that another way, when you try to merge one commit with a commit that can be reached by following the first commit’s history, Git simplifies things by moving the pointer forward because there is no divergent work to merge together – this is called a “fast-forward.”

Your change is now in the snapshot of the commit pointed to by the `master` branch, and you can deploy the fix.

![`master` is fast-forwarded to `hotfix`.](https://git-scm.com/book/en/v2/book/03-git-branching/images/basic-branching-5.png)

Figure 3-14. `master` is fast-forwarded to `hotfix`

`reference: https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging`

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
