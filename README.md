DWM
===============

This is my own build of dwm-5.9 on Arch Linux. 

![Preview](https://github.com/spo11/dwm/raw/master/screenshot.png)

Patches
-------------

 * [pertag without bar](http://dwm.suckless.org/patches/dwm-5.8.2-pertag_without_bar.diff)
 * [bstack-alt](http://dwm.suckless.org/patches/dwm-5.9-bstack-alt.diff) 
 * [statuscolors](http://dwm.suckless.org/patches/dwm-5.9-statuscolors.diff)
 * [uselessgap](http://dwm.suckless.org/patches/dwm-5.9-uselessgap.diff)

General Information
---------------------
### Fonts
I use the [terminusmod](https://aur.archlinux.org/packages.php?ID=49117) font, which contains glyphs for the status icons. To view other possible options for what characters to include, install **gucharmap**, the GNOME font preview application. Select 'Terminusmod' in the dropdown, and set the size to 12. Select the 'Latin' script. Scroll at the topmost place in the Character Table, and you should see other characters there. 

### Status Bar
Perhaps you want to have a status bar containing MPD, netcfg/wifi, volume information. Grab [this script](https://github.com/spo11/configs/blob/master/scripts/startdwm) to have that kind of output. 

Make sure to make the file executible:
```
chmod +x startdwm
```

Place it in *~/.bin/*.

Applying Other Patches
------------------------

Save any *.diff file (ensuring that it corresponds to whatever version of dwm you have) to dwm/src/dwm-5.9/.

*Change to src/dwm-5.9/*. Then issue the following command:

```
patch -p1 < nameofpatch.diff
```

Instructions
-------------
### Building DWM
To build this, simply issue this command:

```
makepkg -efi --skipinteg
```

### Starting this dwm build
Edit your ~/.xinitrc file and copy and paste the following lines:
```bash
#!/bin/zsh
mpd ~/.mpd/mpd.conf & # this is to start the music player daemon
nitrogen --restore & # this is to set an image background
xset +fp /usr/share/fonts/local & # must be done to make sure the symbols in Terminusmod show up 
xset fp rehash & # see above
exec ck-launch-session dbus-launch --sh-syntax --exit-with-session ~/.bin/startdwm
```

Troubleshooting
----------------

You may find that you are unable to build this because of some error with config.h not being found. Just copy config.h in the root directory to src/ and then rebuild.  

