[Index/Preface](index-preface.md) | [Chapter I ](Chapter1.md) | [Chapter II ](Chapter2.md) | [Chapter III](Chapter3.md) | [Chapter IV](Chapter4.md) | [Chapter V](Chapter5.md)


# Chapter V: Variable Usage

Within Image, there are certain variables which can be considered "reserved." This does not mean that you cannot use them, per se, but that they can only be used in conjunction with specific purposes. Some variables may be used any time, but have a specific purpose. Some variables can be used with certain subsystems, but not with others. Some variables may be used anywhere, but change continually. This is explained in detail in the following paragraphs.  
  
An example of a variable used for a specific purpose is NA$. This variable is used to print the handle of the user online. Storing something for a module in this variable would cause an undesirable effect. Basically, these types of variables are used to control system statistics and are best left alone, only to be used to output information. These variables are sometimes used as interfaces between the BASIC and ML, an example being PL. Setting PL to 0 will cause all user input to be in the form of upper and lower case characters. When you set this in BASIC, it causes the ML input routines to recognize the upper/lower case characters.  
  
The main variables that can be used sometimes are arrays. Depending on which subsystem you are in, the arrays may or may not be in use. If they are not in use, it is safe to use them. The only exceptions to this is ST(X), DV%(X) and TT\$(X). ST(X) holds the BAR stats, changing the values of this array should be reserved for updating the BAR stats. DV\%(X) is the system device designator. Altering this will change the device accessed by the system. TT\$(X) cannot be used in a module that calls the editor. All text stored in the editor is put into TT$(X).  
  
Some variables are intended to continually change. These include variables that will print text to the screen and modem, as well as variables that form links between the BASIC and ML portions of the program. Examples are A$ and AN$. When used in conjunction with & or &,0, the value of A\$ will be printed to the screen and modem. All response entered at a prompt will be stored in AN$. These variables have a set purpose, but are intended to change.  

### Temporary Storage Variables

Virtually any single character alphabetical string (A-Z) can be used as a temporary storage variable with the exception of:  

-   X$ which holds the system drive/LU identifiers,
-   U$ which holds the commands stacked at a prompt, and
-   P$ which is an ML-reserved variable, and contains the text of the last active prompt.

One of the other advantages to using the single character strings is the capability of outputting the current definition of the variable using the £vx MCI command. Also note that any definition of A$ should be temporary and avoided for all purposes except for output to the screen and modem.  
  

### Reserved String Variables

The current reserved string variable listing for Image v1.2 is as follows:  
  
|  |  |  
|--|--|
A$ | Reserved for output to screen and modem.
AG$ | Access group name of user currently online. (Also £vm)
AK$ | Prints line across screen (" " + "-" * LL% -2 + R$). (Also £vj)
AN$ | Last user input. (Also £v7)
BN$ | Current name of your BBS. (Also £v5)
C1$ | Chat mode entry message.
C2$ | Chat mode exit message.
C3$ | "Returning To The Editor" message.
CC$ | 2 character system identifier (Also £vn)
CM$ | Current location in AREA window.
D1$ | Current time and date information in 11 digit format. (Also £v0)
D2$ | Time and date of last logoff, also Library name at entry. (Also £v8)
D3$ | Handle of last user on the system. (Also £v9)
D4$ | Current ML protocol in memory. (Also £vl)
D5$ | True last call date of user online in 11 digit format. (Also £vk)
D6$ | Logoff time of last user.
DD$ | System identifier + user ID number.
DR$ | Currently active drive/LU number + ":".
FF$ | Real first name of user online.
FL$ | 15 character string which determines the user's online flags.
I1$ | Access level + handle of the sysop.
I2$ | Expert flag + phone number + first name + " " + last name of sysop
I3$ | Access group name of sysop
LD$ | Last call date of user online in 11 digit format. Used for new message reads.
LL$ | Real last name of user online.
LT$ | Logon time of user online.
NA$ | Handle of current user online. (Also £v2)
NL$ | Null character [CHR$(0)].
NM$ | Last network sort in 11 digit format.
P$ | Current prompt text.
PH$ | Phone number of current user online. (Also £v4)
PO$ | Text for system main level prompt.
PP$ | System password (change with PC command).
PR$ | Name of current plus file in memory.
PW$ | Password of current online user.
QT$ | Quotation mark [CHR$(34)].
R$ | Return [CHR$(13)].
RN$ | Real name of user online (FF$ + " " + LL$, also £v3)
SY$ | Current subsystem active.
TI$ | C= TOD clock.
U$ | Reserved for command stack.
X$ | System drive/LU designators.


### Reserved Integer Variables

The current reserved integer variables for Image v1.2 are as follows:  
  
|  |  |  
|--|--|
AC% | Access level (0-9) of user online.
AO% | Access level of user at login.
CO% | Computer type of user online (1-9)
CT% | Number of calls today by the user online.
D1% | Currently active device number.
D2% | Currently active drive/LU number.
D3% | Currently active drive/LU number.
DA% | Number of downloads allowed per call (0=unlimited).
DC% | Number of downloads this call by user online.
DV% | Active device number.
I% | Instant mode flag.
KP% | Last key pressed.
LL% | Line length (38-80) of user online.
P1% | Time allowed during prime time.
P2% | Time that prime time begins.
P3% | Time that prime time ends.
PT% | Prime time flag (1=active).
TC% | Total calls to the system by the user online.
TR% | Time remaining on system (in minutes).

### Reserved Floating Point Variables

The current reserved floating point variables for Image v1.2 are as follows:  


|  |  |  
|--|--|
BD | Total number of CBM blocks downloaded by user online.
BU | Total number of CBM blocks uploaded by user online.
CA | Total number of calls since system start.
CN | Total number of calls since last reboot.
CR | Total credit points of user online.
DC | Total number of files downloaded by user online.
DR | Currently active system device (1-6).
EL | Reserved for future expansion.
EM | Expert mode flag.
F1 | System flag.
F2 | System flag.
F3 | System flag.
F4 | System flag.
ID | ID number of user online.
I1 | Next available user account.
I2 | Flag for reserved system.
I3 | Flag for reserved system.
LC | Flag for active subsystem menu.
LE | Editor lines allowed for user online.
LF | Linefeed flag (default protocol for TurboRel subs).
LP | Output control flag.
MF | Reserved for ML use.
NL | C/G mode flag.
NM | Network flag.
PL | Input control flag.
PM | Prompt mode flag.
PR | Active ML protocol in memory.
PS | Total posts by user online.
QB | Modem speed (BPS rate).
QE | Reserved for ML use.
RC | Abort flag.
RQ | Reserved for ML use.
SH | Checks for spacebar hit.
SR | Reserved for ML use.
ST | I/O status.
UC | Total files uploaded by user online.
UH | Number of active user accounts.
UL | Upper/lowercase flag.
UR | Highest user ID +1.
  
### Arrays

The following arrays are dimensioned by the BBS. Most can be used for your own programs, except where noted.  

|  |  |  
|--|--|
| AC%(31) | Can be used for any plus file outside of UD/UX/SB. |
BF(X,Y) | Blocks free on system drives. Should never be used.
CO$(9) | Text for computer types supported. Should never be used.
DV%(X) | Device numbers for system drives. Should never be used.
FL$(9) | Default flags for access groups 0-9. Should never be used.
SO%(31) | Can be used for any plus file outside of UD, UX, SB.
ST(60) | Status. Should never be used.
TT$(254) | Can be used anywhere that does not use the editor.
