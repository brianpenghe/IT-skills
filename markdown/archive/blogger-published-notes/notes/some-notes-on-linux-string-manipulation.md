---
title: 'some notes on Linux string manipulation'
date: 2017-04-18T19:26:00.000-07:00
draft: false
url: /2017/04/some-notes-on-linux-string-manipulation.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


# # # linux bash shell script string manipulation

Bash String Manipulation Examples – Length, Substring, Find and Replace
=======================================================================

# # # 1\. Identify String Length inside Bash Shell Script

```
${#string}
```

The above format is used to get the length of the given bash variable.

```
$ cat len.sh#! /bin/bashvar="Welcome to the geekstuff"echo ${#var}$ ./len.sh24
```

To understand more about bash variables, read [6 Practical Bash Global and Local Variable Examples](http://www.thegeekstuff.com/2010/05/bash-variables/).

# # # 2\. Extract a Substring from a Variable inside Bash Shell Script

Bash provides a way to extract a substring from a string. The following example expains how to parse n characters starting from a particular position.

```
${string:position}
```

Extract substring from $string at $position

```
${string:position:length}
```

Extract $length of characters substring from $string starting from $position. In the below example, first echo statement returns the substring starting from 15th position. Second echo statement returns the 4 characters starting from 15th position. Length must be the number greater than or equal to zero.

```
$ cat substr.sh#! /bin/bashvar="Welcome to the geekstuff"echo ${var:15}echo ${var:15:4}$ ./substr.shgeekstuffgeek
```

Also, refer to our earlier article to understand more about [$\*, $@, $#, $$, $!, $?, $-, $\_ bash special parameters](http://www.thegeekstuff.com/2010/05/bash-shell-special-parameters/).

# # # 3\. Shortest Substring Match

Following syntax deletes the shortest match of $substring from front of $string

```
${string#substring}
```

Following syntax deletes the shortest match of $substring from back of $string

```
${string%substring}
```

Following sample shell script explains the above two shortest substring match concepts.

```
$ cat shortest.sh#! /bin/bashfilename="bash.string.txt"echo ${filename#\*.}echo ${filename%.\*}$ ./shortest.shAfter deletion of shortest match from front: string.txtAfter deletion of shortest match from back: bash.string
```

In the first echo statement substring ‘\*.’ matches the characters and a dot, and # strips from the front of the string, so it strips the substring “bash.” from the variable called filename. In second echo statement substring ‘.\*’ matches the substring starts with dot, and % strips from back of the string, so it deletes the substring ‘.txt’

# # # 4\. Longest Substring Match

Following syntax deletes the longest match of $substring from front of $string

```
${string##substring}
```

Following syntax deletes the longest match of $substring from back of $string

```
${string%%substring}
```

Following sample shell script explains the above two longest substring match concepts.

```
$ cat longest.sh#! /bin/bashfilename="bash.string.txt"echo "After deletion of longest match from front:" ${filename##\*.}echo "After deletion of longest match from back:" ${filename%%.\*}$ ./longest.shAfter deletion of longest match from front: txtAfter deletion of longest match from back: bash
```

In the above example, ##\*. strips longest match for ‘\*.’ which matches “bash.string.” so after striping this, it prints the remaining txt. And %%.\* strips the longest match for .\* from back which matches “.string.txt”, after striping  it returns “bash”.

# # # 5\. Find and Replace String Values inside Bash Shell Script

Replace only first match

```
${string/pattern/replacement}
```

It matches the pattern in the variable $string, and replace only the first match of the pattern with the replacement.

```
$ cat firstmatch.sh#! /bin/bashfilename="bash.string.txt"echo "After Replacement:" ${filename/str\*./operations.}$ ./firstmatch.shAfter Replacement: bash.operations.txt
```

Replace all the matches

```
${string//pattern/replacement}
```

It replaces all the matches of pattern with replacement.

```
$ cat allmatch.sh#! /bin/bashfilename="Path of the bash is /bin/bash"echo "After Replacement:" ${filename//bash/sh}$ ./allmatch.shAfter Replacement: Path of the sh is /bin/sh
```

Taking about find and replace, refer to our earlier articles – [sed substitute examples](http://www.thegeekstuff.com/2009/09/unix-sed-tutorial-replace-text-inside-a-file-using-substitute-command/) and [Vim find and replace](http://www.thegeekstuff.com/2009/04/vi-vim-editor-search-and-replace-examples/).

Replace beginning and end

```
${string/#pattern/replacement
```

Following syntax replaces with the replacement string, only when the pattern matches beginning of the $string.

```
${string/%pattern/replacement
```

Following syntax replaces with the replacement string, only when the pattern matches at the end of the given $string.

```
$ cat posmatch.sh#! /bin/bashfilename="/root/admin/monitoring/process.sh"echo "Replaced at the beginning:" ${filename/#\\/root/\\/tmp}echo "Replaced at the end": ${filename/%.\*/.ksh}$ ./posmatch.shReplaced at the beginning: /tmp/admin/monitoring/process.shReplaced at the end: /root/admin/monitoring/process.ksh
```

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
