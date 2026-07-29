---
title: 'Some notes on Linux'
date: 2017-04-18T19:25:00.003-07:00
draft: false
url: /2017/04/some-notes-on-linux.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


# # # how to remove the return char in an output

echo -n hallo >> test

# # # Important bug in grep---unexpected termination of grep -c (both Linux and Mac)  

When grep -c outputs 0 for not finding any matches, the output CANNOT be stored in any variables and it will stop the whole bash file.

To get around it, use if statement to detect whether there are matches and assign a zero value to the result. 

# Hope this bug will be fixed in future

# # # Array of strings 

10.2.1. Creating arrays
-----------------------

An array is a variable containing multiple values. Any variable may be used as an array. There is no maximum limit to the size of an array, nor any requirement that member variables be indexed or assigned contiguously. Arrays are zero-based: the first element is indexed with the number 0.

Indirect declaration is done using the following syntax to declare a variable:

**ARRAY\[INDEXNR\]=value**

The _INDEXNR_ is treated as an arithmetic expression that must evaluate to a positive number.

Explicit declaration of an array is done using the **declare** built-in:

**declare -a ARRAYNAME**

A declaration with an index number will also be accepted, but the index number will be ignored. Attributes to the array may be specified using the **declare** and **readonly** built-ins. Attributes apply to all variables in the array; you can't have mixed arrays.

Array variables may also be created using compound assignments in this format:

**ARRAY=(value1 value2 ... valueN)**

Each value is then in the form of _\[indexnumber=\]string_. The index number is optional. If it is supplied, that index is assigned to it; otherwise the index of the element assigned is the number of the last index that was assigned, plus one. This format is accepted by **declare** as well. If no index numbers are supplied, indexing starts at zero.

Adding missing or extra members in an array is done using the syntax:

**ARRAYNAME\[indexnumber\]=value**

Remember that the **read** built-in provides the -a option, which allows for reading and assigning values for member variables of an array.

[](https://www.blogger.com/null)10.2.2. Dereferencing the variables in an array
-------------------------------------------------------------------------------

In order to refer to the content of an item in an array, use curly braces. This is necessary, as you can see from the following example, to bypass the shell interpretation of expansion operators. If the index number is _@_ or _\*_, all members of an array are referenced.

```
\[bob in ~\] **ARRAY=_(one two three)_**\[bob in ~\] **echo ${ARRAY\[\*\]}**one two three\[bob in ~\] **echo $ARRAY\[\*\]**one\[\*\]\[bob in ~\] **echo ${ARRAY\[2\]}**three\[bob in ~\] **ARRAY\[3\]=_four_**\[bob in ~\] **echo ${ARRAY\[\*\]}**one two three four
```

Referring to the content of a member variable of an array without providing an index number is the same as referring to the content of the first element, the one referenced with index number zero.

[](https://www.blogger.com/null)10.2.3. Deleting array variables
----------------------------------------------------------------

The **unset** built-in is used to destroy arrays or member variables of an array:

```
\[bob in ~\] **unset ARRAY\[1\]**\[bob in ~\] **echo ${ARRAY\[\*\]}**one three four\[bob in ~\] **unset ARRAY**\[bob in ~\] **echo ${ARRAY\[\*\]}**<--no output-->
```

[](https://www.blogger.com/null)10.2.4. Examples of arrays
----------------------------------------------------------

Practical examples of the usage of arrays are hard to find. You will find plenty of scripts that don't really do anything on your system but that do use arrays to calculate mathematical series, for instance. And that would be one of the more interesting examples...most scripts just show what you can do with an array in an oversimplified and theoretical way.

The reason for this dullness is that arrays are rather complex structures. You will find that most practical examples for which arrays could be used are already implemented on your system using arrays, however on a lower level, in the C programming language in which most UNIX commands are written. A good example is the Bash **history** built-in command. Those readers who are interested might check the built-ins directory in the Bash source tree and take a look at fc.def, which is processed when compiling the built-ins.

Another reason good examples are hard to find is that not all shells support arrays, so they break compatibility.

After long days of searching, I finally found this example operating at an Internet provider. It distributes Apache web server configuration files onto hosts in a web farm:

```
#!/bin/bashif \[ $(whoami) != 'root' \]; then echo "Must be root to run $0" exit 1;fiif \[ -z $1 \]; then echo "Usage: $0 </path/to/httpd.conf>" exit 1fihttpd\_conf\_new=$1httpd\_conf\_path="/usr/local/apache/conf"login=htuserfarm\_hosts=(web03 web04 web05 web06 web07)for i in ${farm\_hosts\[@\]}; do su $login -c "scp $httpd\_conf\_new ${i}:${httpd\_conf\_path}" su $login -c "ssh $i sudo /usr/local/apache/bin/apachectl graceful"doneexit 0
```

First two tests are performed to check whether the correct user is running the script with the correct arguments. The names of the hosts that need to be configured are listed in the array farm\_hosts. Then all these hosts are provided with the Apache configuration file, after which the daemon is restarted. Note the use of commands from the Secure Shell suite, encrypting the connections to remote hosts.

Thanks, Eugene and colleague, for this contribution.

Dan Richter contributed the following example. This is the problem he was confronted with:

"...In my company, we have demos on our web site, and every week someone has to test all of them. So I have a cron job that fills an array with the possible candidates, uses **date +%W** to find the week of the year, and does a modulo operation to find the correct index. The lucky person gets notified by e-mail."

And this was his way of solving it:

```
#!/bin/bash# This is get-tester-address.sh ## First, we test whether bash supports arrays.# (Support for arrays was only added recently.)#whotest\[0\]='test' || (echo 'Failure: arrays not supported in this version ofbash.' && exit 2) ## Our list of candidates. (Feel free to add or# remove candidates.)#wholist=( 'Bob Smith <bob@example.com>' 'Jane L. Williams <jane@example.com>' 'Eric S. Raymond <esr@example.com>' 'Larry Wall <wall@example.com>' 'Linus Torvalds <linus@example.com>' )## Count the number of possible testers.# (Loop until we find an empty string.)#count=0while \[ "x${wholist\[count\]}" != "x" \]do count=$(( $count + 1 ))done ## Now we calculate whose turn it is.#week=\`date '+%W'\` # The week of the year (0..53).week=${week#0} # Remove possible leading zero. let "index = $week % $count" # week modulo count = the lucky personemail=${wholist\[index\]} # Get the lucky person's e-mail address. echo $email # Output the person's e-mail address.
```

This script is then used in other scripts, such as this one, which uses a _here_ document:

```
email=\`get-tester-address.sh\` # Find who to e-mail.hostname=\`hostname\` # This machine's name. ## Send e-mail to the right person.#mail $email -s '\[Demo Testing\]' <<EOFThe lucky tester this week is: $email Reminder: the list of demos is here: http://web.example.com:8080/DemoSites (This e-mail was generated by $0 on ${hostname}.)EOF
```

If you're used to a "standard" \*NIX shell you may not be familiar with bash's array feature. Although not as powerful as similar constructs in the P languages (Perl, Python, and PHP) and others, they are often quite useful.

Bash arrays have numbered indexes only, but they are sparse, ie you don't have to define all the indexes. An entire array can be assigned by enclosing the array items in parenthesis:

```
 arr=(Hello World)
``````
 Individual items can be assigned with the familiar array syntax (unless you're used to Basic or Fortran): 
``````
 arr\[0\]=Hello arr\[1\]=World
``````
 But it gets a bit ugly when you want to refer to an array item: 
``````
 echo ${arr\[0\]} ${arr\[1\]}
``````
 To quote from the man page: 
```

> The braces are required to avoid conflicts with pathname expansion.

In addition the following funky constructs are available:

```
 ${arr\[\*\]} # All of the items in the array ${!arr\[\*\]} # All of the indexes in the array ${#arr\[\*\]} # Number of items in the array ${#arr\[0\]} # Length of item zero
``````
 The ${!arr\[\*\]} is a relatively new addition to bash, it was not part of the original array implementation. 
```

The following example shows some simple array usage (note the "\[index\]=value" assignment to assign a specific index):

```
 #!/bin/basharray\=(one two three four \[5\]=five)echo "Array size: ${#array\[\*\]}"echo "Array items:"for item in ${array\[\*\]}doprintf " %s\\n" $itemdoneecho "Array indexes:"for index in ${!array\[\*\]}doprintf " %d\\n" $indexdoneecho "Array items and indexes:"for index in ${!array\[\*\]}doprintf "%4d: %s\\n" $index ${array\[$index\]}done 
```

```
 Running it produces the following output: 
``````
Array size: 5Array items: one two three four fiveArray indexes: 0 1 2 3 5Array items and indexes: 0: one 1: two 2: three 3: four 5: five
```

Note that the "@" sign can be used instead of the "\*" in constructs such as${arr\[\*\]}, the result is the same except when expanding to the items of the array within a quoted string. In this case the behavior is the same as when expanding "$\*" and "$@" within quoted strings: "${arr\[\*\]}" returns all the items as a single _word_, whereas "${arr\[@\]}" returns each item as a separate word.

The following example shows how unquoted, quoted "\*", and quoted "@" affect the expansion (particularly important when the array items themselves contain spaces):

```
 # !/bin/basharray\=("first item" "second item" "third" "item")echo "Number of items in original array: ${#array\[\*\]}"for ix in ${!array\[\*\]}doprintf " %s\\n" "${array\[$ix\]}"doneechoarr\=(${array\[\*\]})echo "After unquoted expansion: ${#arr\[\*\]}"for ix in ${!arr\[\*\]}doprintf " %s\\n" "${arr\[$ix\]}"doneechoarr\=("${array\[\*\]}")echo "After \* quoted expansion: ${#arr\[\*\]}"for ix in ${!arr\[\*\]}doprintf " %s\\n" "${arr\[$ix\]}"doneechoarr\=("${array\[@\]}")echo "After @ quoted expansion: ${#arr\[\*\]}"for ix in ${!arr\[\*\]}doprintf " %s\\n" "${arr\[$ix\]}"done 
```

```
 When run it outputs: 
``````
Number of items in original array: 4 first item second item third itemAfter unquoted expansion: 6 first item second item third itemAfter \* quoted expansion: 1 first item second item third itemAfter @ quoted expansion: 4 first item second item third item
```

# # # comparison operators  

A _binary_ comparison operator compares two variables or quantities. _Note that integer and string comparison use a different set of operators._

**[](https://www.blogger.com/null)integer comparison**

[](https://www.blogger.com/null)\-eq

is equal to

**if \[ "$a" -eq "$b" \]**

[](https://www.blogger.com/null)\-ne

is not equal to

**if \[ "$a" -ne "$b" \]**

[](https://www.blogger.com/null)\-gt

is greater than

**if \[ "$a" -gt "$b" \]**

[](https://www.blogger.com/null)\-ge

is greater than or equal to

**if \[ "$a" -ge "$b" \]**

[](https://www.blogger.com/null)\-lt

is less than

**if \[ "$a" -lt "$b" \]**

[](https://www.blogger.com/null)\-le

is less than or equal to

**if \[ "$a" -le "$b" \]**

[](https://www.blogger.com/null)<

is less than (within [double parentheses](http://tldp.org/LDP/abs/html/dblparens.html))

**(("$a" < "$b"))**

[](https://www.blogger.com/null)<=

is less than or equal to (within double parentheses)

**(("$a" <= "$b"))**

[](https://www.blogger.com/null)\>

is greater than (within double parentheses)

**(("$a" > "$b"))**

[](https://www.blogger.com/null)\>=

is greater than or equal to (within double parentheses)

**(("$a" >= "$b"))**

**[](https://www.blogger.com/null)string comparison**

\=

is equal to

**if \[ "$a" = "$b" \]**

![Caution](https://tldp.org/LDP/abs/images/caution.gif)

Note the [whitespace](http://tldp.org/LDP/abs/html/special-chars.html#WHITESPACEREF) framing the **\=**.

**if \[ "$a"="$b" \]** is _not_ equivalent to the above.

[](https://www.blogger.com/null)\==

is equal to

**if \[ "$a" == "$b" \]**

This is a synonym for \=.

![Note](https://tldp.org/LDP/abs/images/note.gif)

The \== comparison operator behaves differently within a [double-brackets](http://tldp.org/LDP/abs/html/testconstructs.html#DBLBRACKETS) test than within single brackets.

```
\[\[ $a == z\* \]\] # True if $a starts with an "z" (pattern matching).\[\[ $a == "z\*" \]\] # True if $a is equal to z\* (literal matching).\[ $a == z\* \] # File globbing and word splitting take place.\[ "$a" == "z\*" \] # True if $a is equal to z\* (literal matching).# Thanks, Stéphane Chazelas
```

[](https://www.blogger.com/null)!=

is not equal to

**if \[ "$a" != "$b" \]**

This operator uses pattern matching within a [\[\[ ... \]\]](http://tldp.org/LDP/abs/html/testconstructs.html#DBLBRACKETS) construct.

[](https://www.blogger.com/null)<

is less than, in [ASCII](http://tldp.org/LDP/abs/html/special-chars.html#ASCIIDEF) alphabetical order

**if \[\[ "$a" < "$b" \]\]**

**if \[ "$a" \\< "$b" \]**

Note that the "<" needs to be [escaped](http://tldp.org/LDP/abs/html/escapingsection.html#ESCP) within a **\[ \]** construct.

[](https://www.blogger.com/null)\>

is greater than, in ASCII alphabetical order

**if \[\[ "$a" > "$b" \]\]**

**if \[ "$a" \\> "$b" \]**

Note that the ">" needs to be escaped within a **\[ \]** construct.

See [Example 27-11](http://tldp.org/LDP/abs/html/arrays.html#BUBBLE) for an application of this comparison operator.

[](https://www.blogger.com/null)\-z

string is _null_, that is, has zero length

```
 String='' # Zero-length ("null") string variable.if \[ -z "$String" \]then echo "\\$String is null."else echo "\\$String is NOT null."fi # $String is null.
```

[](https://www.blogger.com/null)\-n

string is not _null._

![Caution](https://tldp.org/LDP/abs/images/caution.gif)

The **\-n** test requires that the string be quoted within the test brackets. Using an unquoted string with _! -z_, or even just the unquoted string alone within test brackets (see [Example 7-6](http://tldp.org/LDP/abs/html/comparison-ops.html#STRTEST)) normally works, however, this is an unsafe practice. _Always_ quote a tested string. [](http://tldp.org/LDP/abs/html/comparison-ops.html#FTN.AEN3641)\[1\]

**Example 7-5. Arithmetic and string comparisons**

```
#!/bin/basha=4b=5# Here "a" and "b" can be treated either as integers or strings.# There is some blurring between the arithmetic and string comparisons,#+ since Bash variables are not strongly typed.# Bash permits integer operations and comparisons on variables#+ whose value consists of all-integer characters.# Caution advised, however.echoif \[ "$a" -ne "$b" \]then echo "$a is not equal to $b" echo "(arithmetic comparison)"fiechoif \[ "$a" != "$b" \]then echo "$a is not equal to $b." echo "(string comparison)" # "4" != "5" # ASCII 52 != ASCII 53fi# In this particular instance, both "-ne" and "!=" work.echoexit 0
```

**Example 7-6. Testing whether a string is _null_**

```
#!/bin/bash# str-test.sh: Testing null strings and unquoted strings,#+ but not strings and sealing wax, not to mention cabbages and kings . . .# Using if \[ ... \]# If a string has not been initialized, it has no defined value.# This state is called "null" (not the same as zero!).if \[ -n $string1 \] # string1 has not been declared or initialized.then echo "String \\"string1\\" is not null."else echo "String \\"string1\\" is null."fi # Wrong result.# Shows $string1 as not null, although it was not initialized.echo# Let's try it again.if \[ -n "$string1" \] # This time, $string1 is quoted.then echo "String \\"string1\\" is not null."else echo "String \\"string1\\" is null."fi # Quote strings within test brackets!echoif \[ $string1 \] # This time, $string1 stands naked.then echo "String \\"string1\\" is not null."else echo "String \\"string1\\" is null."fi # This works fine.# The \[ ... \] test operator alone detects whether the string is null.# However it is good practice to quote it (if \[ "$string1" \]).## As Stephane Chazelas points out,# if \[ $string1 \] has one argument, "\]"# if \[ "$string1" \] has two arguments, the empty "$string1" and "\]" echostring1=initializedif \[ $string1 \] # Again, $string1 stands unquoted.then echo "String \\"string1\\" is not null."else echo "String \\"string1\\" is null."fi # Again, gives correct result.# Still, it is better to quote it ("$string1"), because . . .string1="a = b"if \[ $string1 \] # Again, $string1 stands unquoted.then echo "String \\"string1\\" is not null."else echo "String \\"string1\\" is null."fi # Not quoting "$string1" now gives wrong result!exit 0 # Thank you, also, Florian Wisser, for the "heads-up".
```

**Example 7-7. _zmore_**

```
#!/bin/bash# zmore# View gzipped files with 'more' filter.E\_NOARGS=85E\_NOTFOUND=86E\_NOTGZIP=87if \[ $# -eq 0 \] # same effect as: if \[ -z "$1" \]# $1 can exist, but be empty: zmore "" arg2 arg3then echo "Usage: \`basename $0\` filename" >&2 # Error message to stderr. exit $E\_NOARGS # Returns 85 as exit status of script (error code).fi filename=$1if \[ ! -f "$filename" \] # Quoting $filename allows for possible spaces.then echo "File $filename not found!" >&2 # Error message to stderr. exit $E\_NOTFOUNDfi if \[ ${filename##\*.} != "gz" \]# Using bracket in variable substitution.then echo "File $1 is not a gzipped file!" exit $E\_NOTGZIPfi zcat $1 | more# Uses the 'more' filter.# May substitute 'less' if desired.exit $? # Script returns exit status of pipe.# Actually "exit $?" is unnecessary, as the script will, in any case,#+ return the exit status of the last command executed.
```

**[](https://www.blogger.com/null)compound comparison**

[](https://www.blogger.com/null)\-a

logical and

_exp1 -a exp2_ returns true if _both_ exp1 and exp2 are true.

[](https://www.blogger.com/null)\-o

logical or

_exp1 -o exp2_ returns true if either exp1 _or_ exp2 is true.

These are similar to the Bash comparison operators **&&** and **||**, used within [double brackets](http://tldp.org/LDP/abs/html/testconstructs.html#DBLBRACKETS).

```
\[\[ condition1 && condition2 \]\]
```

The **\-o** and **\-a** operators work with the [test](http://tldp.org/LDP/abs/html/testconstructs.html#TTESTREF) command or occur within single test brackets.

```
if \[ "$expr1" -a "$expr2" \]then echo "Both expr1 and expr2 are true."else echo "Either expr1 or expr2 is false."fi
```

![Caution](https://tldp.org/LDP/abs/images/caution.gif)

But, as _rihad_ points out:

```
\[ 1 -eq 1 \] && \[ -n "\`echo true 1>&2\`" \] # true\[ 1 -eq 2 \] && \[ -n "\`echo true 1>&2\`" \] # (no output)# ^^^^^^^ False condition. So far, everything as expected.# However ...\[ 1 -eq 2 -a -n "\`echo true 1>&2\`" \] # true# ^^^^^^^ False condition. So, why "true" output?# Is it because both condition clauses within brackets evaluate?\[\[ 1 -eq 2 && -n "\`echo true 1>&2\`" \]\] # (no output)# No, that's not it.# Apparently && and || "short-circuit" while -a and -o do not.
```

# # # awk: sum up a column of numbers  

awk '{ sum+=$1} END {print sum}' count.txt

# # # Using scp to copy/download entire folder from the server  

scp -r UserName@serverIP:/path/to/the/file /local/path

# # # How to grep out words containing a certain character?怎样提取文件中含有某一特定字符的词语  

For example. 
We have a list of mail addresses like: 
sucvzkba@126.com; aesr;oiuh bzdk@gmail.com; hlasdv 1986 Oct iejx@foxmail.com; 183cm 

We want to get: 
sucvzkba@126.com; bzdk@gmail.com; iejx@foxmail.com; 

First: How to change space into an endline/new line? 
      tr ' ' '\\n' < Myfile 

Second: How to grep those lines containing @ ? 
      grep @ Myfile 

Third: How to change an endline into space? 
     tr '\\n' ' ' < Myfile 

And then pipe them up: 
     tr ' ' '\\n' < Myfile | grep @ | tr '\\n' ' '> Mynewfile

# # # remove the first line using ubuntu linux  

```
tail -n +2 $file >> essay1.txt
``````

# # # 
Read-only file system (when mount remount doesn't work) 

To solve this problem, simply defragment the disk.

# # # 
[how to install g++ on ubuntu]E: Invalid operation build-essential  

1. Click applications -> ubuntu software center ->edit-> software sources, then activate all the sources 
2. Make sure the computer is connected to network 
3. sudo apt-get install build-essential

# # # 
How to replace a word/string using linux

`sed -i 's/old-word/new-word/g' *.txt` 
注意这个命令是直接在原文件上操作的

```

#Python #Linux #download #TroubleshootNotes #BloggerPublishedNonAcademicNotes
