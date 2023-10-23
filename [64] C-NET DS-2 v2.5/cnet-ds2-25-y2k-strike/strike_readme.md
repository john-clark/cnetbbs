C-Net DS2 v2.5c – y2k fix and wifi modem settings
-------
November 3, 2018 by admin	

https://1200baud.wordpress.com/2018/11/03/c-net-ds2-v2-5c-y2k-fix-and-wifi-modem-settings/

This is the same as the cracked version from Vendetta, with boot file fix, y2k fix, enhancements for wifi modems like the Strikelink WiFi (make sure to add/connect the DCD pin on the C64 to D4 on the nodemcu for Strikelink WiFi use). 

Still only 2400 baud, but tested and working. I may take a shot at adding Swiftlink drivers for faster speed in the future. I’ve already hacked the ml and know how the modem drivers work, just a matter of seeing if it plays nice with other modem types. The 2400 baud routines that originally come with this version of DS2 are the proper George Hug 2400 baud routines, so it’s solid at 2400.

For original sysops who don’t want to use files from the Vendetta release, heres the y2k fix information.

In ml-2577, change the following bytes:
```
a479 – change #$b1 to #$b2
a47a – change #$ba to #$b0
a080 – change #$90 to #$20
```
