[Index/Preface](index-preface.md) | [Chapter I ](Chapter1.md) | [Chapter II ](Chapter2.md) | [Chapter III](Chapter3.md) | [Chapter IV](Chapter4.md) | [Chapter V](Chapter5.md)


# Chapter II: BASIC Subroutines

The purpose of this chapter is to provide you with all existing subroutines available for your use. All routines are shown being accessed through their recommended entry points. Some routines may be accessed through several entry points; others may not. Failure to use the proper entry points of the routines provided may cause undue garbage on the CPU stack or other problems with your programs.

1001

Position record of relative file currently open as logical file #2.

Expects:

X: Record desired.

Returns:

E%: Error number.  
E$: Error message.  
T%: Track number.  
S%: Sector number.

----------

1004

Checks status of user flags 1-15.

Expects:

A: flag number.

Returns:

A=0: Not accessible  
A=1: Access allowed

### User Flags

Each user has a total of 15 flags which decide whether or not they have access to a particular function or area of the system. These flags are held in a fifteen digit string, each digit representing a seperate flag which can be checked by setting the variable A to the flag number (1-15) and issuing a GOSUB 1004 command. If A returns with a value of zero, access is denied. The values of each flag are as follows:

 1 Non-Weed Access

 6 Editor Lines

11 BAR/Log Access

 2 Credit Ratio

 7 Unlimited Credits

12 Sub Maint

 3 Local Maint

 8 Remote Maint

13 Files Maint

 4 Post/Respond

 9 E-Mail Access

14 MCI Access

 5 U/D Access

10 User List Access

15 Prime Time U/D Access

----------

1005

Upper/lowercase input.

Expects:

P$: Displays prompt  
Number of characters allowed in input is governed by POKEing location 53252: 0-255

Returns:

AN$: User input

----------

1006

Uppercase input - accepts a line of text, delimited by the RETURN key.

Expects:

Same as above

Returns:

AN$: User input  
U$: Duplicate of AN$, for command stacking

----------

1007

'Hotkey' input - waits for a single key. RETURN doesn't need to be pressed.

Returns:

AN$: User input

----------

1009

Set drive - Sets active system drive, 1-6.

Expects:

DR: 0-6. 0 is the drive designated by PF, TF, TF, MF, or RF subsystems. 1-6 are the [drive designators](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap1.html#drives) used by the system.

Returns:

DV%: Active device number  
DR$: "<_active device_>:"

----------

1010

Closes and then (re)opens the command channel—logical file #15—on the device and drive requested, as above

Expects:

Same as above

----------

1011

Opens file.

Expects:

DR: Drive designator  
A$: Filename. Add ",s,[r|w|a]" for SEQuential files, ",l,"+CHR$(_<recordlength>_) for RELative files.

Returns:

E%: Error number

----------

1012

Read error channel of currently active device/drive

Returns:

A$: Error message  
E%: Error number  
E$: Copy of A$  
T%: Track  
S%: Sector

----------

1013

Loads plus file module from plus file disk.

Notes:

-   The name is stored in CM$ and output to the top of the AREA window on the sysop's screen.  
    
-   A$ (the filename to load) does not need a leading "+." The drive designators and "+." are automatically added.

Expects:

A$, CM$: As noted above.  
DR: Drive designator

----------

1016

Same as above, but will load the plus file and proceed to line 1 if no error is encountered.

Expects:

Same as above.

----------

1023

Scratch-and-replace. Scratches (deletes) the specified file and re-opens it for writing. Note: This routine should _only_ be used for SEQuential files.

Expects:

A$: Filename to be scratched.  
DR: Drive designator.

Returns:

E%: Error number (?)

----------

1024

Scratch (delete) specified file.

Expects:

Same as above.

Returns:

Same as above.

----------

1025

Update BAR stats. This routine will update the ST() array of the Board Activity Register. Note: Line 1025 will fall through to line 1026 before RETURNing.

Expects:

X: Set to the number in 4. Access group name of user currently online. (Also .  
I: Value to be added to ST(X)

----------

1026

Outputs the value of ST(X) to record X of RELative file currently open on logical file number 2. Note: "e.stats" should be opened before calling this routine.

Expects:

X: Record number.

Returns:

E%: Error number (?).

----------

1027

Sets active device and drive to the e. drive, and opens a SEQuential file.

Expects:

B$: Filename without e. prefix.  
A$: R, W, or A, depending if you want to read, write, or append to the file.

----------

1030

Read currently open SEQuential file until the ^ character is encountered, then reset output defaults and return.

Expects:

SR: the logical file number of the currently open file (2 in most cases)

----------

1034

Deletes user handle from alphabetical index.

Expects:

AN$: Name of user to delete from index.

----------

1038

Inserts user handle into alphabetical index.

Expects:

AN$: Name of user to delete from index.

----------

1040

Search alphabettical index for user name.

Expects:

AN$: Name of user to search for in index.

Returns:

AN$: 1 if found, 0 if not. [Note: Why use a string variable? I'm going to check this for accuracy.]

----------

1060

Opens RELative file `e.stats` on your etcetera disk.

----------

1062

Opens e-mail file for desired user.

Expects:

TT$: The name of the user to send mail to, minus the m. prefix.  
A$: R or W, depending on whether you want to read from or write to the file.

----------

1063

Opens RELative file e.data on your etcetera disk.

----------

1064

Opens the daily log.

Expects:

A$: R, W, or A, depending if you want to read, write, or append to the file.

----------

1065

Opens RELative file u.config on your e. file disk.

----------

1067

Loads plus file module from plus file disk and proceed to line 1 if no errors are encountered.

Notes:

-   The name is stored in CM$ and output to the top of the AREA window on the sysop's screen.  
    
-   A$ (the filename to load) does not need a leading "+." The drive designators and "+." are automatically added.

Expects:

A$: As stated above.

----------

1070

Assembles user's online stats into a single string (A$), each separated by a carriage return. Positions RELative file pointer and prints A$ to the u.config file. The u.config file must be opened prior to calling this routine.

----------

1075

Clears the screen, outputs SEQuential file to screen and modem.

Expects:

A$: Name of file.  
DR: Drive designator.

----------

1076

Outputs SEQuential file to screen and modem without clearing screen first.

Expects:

Same as above.

----------

1079

Reads blocks free and updates sysop screen.

Expects:

DR: Device designator.

Returns:

BF: Blocks free.

----------

1089

Disk directory.

Expects:

DR: Device designator.

----------

1093

Clears all programmable arrays (those not DIMensioned at the start of the program).

----------

1095

Adds a line to the system log and displays on the printer (device #4).

Expects:

A$: Line to be output.

----------

1096

Displays a line on the printer (device #4).

Expects:

Same as above.

----------

1098

Resets system to default outputs, displays current prompt to the AREA window, and waits for uppercase input of up to 38 characters.

Expects:

P$: Prompt to display.

----------

1099

Displays first 11 characters of prompt, and first 4 characters of AN$ to AREA window.

Expects:

P$: Prompt to display.  
AN$: User input.

----------

1300

Loads module (minus the +. prefix) and GOSUBs to line 1 of the module. This routine is for all level command type modules like +.ST, +.XP, +.LD, etc. These types of modules must return control to the main program with a RETURN.

Expects:

Z$: Name of module to load.

----------

1301

Loads module (minus the +. prefix) and continues to line 1 of the module, unless an error is encountered in which case it will return to the main prompt. This is a good routine to load main level command modules like +.BB and +.CP.

Expects:

Z$: Name of module to load.

----------

1348

Outputs SEQuential file s.new user to screen and modem.

----------

1349

Outputs SEQuential file s.config to screen and modem.

----------

1350

Clears screen and outputs SEQuential file.

Expects:

A$: Filename to be output, minus s. prefix.

----------

1351

Clears screen and outputs SEQuential file s.menu plus a number. It is followed by s.menu 1 if the menu number chosen is greater than 1.

Expects:

LC: Number of menu to view:  

1.  Main menu
2.  Sub-boards
3.  BBS editor
4.  Sysop functions
5.  Upload/download
6.  Electronic mail
7.  Directory subsystem
8.  End-of-bulletin commands
9.  Full disk exchange
10.  Voting subsystem

----------

1354

Read SEQuential file from drive. If no device/drive are specified, read will be from device 8, drive 0.

Expects:

X: Drive to have file read from.  
AN$: Command and device,drive. (For example, RD8,0).

----------

1360

Display message to sysop screen AREA window.

Expects:

CM$: 14 characters maximum.

----------

1375

Display online user's computer type to chat window.

----------

1376

Display message to computer type/chat message window.

Expects:

AN$: Message to display, 16 characters maximum.

----------

1450

Prompts for device and drive, then prompts for disk command before returning.

Notes:

-   If the command starts with n0: or s0:, you will be prompted "Are you sure?"  
    
-   @ will return status of drive.

----------

1460

Add credits in the amount specified to user online.

----------

1470

Input routine for device, drive prompt.

-   If the device number is followed by a comma and a number in the range of 0-255, the second number represents the drive/logical unit number. Default device, drive is 8,0.
    
-   Values of 1-6 will return system drives.
    
-   Values of 7-15 will return the device number for each of the system drives.

Returns:

D1%: Device number.  
D2%: Drive number.

----------

1490

Add a line to the daily log.

Expects:

A$: Line to be added.

----------

1500

Translate IMAGE-encoded [function keys](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap1.html#fkeys) to text.

----------

1520

Time-of-day clock routines.

----------

1604

BBS text editor entry routine.

Returns:

TT$(): All lines typed will be stored in this array.  
KK: Equals the number of the last line entered. If 0, no text was entered or the editor was aborted.

----------

1610

Alternate editor entry. This will not clear the text already in memory.

Returns:

Same as above.

----------

1634

Change access. This will change the user's flags to that of the access group it has been changed to via the Acs checkmark.

Expects:

AO%: Old access flags.

Returns:

AC%: New access flags.

----------

1640

Chat request. The first time a user requests chat, s/he will be asked a reason for chat. Every time thereafter, they will be told the page function is on.

----------

1656

Displays current time and date, and minutes left for this call.

----------

1678

Feedback. This will let the user leave a message to the sysop. Each user is allowed to leave two messages per call.

----------

1694

Logs the user off and resets BBS for incoming calls.

Notes:

-   If O is followed by a #, then the user's last call date will _not_ be updated. [Note: I haven't been able to verify this.]
    
-   If the last character of the command is !, then the user will not be asked to log off, but be immediately disconnected.  
    
-   On a normal logoff, the user's last call date is updated to the time the user logged on, not the time of logoff.

----------

1736

Load ML module into memory at $C000 (49152).

Expects:

A: Number of ML module to load.

0.  Punter
1.  Xmodem
2.  Copier
3.  Relaxed Punter
4.  Indexer
5.  Clock

----------

1811

Main system prompt entry. Clears arrays.

----------

1812

Alternate main system prompt entry.

----------

1901

Output Are You Sure? and fall through to the "Yes/No" routine below.

----------

1902

"Get key" routine. Waits for a user to hit a key (Y or N). If Y is hit, Yes! will be output, otherwise No! will be output.

Returns:

A=0: N or any other key other than Y was entered.  
A=1: Y was entered.

----------

1903

Same as above, except you must add your own "get key" routine, most likely calling line 1007.

----------

1908

Displays current time to screen and modem, also minutes left if the caller does not have unlimited time.

----------

1910

"Say" routine. Reads a random quote from the e.say data file and outputs it to the screen and modem.

----------

1914

Resets all system output to default parameters.

----------

1915

Checks for local console (ZZ) mode.

----------

1920

Outputs Aborted! to screen and modem.

----------

1980

Outputs record from e.text (a file that contains various customizable error messages such as Not cleared for this function.)

Expects:

X: Record number.

----------

1985

Outputs Sorry, _b$_ limit exceeded.

Expects:

B$: Whatever you want it to be: time, credit...

----------

1989

Outputs Illegal Command message.

----------

2000-  
2015
