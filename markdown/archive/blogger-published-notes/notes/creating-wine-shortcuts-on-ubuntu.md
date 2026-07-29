---
title: 'creating wine shortcuts on ubuntu'
date: 2014-12-28T22:24:00.000-08:00
draft: false
url: /2014/12/creating-wine-shortcuts-on-ubuntu.html
---

> **Archived note — originally created: 2014-12-28 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


http://askubuntu.com/questions/437555/creating-wine-shortcuts 

1. Open your favourite text editor (`gedit`, `nano`, etc.), create a new file with the following content and save it to your Desktop with a name having extension `.desktop` 
 In this example, I've chosen to the name `inetexplorer.desktop` and saved it to my desktop. 

 > ```
 > [Desktop Entry] 
 > Name=Internet Explorer 
 > Exec=wine "C:\Program Files\Internet Explorer\iexplore.exe" 
 > Icon=/path/to/iconfile 
 > Type=Application 
 > Categories=Wine; 
 > 
 > ```

 Here, replace the value for **Name** field with that of the target application's name. (In the example, it's Internet Exolorer.) The value of **Exec** would be in the format: 
 ```
 wine "C:\path to the\executable file" 

 ```(for GUI applications) 
 ```
 wineconsole "C:\path to the\executable file" 

 ```(for CLI application) like say 
 ```
 wine "C:\Program Files\Internet Explorer\iexplore.exe" 

 ```(enclosing the path within double quotes `".. .."` is important if the path contain blank spaces.) 
 Replace _/path/to/iconfile_ (the value for **Icon** field) with the path of an icon file (like _Icon=/home/username/Pictures/internet-explorer.png_) or you can omit this line of entry. 
 On the left is a shortcut with icon specified, for the one on right, not.![iconField](http://i.stack.imgur.com/YFiiS.png)
2. Turn on the file's execute bit on. 
 Graphically you can do it by _right clicking_ the `.desktop` file, and from the context menu select _Properties_. In the properties window, select _Permission_ tab, look for a label **Execute:** and check-mark the check-box next to it so that the shortcut becomes executable. 
 selecting property from right-click context menu![rightClickTheFile](http://i.stack.imgur.com/MugiU.png) 
 setting execute permission![executableProperty](http://i.stack.imgur.com/GYKb6.png) 
 From terminal, you can do this with: 
 ```
 chmod +x $USER/Desktop/inetexplorer.desktop 

 ```where `$USER/Desktop/inetexplorer.desktop` should be the absolute path of the desktop shortcut that was created.

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
