DWM
===============

This is my own build of dwm-5.9 on Arch Linux.

Patches
-------------

 * [pertag without bar](http://dwm.suckless.org/patches/dwm-5.8.2-pertag_without_bar.diff)
 * [bstack-alt](http://dwm.suckless.org/patches/dwm-5.9-bstack-alt.diff) 
 * [statuscolors](http://dwm.suckless.org/patches/dwm-5.9-statuscolors.diff)
 * [uselessgap](http://dwm.suckless.org/patches/dwm-5.9-uselessgap.diff)

Applying Other Patches
------------------------

Save any *.diff file (ensuring that it corresponds to whatever version of dwm you have) to dwm/src/dwm-5.9/.

*Change to src/dwm-5.9/*. Then issue the following command:

```
patch -p1 < nameofpatch.diff
```

Instructions
-------------
To build this, simply issue this command:

```
makepkg -efi --skipinteg
```

Troubleshooting
----------------
You may find that you are unable to build this because of some error with config.h not being found. Just copy config.h in the root directory to src/ and then rebuild.  

