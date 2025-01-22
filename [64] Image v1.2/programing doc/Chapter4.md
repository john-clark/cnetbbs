[Index/Preface](index-preface.md) | [Chapter I ](Chapter1.md) | [Chapter II ](Chapter2.md) | [Chapter III](Chapter3.md) | [Chapter IV](Chapter4.md) | [Chapter V](Chapter5.md)

# Chapter IV: Disk File Formats

  
This chapter will give you the formats for all important files on your system. The maps will include the name of each file, the information stored in each record, and the associated system variables.  
  
####  1. u.config (user statistics) REL 254 bytes per record  
  
Field | Variable | Description
--|--|--
1 | NA$ | Handle
2 | PW$ | Password
3 | FF$ | First name
4 | LL$ | Last name
5 | PH$ | Phone number
6 | LD$ | Last call date (for new messages)
7 | AC% | Access level
8 | CT% | Calls today
9 | TC% | Total calls
10 | CO% | Computer type (CO$(CO%) to see text)
11 | LL% | Line length
12 | UL   | Upper/lowercase flag*
13 | LL | Linefeed flag (1=on)
14 | EM | Expert mode flag (1=on)
15 | DC | Total files downloaded
16 | UC | Total files uploaded
17 | BD | Total blocks downloaded
18 | BU | Total blocks uploaded
19 | CR | Credit points
20 | PS | Total posts
21 | RP | Total responses
22 | D5$ | True last call date
23 | FL$ | User flags
24  | JN$ | Joined/unjoined flags
\* Note that the UL flag is used for the default transfer protocol if your system uses the TurboRel Subs.

  
#### 2. e.data (system data) REL 40 bytes per record  
  

Record # | Variable | Description
--|--|--
1 | CA | Total calls to the system
2 | AG$ | Access group name (AG$) for group 0*
3 |  | Access group 1 (see record #2)
4 |  | Access group 2 (see record #2)
5 |  | Access group 3 (see record #2)
6 |  | Access group 4 (see record #2)
7 |  | Access group 5 (see record #2)
8 |  | Access group 6 (see record #2)
9 |  | Access group 7 (see record #2)
10 |  | Access group 8 (see record #2)
11 |  | Access group 9 (see record #2)
12 | UR | Highest user account minus one
13 | OC$ | 30 character string of 0's and 1's for SB
14 |  | Same as record 13 for UD
15 |  | Same as record 13 for UX
16 | UH | Number of active user accounts
17 | D3$ | Last caller on system
18 | PP$ | System remote password
19 | D6$ | Time of last user logoff (11 digits)
20 | PT%, P2%, P3% | Time allowed during prime time (P1%), prime time start (P2%), prime time end (P3%)
21 | FL$(0) | Default flags for access group 0.
22 | FL$(1) | Default flags for access group 1.
23 | FL$(2) | Default flags for access group 2.
24 | FL$(3) | Default flags for access group 3.
25 | FL$(4) | Default flags for access group 4.
26 | FL$(5) | Default flags for access group 5.
27 | FL$(6) | Default flags for access group 6.
28 | FL$(7) | Default flags for access group 7.
29 | FL$(8) | Default flags for access group 8.
30 | FL$(9) | Default flags for access group 9.
31 | L1 | Next available user account
32 | AT$ | Modem command string
\* Note that in records 2-10, the access group name is preceded by 4 control codes which designate:  

-   time per call (0=unlimited)
-   calls per day (0=unlimited)
-   downloads per call (0=unlimited)
-   maximum idle time (1-9 minutes)  
    

These control characters may be seen using the +.access editor.

  
####  3. e.stats (system stats) (REL) 20 bytes per record  
  
  |  | Last | Log | Current | Total | 
--|--|--|--|--|--
Feedback | 1 | 12 | 23 | 30
Sysop Mail | 2 | 13 | 24 | 31
User Mail | 3 | 14 | 25 | 32
Posts | 4 | 15 | 26 | 33
Responses | 5 | 16 | 27 | 34
Uploads | 6 | 17 | 28 | 35
Downloads | 7 | 18  | | 36
New Users | 8 | 19 | 29
Calls | 9 | 20
% Used | 10 | 21
% Idle | 11 | 22
Record 37: Total minutes system used overall
Record 38: Total minutes system idle overall

  
#### 4. bd.data (SEQ)  
  
bd.data is a SEQ file which your system reads once during boot. If any changes are made to this file, you must reboot your system to activate them.  
  

Line | Variable | Description
--|--|--
1 |  | System disk device
2 |  | System disk drive
3 |  | E-Mail disk device
4 |  | E-Mail disk drive
5 |  | Etcetera disk device
6 |  | Etcetera disk drive
7 |  | Directory disk device
8 |  | Directory disk drive
 |  | 
10 |  | Plus file device
11 |  | Plus file drive
12 |  | User file device
13 |  | User file drive
14 | CC$ | System identifier
15 |  | New user credits
16 |  | Highest device number
17 |  | Highest drive number
18 | BN$ | BBS name
19 | PO$ | Main prompt


#### 5. U/D directory file format (SEQ)  
  
Line |  Variable | Description
--|--|--
1 | RN | Number of files in directory (60 max)
2 | F%(X) | File size in CBM blocks
3 | NN$(X) | User ID number padded with 0's, plus handle
4 | DT$(X) | Upload date plus last download date plus filename, type
5 | ED$(X) | Description of file
6 | C%(X) | Times downloaded
7 | D%(X) | Computer type 0-9 (0=any)
Lines 2-7 are repeated throughout the file, once for each file in the directory. The number of times is determined by the first file entry (RN).  
  
#### 6. SB directory format (SEQ/REL)  
  
Position | Variable | Description
--|--|--
1 | RN | Number of posts in directory (60 max)
2 |  | Title of original message
3 |  | ID# (or net ID#) of poster, plus handle
4 |  | Date of message, plus date of last response
5 |  | Total number of responses 
Lines 2-5 are repeated throughout the file, once for each file in the directory. The number of times is determined by the first file entry (RN).  
  
#### 7. e.Sub, e.U/D, e.U/X file formats (REL)  
  
```Record 1```
Total number of subs, libraries defined

```Records 2-901```
Field | Variable | Description
--|--|--
1 |  | Password for password-protected board
2 | AC%(X) | Access code
3 | BN$(X) | Board name
 |  |  | Unused
5 |  | Device
6 |  | Drive
7 |  | Open/close flag

  
#### 8. E-mail format (m.<handle>) SEQ  
  

Line | Description
--|--
1 | Handle of sending user
2 | ID of sending user
3 | Date sent
4 | [ title ]
.   | 
.   | text of message 
n  | 
n+1 | ^ at end of message

[Lines 1-n+1 are repeated throughout the file, once for each message in the user's mailbox.]


