---
title: 'Basic Condor commands '
date: 2015-09-14T22:50:00.001-07:00
draft: false
url: /2015/09/basic-condor-commands.html
---

> **Archived note — originally created: 2015-09-14 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


# # # from: http://www.rcc.uh.edu/hpc-docs/134-basic-condor-commands.html

# # # 

# # # 

# # # Condor Commands to Submit and Monitor Jobs

These are some frequently used commands. For complete documentation on Condor commands, refer to the online man page: type **man** _command _at the shell prompt. Or review them all in the [Command Reference Manual](http://www.cs.wisc.edu/condor/manual/v7.0/9_Command_Reference.html) at the Condor Project website.

# # # # Frequently Used Condor Commands

# # # # Basic Usage

# # # # Example

**condor\_submit**

submit a job

condor\_submit  \[_submit file_\]

```
$ condor\_submit job.condor
```

**condor\_q**

show status of jobs

condor\_q \[_cluster_\]

```
$ condor\_q 1170
```

**condor\_rm**

remove jobs from the queue

condor\_rm \[_cluster_\]

```
$ condor\_rm 1170 
```

**condor\_hold**

hold jobs in the queue

condor\_hold \[_cluster_\]

```
$ condor\_hold 1170
```

**condor\_release**

release jobs in the queue

condor\_release \[_cluster_\]

```
$ condor\_release 1170
```

**condor\_prio**

change priority of queued jobs

condor\_prio \[_cluster_\]

```
$ condor\_prio 1170
```

**condor\_compile**

relink an executable for the standard universe

condor\_ compile \[cc | f77 | g++  | make | ...\] ...

```
$ condor\_compile cc whetstone.c -lm
```

# # # # Commands to Monitor Job Status

**condor\_q**

list your jobs

**condor\_q -global**

list all jobs

**condor\_q -submitter **_submitter\_id_

list jobs for _submitter\_id_

**condor\_q -run**

list running jobs

**condor\_status -state -total**

list summary of pool resources

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
