[Index/Preface](index-preface.md) | [Chapter I ](Chapter1.md) | [Chapter II ](Chapter2.md) | [Chapter III](Chapter3.md) | [Chapter IV](Chapter4.md) | [Chapter V](Chapter5.md)

# Chapter I: General Information

There are several things which are often used and would fit the description of general information. The items covered in this chapter are used in almost every module you can find.

### The Function Keys

IMAGE BBS uses function keys to represent specific ASCII characters which:

-   allows typing special characters in quote mode rather than using CHR$() codes, and
    
-   avoids the pitfall of truncating lines, or the necessity of using custom I/O routines to read SEQuential data files.
    

		F1: Comma          (,)

		F5: Quotation mark    (")

		F2: Question mark (?)

		F6: RETURN [CHR$(13)]

		F3: Colon (:)

		F7: Asterisk          (*)

		F4: Equal sign (=)

		F8: Up-arrow          (^)

### The Drive Designators:

IMAGE BBS uses six drive [designators to] identify the system drive in which to find a specific file. The active drive is set by setting the variable DR to a value of 1 through 6 as I will describe below:

1: System drive. This drive should contain all of your s.* files. When writing your own modules, all files which are usually read but NOT changed often (like intro screens) should carry the s. prefix and be stored on this device.

2: E-mail drive. This drive contains all mail (m.*), forced mail (fm.*), and network (nm.*) files.

3: Etcetera drive. This is one of the most active drives on your system. It contains all files which change often, and should be used to store data which needs to change frequently. [Note: these files have an e.* prefix.]

4: Directory drive. This drive holds all the sub-directories (d.* files) used by the system.

5: Plus-file drive. This drive holds all IMAGE BBS program modules.

6: User drive. This drive is used to store the user records and alphabetical user list.

### Time and Date Format

IMAGE BBS uses an 11-digit string to represent the current time and date. This information is stored in D1$.

	1  90 11 03 80 45    IMAGE BBS will translate this into the string  
	^  ^  ^  ^  ^  ^     "Sun, Nov  3 1990  12:45 PM"  
	|  |  |  |  |  |  
	|  |  |  |  |  +---- Minutes  00-59   
	|  |  |  |  |  
	|  |  |  |  +------- Hour     00-11: AM         
	|  |  |  |                    80-91: PM (subtract 80 to get correct hour)  
	|  |  |  |  
	|  |  |  +---------- Date     01-31  
	|  |  |  
	|  |  +------------- Month    01-12  
	|  |  
	|  +---------------- Year     00-99     (plus hard-coded century base)  
	|  
	+------------------- Day       1-7      (1=Sunday, 7=Saturday)

[Note: Spaces and diagram added for clarity. Also, one thing the manual doesn't mention is putting CHR$(4), CTRL-D, in an & statement followed by a properly formatted 11-digit string will display a readable time/date stamp. To wit,
	
	&"[CTRL-D]19011038045"

will echo the same string as at the top of this explanation.]

### Carrier Loss

All prompts for user input must be protected against a lost carrier! This is simple, and easily forgotten. If the carrier is lost, the system will automatically drop the user's time to zero. Time remaining is stored in the integer variable TR%. The simplest way to protect your system is to check the value of TR%: if it is less than one either GOTO line 1811, or RETURN if it is a subroutine.

### Access Levels

IMAGE BBS uses the following table to determine which access groups (0-9) have access to seperate areas of the system.

| **Group** | **Value** | **Group** | **Value** |
|--|--|--|--|
| 0 | 1 | 5 | 32 |
| 1 | 2 | 6 | 64 |
| 2 | 4 | 7 | 128 |
| 3 | 8 | 8 | 256 |
| 4 | 16 | 9 | 512


To figure out which access levels would have access to certain areas, you must add the values of the access groups you wish included together. For example, if you wanted all groups allowed access to the function, you would need an access code of 1023. If you just wanted levels 8 and 9, the access code would be 768 (256+512). [Note: Most prompts that ask for access levels will let you type a question mark and RETURN, and the system will figure out the correct numerical value for you.]

### Plus Files

A plus file is a BASIC module which is loaded into memory when needed by the BBS. The maximum size that any one plus file is 56 CBM blocks. There are two distinct types of plus files: the standard plus file, and the mini plus file.

The standard plus file can range from lines 1 to 999.

-   Under no circumstances should you allow your program to fall through past line 999.
    
-   The last line of the program should be a REMark.
    
-   Depending on the type of module, it should return control to the main system via a GOTO 1811 or a RETURN.
    

The mini plus file is a smaller module which may be loaded between the plus file and the main BASIC program. Care should be taken when using these types of modules. I will cover more on these modules further on in this chapter.

### ML Modules (++ files)

An ML module is normally used for such items as transfer protocols and copiers. However, they can be used for any function that you wish. All ML modules must reside in the $C000 to $CA00 range of memory.

### Mini Plus Files

A mini plus file is a module or series of modules which link to a plus file module in much the same way a plus file links to the main module. When using mini modules, the size of the plus file is limited to 40 CBM blocks instead of 56. Also, the mini module may range from one line higher than the main module (the first line must be a REMark) to line 999.

A standard module using mini plus files will look like this:
	
	 1 - 798 Main BASIC module  
	 799 REMark 
	----------
	 800 REMark (first line of mini plus module)  
	 801 - 998 BASIC mini module  
	 999 REMark 
	----------
	 1000 - IM module
