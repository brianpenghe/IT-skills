---
title: 'C++ : convert string to int number'
date: 2017-04-18T15:44:00.001-07:00
draft: false
url: /2017/04/c-convert-string-to-int-number.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


# # # Convert string to number using stringstream  

# # # # String to Number

Also converting a string to a number via stringstream takes two steps: 

1. Constructing the stream from the string
2. Reading the value into the variable

For this ( as you need to read input from the stream ) an `istringstream` will be used While a number can always be converted in a string, a string must be valid to be converted to a number ( eg: An attempt of converting "hello" to an integer would certainly fail ) so on this conversion, some checking must be done Here is the code example:  

string Text = "456"; // string containing the number  
int Result; //number which will contain the result  
istringstream convert(Text); // stringstream used for the conversion constructed with the contents of 'Text'  
                                           // ie: the stream will start containing the characters of 'Text'  
if ( !(convert >> Result) ) //give the value to 'Result' using the characters in the stream  
          Result = 0; //if that fails set 'Result' to 0 //'Result' now equal to 456 This conversion is even easier to reduce to a single line:  
string Text = "456"; int Number; if ( ! (istringstream(Text) >> Number) ) Number = 0;  

In the above code an object of istringstream gets constructed from 'Text' istringstream(Text) and its contents get read into the numeric variable >> Number. If that operation fails if ( !, 'Number' is set to zero Number = 0; Locales and manipulators can be used as well as with any stream

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
