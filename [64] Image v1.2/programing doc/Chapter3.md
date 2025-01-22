[Index/Preface](index-preface.md) | [Chapter I ](Chapter1.md) | [Chapter II ](Chapter2.md) | [Chapter III](Chapter3.md) | [Chapter IV](Chapter4.md) | [Chapter V](Chapter5.md)


# Chapter III: Machine Language Subroutines

  

## Jump Table Routines (& Commands) - v1.2

----------

**Routine**

**Description:**

**0 - outastr**

Output routine. Handles MCI.

_Examples:_

&

&"text"

Display A$.

Display text.

----------

**1 - inline**

Input routine. Handles word wrap, MCI access, line length, and graphics. Before calling, use POKE 53252,_<line length>_ to set the line length. W$ is the text that is wrapped, and AN$ holds the inputted text.

_Usage:_

&,1,x,y

x=

**Bit/value**

**Use**

0/1

Graphics allowed

1/2

"." on column 1 exits

2/4

Disable P$ prompt

3/8

Allow MCI

4/16

Text wrap on

5/32

Edit mode on

6/64

Ignore time expired

7/128

Delete on column 1 exits

y= [This part was left blank in the original document.]

_Examples:_

POKE 53252,10:P$="Name?":&,1

Prompts user for name, and allows up to ten characters to be entered.

POKE 53252,20:W$=NA$:P$="Handle":&,1,32:IF AN$<>"" THEN NA$=AN$

Prints prompt, then old handle, and then the prompt again, and allows the user to enter a new handle.

----------

**2 - dskin**

File input routine, which will input a maximum of 80 characters into the variable A$. Also allows bytes to be read directly from a file into a variable.

_Usage:_

&,2,_file#_,0

&,2,_file#_,_N_

Normal input, stop at CHR$(13)

Input up to N bytes into A$, ignoring CHR$(13)

----------

**3 - read0**

File read routine, also allows an optional speed variable for Movie Files. Using a speed of 0 uses the normal file read, whereas using any other value uses the Movie File read, with an appropriate slowdown based on the speed value.

_Usage:_

&,3,_file#_

&,3,_file#_,_speed_

Normal file read

View Movie File

----------

**4 - getmdm**

Get a character from the modem. This returns the character that was received in location 780. This routine does no ASCII translation, and no high bit stripping. It gets the character directly from the RS232 routines.

_Usage:_

&,4:A=PEEK(780)

----------

**5 - getversn**

Get the version number information that is embedded into the ML. This puts the revision number into A% and the revision date into A$.

_Usage:_

&,5

----------

**6 - password**

Password input. Sets text length to 14 characters, and inputs a password. Mask character is printed rather than the real character that is typed. Password is returned in AN$.

_Usage:_

&,6

----------

**7 - prg**

Loads modules into memory. The filename and drive number are in A$, and the device number is passed directly in the command.

_Usage:_

DR=5:GOSUB 1010:A$=DR$+"+._<filename>_":&,7,DV%

Loads a +.file from the +.file disk

DR=5:GOSUB 1010:A$=DR$+"+.nm.file":&,7,DV%,1

Loads a mini-module from the +.file disk. See the section on "Using Modules" for more information.

----------

**8 - dskdir**

This will read the directory from a file that was opened as a directory channel.

_Usage:_

DR=1:GOSUB 1010:OPEN 2,DV%,0,"$"+DR$+"*":  
&,8,2:CLOSE 2

This reads the directory from the system disk.

DR=2:GOSUB 1010:OPEN 2,DV%,0,"$"+DR$+"m.*":  
GET #2,A$,A$:&,8,2,1:&,8,2,1:CLOSE 2

This reads the first entry for the first E-mail file into A$.

----------

**9 - btmvar**

This displays the contents of a variable at the bottom of the screen. The variable displayed can be either A$ or AN$.

_Usage:_

&,9

&,9,1

Display AN$

Display A$

----------

**10 - term**

This is the terminal mode that is used in Image Term. To exit term mode, press the C= and CTRL keys together.

_Usage:_

&,10

----------

**11 - clrarr**

This is used to clear the contents of an array. Any of the arrays can be cleared, except BF().

_Usage:_

&,11

&,11,1

&,11,2

Clear TT$().

(This was left blank in the original document.)

(This was left blank in the original document.)

----------

**12 - newusr**

This is the same as the normal file read, except the file read is non-abortable, and the speed option is not supported.

_Usage:_

&,12,file#

----------

**13 - inchr**

This is the "get character" routine. Like the MCI Get (£G), it waits for a character from either the keyboard or the modem, and returns it in AN$.

_Usage:_

&,13

----------

**14 - bell1**

Sounds a bell

_Usage:_

&,14

----------

**15 - convan**

Converts AN$ from an 11-byte date to text. The resulting text string is placed back into AN$.

_Usage:_

&,15

----------

**16 - sys49152**

This does a SYS 49152 to call a protocol.

_Usage:_

&,16

----------

**17 - sys49155**

This does a SYS 49155 to call a protocol.

_Usage:_

&,17

----------

**18 - setmode**

Set the screen mode (1=split, 0=full)

_Usage:_

&,18,0

&,18,1

Set full screen mode

Set split screen mode

----------

**19 - disp1**

Display top of screen for user online. This loads the appropriate scn.* files.

_Usage:_

&,19,device#,drive#

----------

**20 - disp2**

Display top of screen for system idle. This loads the appropriate scn.* files.

_Usage:_

&,20,device#,drive#

----------

**21 - disp3**

Display bottom of screen.

_Usage:_

&,21,device#,drive#

----------

**22 - tenwait**

Time delay. This will wait for any interval between .1 second to 25.5 seconds, in 1/10 second steps.

_Usage:_

&,22,tenths

----------

**23 - xgetin**

This is the get character routine that should be used when writing ML routines that need to get a character from the user. The character is returned in location $FE.

----------

**24 - xchrout**

This is an output character routine that should be used when writing ML routines that need to output a character to the user.

----------

**25 - sound**

Makes various sounds.

_Usage:_

&,25

&,25,1

&,25,2

Beep

Siren

Bell

----------

**26 - getmdm**

Same as &,4.

----------

**27 - arraysav**

Save variable pointers. This saves the pointers that tell where BASIC variables start and end, so they can be later restored to erase unnecessary variables.

&,27

----------

**28 - arrayres**

Restore array pointers.

&,28

----------

**29 - usevar**

Get contents of a variable. This is the routine to call to read the value of a variable from machine language. The X register holds the variable # to access (see [variable table](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap3-1.html#vartab)). The contents of the variable is read into the buffer at $61.

----------

**30 - putvar**

Put value into a variable. This stores the contents of the buffer at $61 into a variable. The routine is meant only to be called from ML routines. The X register holds the variable # (see [variable table](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap3-1.html#vartab)).

----------

**31 - zero**

Set value to floating point 0. This stores the floating point equivalent of 0 into the buffer at $61.

----------

**32 - minusone**

Set value to floating point -1. This stores the floating point equivalent of -1 into the buffer at $61.

----------

**33 - getarr**

Get descriptor for TT$(X). This get the descriptor (length and pointer) of an element of the TT$ array. The element # is in the X register. The descriptor is stored in the buffer at $61.

----------

**34 - putarr**

Put descriptor for TT$(X). This stores the buffer at $61 as an element of the TT$ array. The element # is passed in the X register.

----------

**35 - getln**

Get string for TT$(X) into buffer. This gets the descriptor for an element of TT$() into the buffer at $61 and gets the corresponding string into the general text buffer at $CE77.

----------

**36 - putln**

Put string in buffer to TT$(X). Used in protocols.

----------

**37 - trapon**

Turn error trap on

Usage:

&,37

----------

**38 - trapoff**

Turn error trap off

Usage:

&,38

----------

**39 - prtln**

Print TT$(X). Used in protocols.

----------

**40 - forcegc**

This routine will force a fast garbage collect. This can be useful when you need to find out exactly how much memory is available.

----------

**41 - setbaud**

This sets the baud rate that IMAGE will use. Note that you should not change the baud rate while someone is connected, since this only changes the rate at which IMAGE sends/receives, and the modem will not follow.

_Usage:_

&,41,_x_

x=0

300 baud

x=1

Not used

x=2

1200 baud

x=3

2400 baud

----------

**42 - reserved**

Internal usage

----------

**43 - reserved**

Internal usage

----------

**44 - chatchk**

Checks for the presence of the Cht check mark.

----------

**45 - prtvar**

Will print a variable.

----------

**46 - prtvar0**

Will print a variable with MCI forced off.

----------

**47 - carchk**

Will check for presence of a carrier.

----------

**48 - getkbd**

Gets a character from the keyboard.

----------

**49 - getmod**

Gets a character from the modem, using ASCII translation.

----------

**50 - outscn**

Outputs a character to the IMAGE window.

----------

**51 - outmod**

Outputs a character to the modem with ASCII translation.

----------

**52 - chkflags**

This is the BASIC interface to the Lightbar.

_Usage:_

Described in the section ["The Lightbar."](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap3-3.html#thelightbar)

----------

**53 - disp4**

Loads the display for the IMAGE Terminal menu.

----------

**54 - editor**

This is the BASIC interface to the Editor.

_Usage:_

Described in the section "[The Editor.](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap3-3.html#theeditor)"

----------

The flags that can be used for the input routine are in the form of bits. Each value turns one option on or off:  
  

**Bit**

**Purpose**

1

Allow graphics characters

2

Disable "." on column 1

4

Disable P$ (prompt)

8

Disable £ key

16

Word wrap on

----------

**Variable Table:**

0 AN$ 5 D2$ 10 TT$ 15 LP 20 NL 25 EF 30 A% 35 C2$  
1 A$ 6 D3$ 11 NA$ 16 PL 21 UL 26 LF 31 B% 36 CO$  
2 B$ 7 D4$ 12 RN$ 17 RC 22 QE 27 W$ 32 DV% 37 CH$  
3 TR$ 8 D5$ 13 PH$ 18 SH 23 RQ 28 P$ 33 DR$ 38 KP%  
4 D1$ 9 LD$ 14 AK$ 19 MW 24 AC% 29 TR% 34 C1$

## Memory Locations

----------

Here is a list of memory locations used by IMAGE ML:

| **Location** | **Name** | **Use**                                                                                        |
| ------------ | -------- | ---------------------------------------------------------------------------------------------- |
| 97           | var      | Store value of variable for usevar, putvar, zero, minusone, getarr, putarr, getin, putin, etc. |
|              |          |                                                                                                |
| 830          | idlemax  | Maximum idle time allowed                                                                      |
|              |          |                                                                                                |
| 2024         | mjump    | Number of lines to skip for £J, £E, £D                                                         |
| 2025         | mresult  | Result of £T, £T                                                                               |
| 2026         | mspeed   | Print speed for £S                                                                             |
| 2027         | mprint   | Print mode for £P                                                                              |
| 2028         | mcolor   | Current color for £C                                                                           |
| 2029         | mprtr    | Printer flag for £L                                                                            |
| 2030         | mreverse | Reverse mode flag for £R                                                                       |
| 2031         | mci      | MCI on/off flag                                                                                |
| 2032         | mdigits  | Number of digits for £%                                                                        |
| 2033         | carrst   | Carrier flag                                                                                   |
| 2034         | tsp1     | Transmit speed lo byte                                                                         |
| 2035         | tsp2     | Transmit speed hi byte                                                                         |
| 2036         | chks     | Checkmark flag for Lightbar (left side)                                                        |
| 2037         | chks     | Checkmark flag for Lightbar (right side)                                                       |
| 2038         | readmode | Stores the unabortable file read flag                                                          |
| 2039         | filenum  | Stores the file number for read0/dskin                                                         |
| 2041         | abtchr   | Alternate abort character (works like <space>)                                                 |
| 2042         | clock    | Turns on BIG clock                                                                             |
| 2043         | filetyp  | Filetype for Punter transfer protocol                                                          |
|              |          |                                                                                                |
| 16384        | tempbott | Temporary storage for bottom of screen (for full screen)                                       |
| 16464        | tempbotc | Temporary storage for bottom of screen color memory (full screen)                              |
| 16544        | pmodetbl | Print mode definition table (for £P_x_ command)                                                |
|              |          |                                                                                                |
| 16640        | tempscn  | Temporary storage for top of screen (full screen)                                              |
| 16880        | tempcol  | Temporary storage for top of screen color memory (full screen)                                 |
|              |          |                                                                                                |
| 17124        | curdsp   | Current display number (for top of screen)                                                     |
| 17138        | mask     | Password mask character                                                                        |
| 17139        | scnmode  | Screen mode (full or split)                                                                    |
|              |          |                                                                                                |
| 53248        | local    | Flag for forced local mode (if enabled, nothing is output to modem)                            |
| 53249        | case     | Uppercase lock flag                                                                            |
| 53250        | editor   | Flags for the &,1 routine                                                                      |
| 53251        | tsr      | Time remaining                                                                                 |
| 53252        | llen     | Line length for &,1                                                                            |
| 53254        | chat     | Flag for returning from & for an abort                                                         |
| 53256        | chatpage | Turns on the flashing page                                                                     |
| 53257        | access   | Shadow for ac%                                                                                 |
| 53258        | mxor     | Carrier XOR value                                                                              |
| 53259        | mkolor   | Kolorific mode flag                                                                            |
| 53260        | mupcase  | Uppercase mode flag                                                                            |
| 53261        | irqcount | IRQ slowdown flag                                                                              |
| 53262        | trans    | ASCII translation flag                                                                         |
| 53263        | index    | Length of line returned by inline                                                              |


## Using Modules

In IMAGE BBS, the "main" program, also known as the "im" file, resides at $4601 in memory. Other modules, called "plus files," load at $0801. The area designated for plus files is $0801-$4000, which is about 14k. (This is about 56 CBM 1541 "blocks.") The main file starts at line 1000. Modules start at line 1. When you enter a module, it is _always_ entered with either a GOTO 1, or GOSUB 1.

When a module starts to become too large for the 14k buffer, you can further divide it into sub-modules. The most common way is to use "mini-modules." These are modules that can be up to 4k in length, or about 17 disk blocks. The mini-modules load at $3001 in memory. When one is loaded, it is effectively appended on to the end of the plus file that is currently in memory. Therefore, you cannot start a mini-module at line 1. All of the line numbers in the mini-module _must_ come _after_ the line numbers in the plus file. If there is an overlap, it may crash the system, forcing you to reboot. For this reason, be _very_ careful when you program using modules.

There are a few restrictions that you must be aware of. First, the mini-module and the plus file must share the same area of memory. So, even though the maximum size of a plus file is 14k, if you are using a mini-module, the maximum size for the plus file becomes 10k, and the mini module is 4k, which is a total of 14k. There are other sizes of modules, and here is a chart to explain them:

**Size of modules:**

**Plus file length:**

**Module length:**

**Module address:**

No module

14k / 56 blocks

Mini-module

10k / 41 blocks

4k / 17 blocks

$3001

Small module

6k / 25 blocks

8k / 33 blocks

$2001

Large module

2k / 9 blocks

12k / 49 blocks

$1001

## Using ML Modules:

If you wish to use ML modules, more commonly known as "++" files, the &,7,dv%,2 command will load them for you. You can call any of the normal IMAGE & routines by loading the Accumulator with the & number, and X and Y with the parameters. Then a JSR $DD01 will call the routine. The area set aside for ML modules is from $C000-CA7F.

## RS232 Routines:

The RS232 routines that IMAGE uses reside in memory from $4300-$45FF. There is a jump table at $4300 which has the ONLY safe entry points into these routines. NOTE: Calling some of these routines will result in "strange" things happening, be _very_ careful.

$4300 Install

This is the install routine that is called when the system is booted. _Do not_ call this routine, since it _will_ crash your system.

$4303 Enable

This routine enables the NMI interrupts that perform the RS232 I/O. Note that during such things as disk access these must be turned off, and then turned back on when disk access is finished. IMAGE handles this for you, and you should never need to call this routine.

$4306 Disable

See above for "Enable."

$4309 RSGet

This gets a character from the RS232 device. Note that RS232 has a 256-byte "ring" buffer so that characters which are received when the system is busy are not lost. The character is returned in the Accumulator.

$430C RSOut

This will output a character to the RS232 device. The character is passed in the Accumulator. Note that the routines use a technique called "double buffering" which means that while one character is being transmitted, another can be put into a "holding" buffer, until the first character is done. This allows the system to output a character, and then go back to doing more processing while it is being sent. This keeps the screen cursor sychronized with the cursor on the user's side, while still gaining the benefit of a buffered I/O system.

$430F SetBaud

This will set the baud rate as defined by an internal table. See the listing for &,41.

## The Swapper

IMAGE uses a sort of virtual memory mechanism to allow the 12k of RAM that is "hidden" in the 64 to be used. RAM from $D000-$FFFF is used to store many of the routines that IMAGE does not need to use as often as others. Examples are the disk input routine (&,2) and the entire editor system! These routines are accessed using the "swapper." This is a routine that swaps the needed routines into memory, and swaps whatever is in that memory to the hidden RAM. The routines are then executed, and then swapped back to the hidden RAM. Thus, the 12k of hidden RAM can be used to store more ML for the IMAGE system. In IMAGE 1.2, all but 2k of this RAM is used, and in future versions, that last 2k will be used!

The swapper is located at $CA80. To use it, you set the Accumulator and the Y register with the starting page numbers to swap, and the X register to how many pages of RAM to swap. Thus, to swap memory from $C000-$C2FF with the memory from $C300-$C5FF, you would do this:

> LDA #$C0  
> LDY #$C3  
> LDX #$03  
> JSR $CA80

To swap it back again, repeat the same sequence of commands. Be very careful when using this routine, since it does not care _what_ it swaps, and will try to swap anything you tell it to!

## The Lightbar

The lightbar is controlled by IRQ routines which read the function keys, and make the necessary screen/memory changes that are requested. There is an & [command] which allows you to get or set the status of the lightbar. This is &,52.

There are several functions implemented in this command in version 1.2. You can clear/set/toggle/read any individual checkmark. Here are some examples:

> &,52,0,0 Clear the check on the left side of Sys.
> 
> &,52,0,1 Set the check on the left side of Sys.
> 
> &,52,0,2 Toggle the check on the left side of Sys.
> 
> &,52,0,3 Read the check on the left side of of Sys.
> 
> [Additionally, there is another function I discovered.
> 
> &,52,x,4 moves the "lit" section to positions 1-8 (page 1) or 9-16 (page 2). Very useful.
> 
> Also, mainly because I get tired of flipping through the sysop documentation for IMAGE, I'll include a section here on what the various positions on the Lightbar are for:

Left

> L Chk R

Right

Sysop available

> 0 Sys 1

Trace mode on

Change access

> 2 Acs 3

Block 300 baud users

Local logon

> 4 Loc 5

Pseudo-local mode

Alter time

> 6 Tsr 7

Toggle prime time

Enter chat

> 8 Cht 9

Toggle local bells

Private system

> 10 New 11

Disable screen blanking

Print output

> 12 Prt 13

Print log entries

Close U/Ds

> 14 U/D 15

No 300 baud callers

ASCII translation on

> 16 Asc 17

Linefeeds on

ANSI graphics on

> 18 Ans 19

IBM graphics on

Expert mode on

> 20 Exp 21

Main prompt macros on

Credit when file validated

> 22 Fn5 23

Log off after file transfer complete

Undefined in stock system

> 24 Fn4 25

Undefined in stock system

Undefined in stock system

> 26 Fn3 27

Undefined in stock system

Undefined in stock system

> 28 Fn2 29

MCI off

Undefined in stock system

> 30 Fn1 31

Undefined in stock system

> Certain mods like the Graphic Menu or Callback Validator will use the Fn areas for their own use.]

## The Editor:

The programming of the IMAGE editor is best left to those who know a _lot_ about the IMAGE system. There is an & [command] which will make the necessary calls into the editor ML. This ML resides from $D000-$DFFF, and is swapped into memory from $1000-$1FFF by the swapper when it is called. There are 3 legal entry points, which are accessed by &,54, &,54,1, and &,54,2. The first entry point is the "normal" entry. This puts the user into the editor with an empty buffer. The second entry does not clear the buffer. The last entry is the entry that you would use in [writing] an extended command, if the command which was typed was not a recognized command.
