# Popcorn time instalation for ARMv7 (Ubuntu 14.04.2)

This is an experimental build for Odroid-U3. I only tried it on Odroid U3 and XU4!
Some videos/audios can't be decoded yet due to lack of codecs on nwjs. 

### Instalation guide
  - Download files:
     - Popcorn-Time.tar.gz
     - pt_installer.sh
  - (optional) Move downloaded files to the same folder
  - Run pt_installer.sh from terminal with sudo privileges
  - Run Popcorn Time 
  - Eat popcorn!

### Kodi as External player
(Obviously you need a working kodi !)

To get it to work you first need to go into the popcorn time settings and set it to always stream on the same port. 
I chose 51234

Then create a file somewhere named stream.strm with the following in it.

`http://127.0.0.1:51234/`

For the next step there are two ways.

#####One (harder but better)
Recompile popcorntime with this 
```
        'kodi': {
            type: 'kodi',
            switches: '/LOCATION/OF/stream.strm',
            subswitch: '',
            fs: '',
        },
```
added to the players section of desktop.git/src/app/lib/device/ext-player.js

If you copy external-kodi-icon.png to desktop.git/src/app/images/icons/ you'll also have the correct icon.
https://github.com/LeonardLaszlo/popcorn-time-building-guide-armv7

Then kodi appears in the list of external players.

#####Two (easier)
Choose one of the supported external players that you DON'T have on your system eg mpv, mplayer, vlc, smplayer
create a file with that name in /usr/local/bin, make it executable and put this in it

```
#!/bin/bash
/usr/lib/kodi/kodi.bin /LOCATION/OF/stream.strm
```

Obviously the wrong program name shows up in the list the second way.

I find the streams much more watchable in Kodi

### VPN just for pocorntime
If you want to use a different vpn than the integrated vpn.ht but have other programs still use the standard connection there is a great guide here.

https://schnouki.net/posts/2014/12/12/openvpn-for-a-single-application-on-linux/

(systemd only I think)

### Uninstalation guide - How to uninstall Popcorn Time ?
  - Main application:
    - Delete ~/.Popcorn-Time
    - Delete ~/.local/share/applications/Popcorn-Time.desktop

  - Configuration files and databases:
    - Delete ~/.config/Popcorn-Time
