---
title: '[Solved]On JupyterHub''s linux terminal, can''t activate my conda environment'
date: 2021-04-10T09:19:00.006-07:00
draft: false
url: /2021/04/on-jupyterhubs-linux-terminal-cant.html
---

> **Archived note — originally created: 2021-04-10 — old (5–8 years) — verify carefully**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


[![](https://1.bp.blogspot.com/-dP8g48a8APU/YHHP0NwdaUI/AAAAAAAAMd4/uD9aFlrQ1G8ZFi36sQBIumtJhnwyz4SlwCLcBGAsYHQ/w547-h217/Image%2BPasted%2Bat%2B2021-4-10%2B14-39.png)](https://1.bp.blogspot.com/-dP8g48a8APU/YHHP0NwdaUI/AAAAAAAAMd4/uD9aFlrQ1G8ZFi36sQBIumtJhnwyz4SlwCLcBGAsYHQ/s639/Image%2BPasted%2Bat%2B2021-4-10%2B14-39.png)

"To initialize your shell, run..." 

I ran "conda init bash" and restarted server but still couldn't solve the problem.

The solution from Kelvin: 

in your `~/.bash_profile`

add `source activate root`

right at the top

And then start a new linux terminal session

There was another R issue (see my next blog)

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
