C-Net Dongle Cracked!
---------------------
October 31, 2018 by admin

https://1200baud.wordpress.com/2018/10/31/c-net-dongle-cracked/


Thanks to Hoy Brothers from 13th Floor BBS for sending me the results of tests on an original C-Net dongle. Between that, some cryptic info I found on old comp.sys.cbm posts, and lots and lots of testing, I figured it out. 

This should allow all those oldschool sysops who lost their original dongles (like me) to load their original C-Net disks again. Should work with various versions. Not sure about C-Net 128, but I’d love feedback from anyone who tries this to confirm different versions it runs on. My original C-Net 12.0 runs fantastic now.

```
  C64 Port 2 Female DB9
  .--------------------.
(   1   2   3   4   5   )
 \  o   o   o   o   o  /
  \   o   o   o   o   /
   \  6   7   8   9  /
    '---------------'

1 	Joy B0 	up
2 	Joy B1 	down
3 	Joy B2 	left / paddle b fire x
4 	Joy B3 	right / paddle b fire y
5 	Pot BY 	paddle b pot y
6 	Button B 	fire
7 	+ 5V 	max. 100 mA
8 	GND 	Ground
9 	Pot BX 	paddle b pot x 
```

Parts needed: 

* 4.7k ohm resistor (1/4 watt should be fine)
* 10uf non-polarized capacitor (5v minimum rating i assume)
* 1n4148 diode (the cheap ones you used to get in batches from radio shack)
* female 9-pin serial connector (for the joystick port). 

Instructions
------------

1. Connect pin 7 to pin 9

2. Pin 5 -> 4.7k ohm resistor -> Pin 9

3. Pin 5 -> 10uf Non-polarized Capacitor -> Pin 9 (the resistor and capacitor run in parallel)

4. Pin 1 -> Anode of Diode – Cathode of diode -> Pin 5

That’s it. Let me know how this works out for you. Remember it plugs into port 2.

Versions confirmed so far:
--------------------------
- DS-2 11.6
- 12.0
