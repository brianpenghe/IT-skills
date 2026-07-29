---
title: 'some Linux notes'
date: 2017-04-18T19:26:00.004-07:00
draft: false
url: /2017/04/some-linux-notes.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


# # # \[Bash shell script\]how to join two lists without duplicates in any field/remove duplicates in a field  1\. ask '{print $1}' FILENAME | sort | uniq > TEMP

this command gets the unique contents of field 1 from a table FILENAME

2. while read line

     do

grep $line FILENAME | head -1 >> OUTPUTFILE

done <TEMP

        this command greps the values in field $1 of FILENAME. 

# # # [Ubuntu 怎样截图 how to capture your screen under ubuntu](http://blog.163.com/bsbfans@126/blog/static/45662824201211125335630/ "阅读全文")

用系统自带的Take Screenshot 软件截图（下图左） 

点击：Applications/Accessories/Take Screenshot，会弹出一个窗口。 上面有几个选项： Grab the whole desktop：截取整个桌面。 Grab the current window：截取当前活动窗口。 Grab after a delay of \*\* seconds：\*\*秒之后截取图片，主要用于截取动态图片，如3D特效。 建议：如果是截取当前活动窗口，则在选中Grab the current window之后，最好点击一下你要截取的窗口，最后再点击Take Screenshot按钮。

![Take Screenshot 软件截图](file:///C:/Documents%20and%20Settings/090927/Local%20Settings/Temporary%20Internet%20Files/Content.IE5/NNA15G3G/20080901114229813[1].jpg)

![Take Screenshot 软件截图](https://images.51cto.com/files/uploadimg/20100315/1007090.jpg)

# # # linux terminal keyboard shortcuts 

< **Command line - input** >
----------------------------

`Home or Ctrl + a` 
Move the cursor to the beginning of the current line.

`End or Ctrl + e` 
Move the cursor to the end of the current line.

`Alt + b` 
Move the cursor to the beginning of the current or previous word. Note that while this works in virtual terminals, it may not work in all graphical terminal emulators, because many graphical applications already use this as a menu shortcut by default.

`Alt + f` 
Move the cursor to the end of the next word. Again, like with all shortcuts that use Alt as the modifier, this may not work in all graphical terminal emulators.

`Tab` 
Autocomplete commands and file names. Type the first letter(s) of a command, directory or file name, press `Tab` and the rest is completed automatically! If there are more commands starting with the same letters, the shell completes as much as it can and beeps. If you then press `Tab` again, it shows you all the alternatives.

This shortcut is really helpful and saves a lot of typing! It even works at the lilo prompt and in some X applications.

`Ctrl + u` 
Erase the current line.

`Ctrl + k` 
Delete the line from the position of the cursor to the end of the line.

`Ctrl + w` 
Delete the word before the cursor.

< **Command line - output** >
-----------------------------

`Shift + PageUp` 
Scroll terminal output up.

`Shift + PageDown` 
Scroll terminal output down.

`clear` 
The `clear` command clears all previously executed commands and their output from the current terminal.

`Ctrl + l` 
Does exactly the same as typing the `clear` command.

`reset` 
If you mess up your terminal, use the `reset` command. For example, if you try to cat a binary file, the terminal starts showing weird characters. Note that you may not be able to see the command when you're typing it.

< **Command line - history** >
------------------------------

`history` 
When you type the `history` command, you'll see a list of the commands you executed previously.

`ArrowUp or Ctrl + p` 
Scroll up in the history and edit the previously executed commands. To execute them, press `Enter` like you normally do.

`ArrowDown or Ctrl + n` 
Scroll down in the history and edit the next commands.

`Ctrl + r` 
Find the last command that contained the letters you're typing. For example, if you want to find out the last action you did to a file called "`file42.txt`", you'll press Ctrl + r and start typing the file name. Or, if you want to find out the last parameters you gave to the "`cp`" command, you'll press Ctrl + r and type in "`cp`".

< **Command line - misc** >
---------------------------

`Ctrl + c` 
Kill the current process.

`Ctrl + z` 
Send the current process to background. This is useful if you have a program running, and you need the terminal for awhile but don't want to exit the program completely. Then just send it to background with `Ctrl+z`, do whatever you want, and type the command `fg` to get the process back.

`Ctrl + d` 
Log out from the current terminal. If you use this in a terminal emulator under X, this usually shuts down the terminal emulator after logging you out.

`Ctrl + Alt + Del` 
Reboot the system. You can change this behavior by editing `/etc/inittab` if you want the system to shut down instead of rebooting.

# # # Bash loop examples  

for loop syntax
---------------

Numeric ranges for syntax is as follows:

```
 for VARIABLE in 1 2 3 4 5 .. Ndo command1 command2 commandNdone
```

This type of for loop is characterized by counting. The range is specified by a beginning (#1) and ending number (#5). The for loop executes a sequence of commands for each member in a list of items. A representative example in BASH is as follows to display welcome message 5 times with for loop:

```
 #!/bin/bashfor i in 1 2 3 4 5do echo "Welcome $i times"done
```

Sometimes you may need to set a step value (allowing one to count by two's or to count backwards for instance). Latest **bash version 3.0+** has inbuilt support for setting up ranges:

```
 #!/bin/bashfor i in {1..5}do echo "Welcome $i times"done
```

Bash v4.0+ has inbuilt support for setting up a step value using {START**..**END**..**INCREMENT} syntax:

```
 #!/bin/bashecho "Bash version ${BASH\_VERSION}..."for i in {0..10..2} do echo "Welcome $i times" done
```

Sample outputs:

```
Bash version 4.0.33(0)-release...Welcome 0 timesWelcome 2 timesWelcome 4 timesWelcome 6 timesWelcome 8 timesWelcome 10 times
```

# # # The seq command (outdated)

![](https://figs.cyberciti.biz/warning-40px.png)**WARNING!** The seq command print a sequence of numbers and it is here due to historical reasons. The following examples is only recommend for older bash version. All users (bash v3.x+) are recommended to use the above syntax.

The [seq command](http://www.cyberciti.biz/tips/how-to-generating-print-range-sequence-of-numbers.html) can be used as follows. A representative example in seq is as follows:

```
 #!/bin/bashfor i in $(seq 1 2 20)do echo "Welcome $i times"done
```

There is no good reason to use an external command such as seq to count and increment numbers in the for loop, hence it is recommend that you avoid using seq. The builtin command are fast.

Three-expression bash for loops syntax
--------------------------------------

This type of for loop share a common heritage with the C programming language. It is characterized by a three-parameter loop control expression; consisting of an initializer (EXP1), a loop-test or condition (EXP2), and a counting expression (EXP3).

```
 for (( EXP1; EXP2; EXP3 ))do command1 command2 command3done
```

A representative three-expression example in bash as follows:

```
 #!/bin/bashfor (( c=1; c
```

Sample output:

```
Welcome 1 timesWelcome 2 timesWelcome 3 timesWelcome 4 timesWelcome 5 times
```

How do I use for as infinite loops?
-----------------------------------

Infinite for loop can be created with empty expressions, such as:

```
 #!/bin/bashfor (( ; ; ))do echo "infinite loops \[ hit CTRL+C to stop\]"done
```

Conditional exit with break
---------------------------

You can do early exit with break statement inside the for loop. You can exit from within a FOR, WHILE or UNTIL loop using break. General break statement inside the for loop:

```
 for I in 1 2 3 4 5do statements1 #Executed for all values of ''I'', up to a disaster-condition if any. statements2 if (disaster-condition) then break #Abandon the loop. fi statements3 #While good and, no disaster-condition.done
```

Following shell script will go though all files stored in /etc directory. The for loop will be abandon when /etc/resolv.conf file found.

```
 #!/bin/bashfor file in /etc/\*do if \[ "${file}" == "/etc/resolv.conf" \] then countNameservers=$(grep -c nameserver /etc/resolv.conf) echo "Total ${countNameservers} nameservers defined in ${file}" break fidone
```

# # # Early continuation with continue statement

To resume the next iteration of the enclosing FOR, WHILE or UNTIL loop use continue statement.

```
 for I in 1 2 3 4 5do statements1 #Executed for all values of ''I'', up to a disaster-condition if any. statements2 if (condition) then continue #Go to next iteration of I in the loop and skip statements3 fi statements3done
```

This script make backup of all file names specified on command line. If .bak file exists, it will skip the cp command.

```
 #!/bin/bashFILES="$@"for f in $FILESdo \# if .bak backup file exists, read next file if \[ -f ${f}.bak \] then echo "Skiping $f file..." continue \# read next file and skip cp command fi \# we are hear means no backup file exists, just use cp command to copy file /bin/cp $f $f.bakdone
``````

``````

### 
Flags of set---The set builtin  

`set`

```
set \[-abefhkmnptuvxldCHP\] \[-o option\] \[argument ...\]
```

`-a`

Mark variables which are modified or created for export. 

`-b`

Cause the status of terminated background jobs to be reported immediately, rather than before printing the next primary prompt. 

`-e`

Exit immediately if a command exits with a non-zero status. 

`-f`

Disable file name generation (globbing). 

`-h`

Locate and remember (hash) commands as functions are defined, rather than when the function is executed. 

`-k`

All keyword arguments are placed in the environment for a command, not just those that precede the command name. 

`-m`

Job control is enabled (see section [Job Control](http://snap.nlc.dcccd.edu/reference/bash1/features_32.html#SEC32)). 

`-n`

Read commands but do not execute them. 

`-o option-name`

Set the flag corresponding to option-name:

`allexport`

same as `-a`. 

`braceexpand`

the shell will perform brace expansion (see section [Brace Expansion](http://snap.nlc.dcccd.edu/reference/bash1/features_11.html#SEC11)). 

`emacs`

use an emacs-style line editing interface (see section [Command Line Editing](http://snap.nlc.dcccd.edu/reference/bash1/features_41.html#SEC41)). 

`errexit`

same as `-e`. 

`histexpand`

same as `-H`. 

`ignoreeof`

the shell will not exit upon reading EOF. 

`interactive-comments`

allow a word beginning with a \`#' to cause that word and all remaining characters on that line to be ignored in an interactive shell. 

`monitor`

same as `-m`. 

`noclobber`

same as `-C`. 

`noexec`

same as `-n`. 

`noglob`

same as `-f`. 

`nohash`

same as `-d`. 

`notify`

same as `-b`. 

`nounset`

same as `-u`. 

`physical`

same as `-P`. 

`posix`

change the behavior of Bash where the default operation differs from the Posix 1003.2 standard to match the standard. This is intended to make Bash behave as a strict superset of that standard. 

`privileged`

same as `-p`. 

`verbose`

same as `-v`. 

`vi`

use a `vi`\-style line editing interface. 

`xtrace`

same as `-x`.

* \-p Turn on privileged mode. In this mode, the `$ENV` file is not processed, and shell functions are not inherited from the environment. This is enabled automatically on startup if the effective user (group) id is not equal to the real user (group) id. Turning this option off causes the effective user and group ids to be set to the real user and group ids.

* \-t Exit after reading and executing one command.

* \-u Treat unset variables as an error when substituting.

* \-v Print shell input lines as they are read.

* \-x Print commands and their arguments as they are executed.

* \-l Save and restore the binding of the name in a `for` command.

* \-d Disable the hashing of commands that are looked up for execution. Normally, commands are remembered in a hash table, and once found, do not have to be looked up again.

* \-C Disallow output redirection to existing files.

* \-H Enable ! style history substitution. This flag is on by default.

* \-P If set, do not follow symbolic links when performing commands such as `cd` which change the current directory. The physical directory is used instead.

* \-- If no arguments follow this flag, then the positional parameters are unset. Otherwise, the positional parameters are set to the arguments, even if some of them begin with a `-`.

* \- Signal the end of options, cause all remaining arguments to be assigned to the positional parameters. The `-x` and `-v` options are turned off. If there are no arguments, the positional parameters remain unchanged.

Using \`+' rather than \`-' causes these flags to be turned off. The flags can also be used upon invocation of the shell. The current set of flags may be found in `$-`. The remaining N arguments are positional parameters and are assigned, in order, to `$1`, `$2`, .. `$N`. If no arguments are given, all shell variables are printed.

### concatenate two strings in bash  

```
 `foo="Hello" foo=$foo" World" echo $foo >HelloWorld` 
```

In general to concatenate two variables you can just write them one after another:

```
 `a='hello' b='world' c=$a$b 
echo $c > helloworld`
``````

``````

# # # 
All about redirection---stderr, stdout... 2>  

3.1 Theory and quick reference
---------------------------------

There are 3 file descriptors, stdin, stdout and stderr (std=standard).

Basically you can:

2. redirect stdout to a file

4. redirect stderr to a file

6. redirect stdout to a stderr

8. redirect stderr to a stdout

10. redirect stderr and stdout to a file

12. redirect stderr and stdout to stdout

14. redirect stderr and stdout to stderr

1 'represents' stdout and 2 stderr.

A little note for seeing this things: with the less command you can view both stdout (which will remain on the buffer) and the stderr that will be printed on the screen, but erased as you try to 'browse' the buffer.

3.2 Sample: stdout 2 file
----------------------------

This will cause the output of a program to be written to a file.

> 
> ```
> ls -l > ls-l.txt 
> ```

Here, a file called 'ls-l.txt' will be created and it will contain what you would see on the screen if you type the command 'ls -l' and execute it.

3.3 Sample: stderr 2 file
-------------------------

This will cause the stderr output of a program to be written to a file.

> ```
> grep da * 2> grep-errors.txt 
> ```

Here, a file called 'grep-errors.txt' will be created and it will contain what you would see the stderr portion of the output of the 'grep da *' command.

3.4 Sample: stdout 2 stderr
---------------------------

This will cause the stderr output of a program to be written to the same filedescriptor than stdout.

> ```
> grep da * 1>&2 
> ```

Here, the stdout portion of the command is sent to stderr, you may notice that in different ways.

3.5 Sample: stderr 2 stdout
---------------------------

This will cause the stderr output of a program to be written to the same filedescriptor than stdout.

> ```
> grep * 2>&1 
> ```

Here, the stderr portion of the command is sent to stdout, if you pipe to less, you'll see that lines that normally 'dissapear' (as they are written to stderr) are being kept now (because they're on stdout).

3.6 Sample: stderr and stdout 2 file
------------------------------------

This will place every output of a program to a file. This is suitable sometimes for cron entries, if you want a command to pass in absolute silence.

> ```
> rm -f $(find / -name core) &> /dev/null 
> ```

3.1 Theory and quick reference
------------------------------

There are 3 file descriptors, stdin, stdout and stderr (std=standard).

Basically you can:

1. redirect stdout to a file
2. redirect stderr to a file
3. redirect stdout to a stderr
4. redirect stderr to a stdout
5. redirect stderr and stdout to a file
6. redirect stderr and stdout to stdout
7. redirect stderr and stdout to stderr

1 'represents' stdout and 2 stderr.

A little note for seeing this things: with the less command you can view both stdout (which will remain on the buffer) and the stderr that will be printed on the screen, but erased as you try to 'browse' the buffer.

3.2 Sample: stdout 2 file
-------------------------

This will cause the output of a program to be written to a file.

> ```
> ls -l > ls-l.txt 
> ```

Here, a file called 'ls-l.txt' will be created and it will contain what you would see on the screen if you type the command 'ls -l' and execute it.

3.3 Sample: stderr 2 file
-------------------------

This will cause the stderr output of a program to be written to a file.

> ```
> grep da * 2> grep-errors.txt 
> ```

Here, a file called 'grep-errors.txt' will be created and it will contain what you would see the stderr portion of the output of the 'grep da *' command.

3.4 Sample: stdout 2 stderr
---------------------------

This will cause the stderr output of a program to be written to the same filedescriptor than stdout.

> ```
> grep da * 1>&2 
> ```

Here, the stdout portion of the command is sent to stderr, you may notice that in different ways.

3.5 Sample: stderr 2 stdout
---------------------------

This will cause the stderr output of a program to be written to the same filedescriptor than stdout.

> ```
> grep * 2>&1 
> ```

Here, the stderr portion of the command is sent to stdout, if you pipe to less, you'll see that lines that normally 'dissapear' (as they are written to stderr) are being kept now (because they're on stdout).

3.6 Sample: stderr and stdout 2 file
------------------------------------

This will place every output of a program to a file. This is suitable sometimes for cron entries, if you want a command to pass in absolute silence.

> ```
> rm -f $(find / -name core) &> /dev/null 
> ```
> 
> 3.1 Theory and quick reference
> ------------------------------
> 
> There are 3 file descriptors, stdin, stdout and stderr (std=standard).
> 
> Basically you can:
> 
> 1. redirect stdout to a file
> 2. redirect stderr to a file
> 3. redirect stdout to a stderr
> 4. redirect stderr to a stdout
> 5. redirect stderr and stdout to a file
> 6. redirect stderr and stdout to stdout
> 7. redirect stderr and stdout to stderr
> 
> 1 'represents' stdout and 2 stderr.
> 
> A little note for seeing this things: with the less command you can view both stdout (which will remain on the buffer) and the stderr that will be printed on the screen, but erased as you try to 'browse' the buffer.
> 
> 3.2 Sample: stdout 2 file
> -------------------------
> 
> This will cause the output of a program to be written to a file.
> 
> > ```
> > ls -l > ls-l.txt 
> > ```
> 
> Here, a file called 'ls-l.txt' will be created and it will contain what you would see on the screen if you type the command 'ls -l' and execute it.
> 
> 3.3 Sample: stderr 2 file
> -------------------------
> 
> This will cause the stderr output of a program to be written to a file.
> 
> > ```
> > grep da * 2> grep-errors.txt 
> > ```
> 
> Here, a file called 'grep-errors.txt' will be created and it will contain what you would see the stderr portion of the output of the 'grep da *' command.
> 
> 3.4 Sample: stdout 2 stderr
> ---------------------------
> 
> This will cause the stderr output of a program to be written to the same filedescriptor than stdout.
> 
> > ```
> > grep da * 1>&2 
> > ```
> 
> Here, the stdout portion of the command is sent to stderr, you may notice that in different ways.
> 
> 3.5 Sample: stderr 2 stdout
> ---------------------------
> 
> This will cause the stderr output of a program to be written to the same filedescriptor than stdout.
> 
> > ```
> > grep * 2>&1 
> > ```
> 
> Here, the stderr portion of the command is sent to stdout, if you pipe to less, you'll see that lines that normally 'dissapear' (as they are written to stderr) are being kept now (because they're on stdout).
> 
> 3.6 Sample: stderr and stdout 2 file
> ------------------------------------
> 
> This will place every output of a program to a file. This is suitable sometimes for cron entries, if you want a command to pass in absolute silence.
> 
> > ```
> > rm -f $(find / -name core) &> /dev/null 
> > ```

# # # Merge two files  

This appends the output to all.txt

```
 `cat *.txt >> all.txt` 
```

This overwrites all.txt

```
 `cat *.txt > all.txt` 
```

```

### 
How to sort a bed file  

```
linux: sort -k 1V,1 -k 2n,2 file.bed -o file.sorted.bed
``````
mac: sort -k 1d,1 -k 2n,2 file.bed
```

```

### 
how to split a bed file according to/by chromosomes  ubuntu :awk '{close(f);f=$1}{print > f".bed"}' example.bed

```
mac : awk '{ file = "TFBS." $1 ".bed" ; print >> file }' TFBS.bed
``````

``````

``````

### 
add up two int variables  

echo $M + $N | bc

### 
Store the output of a command into a variable  

M=$(awk '{print $2}' $outfile | grep -c c) 

```
```

To back up files, use:
``````
$ rsync -ruhavP
```

```

```

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
