---
title: 'Reading a Json String on Linux/Unix Shell? Here''s how I use jq'
date: 2017-04-24T17:22:00.001-07:00
draft: false
url: /2017/04/reading-json-string-on-linuxunix-shell.html
---

> **Archived note — originally created: 2017-04-24 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


This prints out all the fields in your json string:

```
jq keys YourJsonString
```

This prints out the the field called "accession" of all your nodes:

```
jq '.files[].accession' YourJsonString
```

Usually, assuming the outputs follow a constant order, you can juxtapose the fields you need together to make a table by typing this:

```
paste -s <(jq '.files[].href' test) <(jq '.files[].accession' YourJsonString)
```

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
