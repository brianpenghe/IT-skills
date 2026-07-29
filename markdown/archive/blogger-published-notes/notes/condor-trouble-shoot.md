---
title: 'condor trouble shoot'
date: 2017-04-18T19:48:00.004-07:00
draft: false
url: /2017/04/condor-trouble-shoot.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


Always Idle:   server has bad parts 
condor\_status. 
          (1) No output --> something wrong 
          (2) All claimed ---> good and wait 
          (3) LoadAv above number of cpu 

Held: 
condor\_q -better-analyze -global 
The end of the Hold reason contains the likely error message 

             (1)Permission denied
---------------------------------

If you get this on a script, it's checking to see if the file is "executable" which means it's permissions look like:

```
~$ ls -l script.py 
\-rwxrwxr-x 1 diane diane 103 2009-11-12 14:24 script.py\*
```

(Note the 'x'es in the first column. those tell the operating system and condor that the owning user (first x), the owning group (second x) and everyone else (third x). can run this script.

However if you just change the permissions, you're likely to run into the [Failed to execute <script>](https://woldlab.caltech.edu/wiki/Condor/Troubleshooting#Failed_to_execute_.3Cscript.3E) error. So you should just go read that solution now.

             (2)Failed to execute <script>
------------------------------------------

This can happen to a variety of scripts, shell scripts, python scripts, etc. Basically anything that is not a binary executable. The discussion below assumes a python script.

condor doesn't know that '.py's should be run with the python interpreter. So you have two choices for how to tell it.

One is to change the permissions of eland\_results... to include the "executable" bit with something likechmod a+g eland\_results... (or chmod 755 eland\_results). which should change the ls -l output from

```
\-rw-r--r-- 1 user user 953 2010-01-09 15:31 eland\_results\_to\_fasta\_input.py
```

to:

```
\-rwxr-xr-x 1 user user 953 2010-01-09 15:31 eland\_results\_to\_fasta\_input.py
```

in addition if using this method you'll also need to add:

# !/usr/bin/env python

to the top of the file. The advantage to this is now linux will know that this is an executable and you can run it with eland\_results\_to\_fasta\_input.py args.. from the shell as well. (leaving off the python.)

The other choice is to change the executable in the condor submit script from eland\_results\_to\_fasta\_input.py to python and treat eland\_results\_to\_fasta\_input.py as the first argument in the condor submit script.

#Always-Idle #Python #Linux #Caltech #TroubleshootNotes #BloggerPublishedNonAcademicNotes
