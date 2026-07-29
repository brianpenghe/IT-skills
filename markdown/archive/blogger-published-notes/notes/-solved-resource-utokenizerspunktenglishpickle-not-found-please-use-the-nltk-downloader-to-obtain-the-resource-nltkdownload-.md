---
title: '[solved]Resource u''tokenizers/punkt/english.pickle'' not found. Please use the NLTK Downloader to obtain the resource: >>> nltk.download()'
date: 2015-01-20T15:45:00.002-08:00
draft: false
url: /2015/01/solvedresource-utokenizerspunktenglishp.html
---

> **Archived note — originally created: 2015-01-20 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


60[down vote](https://www.blogger.com/null "This answer is not useful")

I had this same problem. Go into a python shell and type:

```
>>> import nltk>>> nltk.download()
```

Then an installation window appears. Go to the 'Models' tab and select 'punkt' from under the 'Identifier' column. Then click Download and it will install the necessary files. Then it should work!

#Python #download #TroubleshootNotes #BloggerPublishedNonAcademicNotes
