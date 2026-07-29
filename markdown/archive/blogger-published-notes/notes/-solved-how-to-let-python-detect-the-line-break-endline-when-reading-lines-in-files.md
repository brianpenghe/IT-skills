---
title: '[solved]How to let python detect the line break / endline when reading lines in files'
date: 2015-01-25T23:10:00.002-08:00
draft: false
url: /2015/01/solvedhow-to-let-python-detect-line.html
---

> **Archived note — originally created: 2015-01-25 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


[up vote](https://www.blogger.com/null "This answer is useful")17[down vote](https://www.blogger.com/null "This answer is not useful")

Simple. Use **splitlines()**

```
L = open("myFile.txt", "r").read().splitlines(); 
for line in L: process(line) # this 'line' will not have '\n' character at the end
```

[share](http://stackoverflow.com/a/339579/3020740 "short permalink to this answer")[edit](http://stackoverflow.com/posts/339579/edit "revise and improve this post")

answered Dec 4 '08 at 4:13

[

![](https://www.gravatar.com/avatar/91160e88d86db6328f3e81313ae500c6?s=32&d=identicon&r=PG)

](http://stackoverflow.com/users/27474/vijay-dev)

[Vijay Dev](http://stackoverflow.com/users/27474/vijay-dev) 
6,844144579

#Python #TroubleshootNotes #BloggerPublishedNonAcademicNotes
