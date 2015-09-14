# Popcorn time instalation guide for ARMv7

This is an experimental build for Odroid-U3 and Odroid-XU4.

### Known issues
- It doesn't work on Chromebook!
- It does not load .torrent files.
- Some videos/audios can't be decoded yet due to lack of codecs on nw.js.

### Instalation guide
- Clone the repository and open a terminal after change into the directory directory:
- Run `chmod +x pt_installer.sh`
- Run `sudo pt_installer.sh`

### Uninstalation guide
- Main application:
	- Delete `~/.Popcorn-Time`
	- Delete `~/.local/share/applications/Popcorn-Time.desktop`

- Configuration files and databases:
	- Delete `~/.config/Popcorn-Time`

##### Link to article in Odroid Magazine:
http://magazine.odroid.com/assets/201507/pdf/ODROID-Magazine-201507.pdf

##### Kodi as external player:
https://github.com/LeonardLaszlo/popcorn-time-installation-guide-armv7/blob/master/KODI.md

##### VPN just for pocorntime:
https://github.com/LeonardLaszlo/popcorn-time-installation-guide-armv7/blob/master/VPN.md

