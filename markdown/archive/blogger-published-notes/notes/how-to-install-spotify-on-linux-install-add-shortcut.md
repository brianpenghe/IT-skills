---
title: 'How to install Spotify on linux : Install -> Add Shortcut'
date: 2017-02-11T19:39:00.000-08:00
draft: false
url: /2017/02/how-to-install-spotify-on-linux-install.html
---

> **Archived note — originally created: 2017-02-11 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


This is a summary of all you have to do 

1\. Install : 
ref:  https://www.spotify.com/us/download/linux/ 

```
\# 1. Add the Spotify repository signing key to be able to verify downloaded packages 
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys BBEBDCB318AD50EC6865090613B00F1FD2C19886 

\# 2. Add the Spotify repository 
echo deb http://repository.spotify.com stable non-free | sudo tee /etc/apt/sources.list.d/spotify.list 

\# 3. Update list of available packages 
sudo apt-get update 

\# 4. Install Spotify 
sudo apt-get install spotify-client
``` 

2\. Add shortcut: 
```
sudo gedit /usr/share/applications/spotify.desktop
``````
then replace the content with the following:
``````
\[Desktop Entry\] 
Name=Spotify 
GenericName=Music Player 
Comment=Spotify streaming music client 
Icon=spotify-client 
Exec=spotify %U 
TryExec=spotify 
Terminal=false 
Type=Application 
Categories=Audio;Music;Player;AudioVideo; 
MimeType=x-scheme-handler/spotify 
Actions=PlayOrPause;Stop;Next;Previous 

\[Desktop Action PlayOrPause\] 
Name=Play or Pause 
Exec=dbus-send --print-reply --dest=org.mpris.MediaPlayer2.spotify /org/mpris/MediaPlayer2 org.mpris.MediaPlayer2.Player.PlayPause 
OnlyShowIn=Unity; 

\[Desktop Action Stop\] 
Name=Stop 
Exec=dbus-send --print-reply --dest=org.mpris.MediaPlayer2.spotify /org/mpris/MediaPlayer2 org.mpris.MediaPlayer2.Player.Stop 
OnlyShowIn=Unity; 

\[Desktop Action Next\] 
Name=Next 
Exec=dbus-send --print-reply --dest=org.mpris.MediaPlayer2.spotify /org/mpris/MediaPlayer2 org.mpris.MediaPlayer2.Player.Next 
OnlyShowIn=Unity; 

\[Desktop Action Previous\] 
Name=Previous 
Exec=dbus-send --print-reply --dest=org.mpris.MediaPlayer2.spotify /org/mpris/MediaPlayer2 org.mpris.MediaPlayer2.Player.Previous 
OnlyShowIn=Unity; 
```

```

```

#Linux #download #TroubleshootNotes #BloggerPublishedNonAcademicNotes
