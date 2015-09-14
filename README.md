# Popcorn time instalation guide for ARMv7

This is an experimental build for Odroid-U3 and Odroid-XU4.
Some videos/audios can't be decoded yet due to lack of codecs on nw.js. 

### Instalation guide
  - Clone the repository and change into directory:
  - (optional) chmod +x pt_installer.sh
  - Run pt_installer.sh from terminal with sudo privileges

### Kodi as External player
(Obviously you need a working kodi! NB.: Since v0.3.8-5 kodi was added as external player, so you don't have to recompile!)

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

### Known issues
- It doesn't work on Chromebook!
- It does not load .torrent files.

### Link to article in Odroid Magazine:

http://magazine.odroid.com/assets/201507/pdf/ODROID-Magazine-201507.pdf
