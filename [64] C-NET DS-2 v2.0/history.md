C-Net 64 DS2 BBS
Electronic Bulletin Board System


History

C-Net has been around about as long as the Commodore 64 computer.  Ken Pletzer
of Perspective Software was the original developer of all three platforms of
C-Net BBS program from the 64 to the Amiga versions.  Ken wrote the first 10
versions of C-Net 64 BBS, then went on to the Commodore 128, where he stuck it
out for about 4 versions of C-Net 128 BBS.  Ken also developed the C-Net Amiga
BBS program versions 1-4.  

After version 10 of C-Net 64 BBS, a few other programmers came into the picture. 
Jim Selleck, Ray Kelm and Don Gladden helped develop versions 11 and 12 which
kept Ken's basic concepts, but further developed the compatibility and
efficiency of the program.  Ray Kelm and Don Gladden who helped develop version
12, later used this version of C-Net to develop Image BBS while Jim Selleck went
off to develop the DS2 versions of C-Net, using ideas from all the previous
releases, as well as a few new techniques he found or developed on his own.

C-Net 64 DS2 v2.0 was the first DS2 named version of C-Net, while v1.0 was
actually named C-Net 64 v11.6a.  The DS2 stands for Developers System 2.  Jim
named it this because the BBS was written with the BBS developer in mind.  With
almost all text output in BASIC, making it easily modified and modular programs
that overlay or append to the current running program, adding additional
features or loading in a completely different area of the BBS.

Jim Selleck's last release was C-Net 64 DS2 v2.5.  This release added CMD HD and
RAMLink support to C-Net, taking advantage of the partition and sub directory
layout of these devices.  Jim began development of version 3.0, but had to
shelve the project due to personal commitments.  A Canadian programmer, named
Rob Muscedere, has taken over the project and has interesting additions to the
C-Net program that Jim had envisioned.  Features like auto-reformatting text
output that formats the text output to that of the user, (40 or 80 columns)
Swiftlink support for high speed modem access, ANSI color and graphics support
and a new modular overlay system, unique to C-Net 64 DS2 v3.0.

Features

C-Net 64 DS2 BBS has many features that make it one of the best bulletin board
systems available for the Commodore 64.  Each area of the BBS is a separate
BASIC program that can be edited by the system operator, just like editing any
other BASIC program.  This part of the text will cover each area and some of the
features.  I'll be using the current release of C-Net 64 DS2 v2.5 as the model
for each of these areas.

	Logging On

	*	65,000 user base limit
	*	Fast handle search routine
	*	Entry and welcome screens system operator definable
	*	News and email alert or display
	*	Auto graphics mode detect (ASCII, ANSI, C/G Modes)

	Main Level 

	*	Access all other areas of the BBS from this point.
	*	Change Password or terminal parameters
	*	View user or system stats
	*	Enter System, P-File or G-File, News or Voting maintenance areas
 	*	Set access levels and system flags for users still online

	Bulletin Board or Message Base

	*	160 subboards divided into 8 libraries with 20 subboards per 
		library
	*	50 posts per subboard with unlimited responses to each post
	*	Scan, Read and About commands allow users to read, scan or 
		view the headers of new messages posted to the system since 
		their last call.
	*	Each subboard can be assigned its own drive, partition or 
		subdirectory
	*	Entry screens and subboard operators can be assigned to each 
		subboard.
	*	Freeze posts so no replies can be made to it
	*	Detailed scan to scan posts for specific replies
	*	40 or 80 column line or visual text editor up to 255 lines
	*	MCI and Commodore Graphic commands supported in the editor
	*	Access levels assigned for each library and subboard
	*	Anonymous post and reply option for shy users
	
	Upload/Download Area

	*	160 subboards divided into 8 libraries with 20 subboards per 
		library
	*	Standard UD subboard holds 50 files per subboard stored with 
		1 to 255 line descriptions, handle of user who uploaded the 
		file, time and date uploaded and computer type for each file
	*	Exchange UD subboards hold unlimited files with no description 
		or other file info
	*	Scan and About commands setup to view new file titles or 
		headers in current or all subboards per library
	*	Each subboard can be assigned an entry screen and subboard 
		operator
	*	Each subboard can be setup as upload or download only
	*	Each subboard can occupy its own drive, partition or 
		subdirectory
	*	New files uploaded are frozen and tagged unvalidated until 
		verified by system or subboard operator
	*	X-Modem, X-Modem CRC and Punter (single or multi-file) 
		protocols supported
	*	Read or download SEQ files.

	E-Mail Area

	*	Send and  receive private electronic mail to/from any other user
	*	List, read, edit, delete or save any message you receive
	*	Counter for old/new mail
	*	Logon alert for waiting mail 
	
	G-File Area

	*	Displays a list of text or graphics files to view online.
	*	20 entries per menu, unlimited menus
	*	Access level for each entry
	*	Each entry can be either a SEQ file or another menu of 20 
		entries
	*	12 character description for each entry
	*	Credit system can be applied to each entry to charge users a 
		number of credits in order to view the file.
	*	Menu driven directory of entries or files
	*	Edit SEQ files from the listing

	P-File Area

	*	Displays a list of games and programs for execution online
	*	20 entries per menu, unlimited menus
	*	Access level for each entry
	*	Each entry can be either a program or another menu of 20 entries
	*	12 character description for each entry
	*	Credits system can be applied to charge users a number 
		credits in order to access each entry.  Credits are earned by 
		posting or responding in the message base.
	*	Menu driven directory of entries or programs

	News Files

	*	Displays a list of system news files the system operator creates
	*	News files can be made to appear during logon, either forced 
		once or re-occurring
	*	Each file can be access level sensitive, meaning only certain 
		access levels will see the file
	*	System operators can edit, add or delete files from the list
	*	Users can list and view entries for their access level

	User List

	*	List all or a specific type of user
	*	Search according to Handle, Computer type, Area code, 
		Real name or Access group
	*	System operator sees the ID#, Handle, Computer, Phone #, 
		Last call date, Real Name and Access Group.
	*	Users see only ID#, Handle, Computer and Last Call Date

	Voting Booth

	*	Displays a list of topics setup by the system operator or 
		particular access level for users to vote on
	*	Topics selected, displays the topic or question and a list of 
		possible replies for the user to pick from
	*	The number of votes and percentages are displayed for each reply
	*	Mainly used to get feedback from users on possible changes or 
		additions to the BBS or simply to get a consensus from a 
		group of people.

	System Maintenance

	*	Access any drive, partition or subdirectory with DOS commands
	*	Read, write or edit system and other SEQ files
	*	Create forced mail that logs the user off or deletes their 
		account
	*	Execute a program
	*	Format disk protection (New command removed)
	*	Access remotely or locally

	Local Mode Menu

	*	Menu for local system operators only
	*	Normal or Instant logon
	*	Copier program
	*	Error and logs for program execution and upload/downloads
	*	Edit user accounts, add or delete users
	*	Feedback, read, send mail set access
	*	Terminal Mode, terminal program for system operators
	*	User List access
	*	Read system operator mail
	*	System Maintenance access
	*	Send private mail to any user
	*	Edit or add reservations
	*	Execute a program
	*	Restart CPAS
	*	Change C-Net configuration

	Waiting for Call Screen

	*	Current date and time line, time still remaining for users 
		online
	*	Displays last caller and the time and date they logged off
	*	Also shows time and date the CPAS restarted, # of calls and 
		memory free
	*	Idle time display clock
	*	Light Bar options control system funtions and set flags
		- System Operator available for chat
		- Access level control
		- Local Mode on/off
		- Time remaining control
		- Chat on/off
		- New users acceptance control
		- Printer on/off
		- Upload/download on/off
		- System operator defined controls (U1-U4)
		- System Operator Next control to alert system operator when 
		  user logs off
	*	Status display, waiting for call, clearing line, connected, 
		etc..
	*	CPAS - Current Period Activity Stats
		- System operator # of feedback messages
		- System operator # of email messages
		- Number of posts made to the system
		- Number of responses 
		- Number of uploads
		- Number of downloads
		- Number of email sent
		- Number of New Users
		- Number of Errors
	*	Status bar displays # of calls since setup, # of logs and # 
		of users
	*	In and Out windows show actual input and output to/from modem
	
Well, thats prettty much a list of most of the areas and the features of each
one.  With the structure of C-Net, most system operators find it so easy to
modify or create their own programs, that there has been hundreds of mods,
online games and other programs written by the system operators themselves.  The
6 online multi-player games that come with the C-Net 64 DS2 BBS package is a
result of one such system operator.  Paul Van Doleweerd has allowed us to
compile six of his programs and make them available with the program package. 
Paul also offers his own p-file disk of the latest release of his games and mods
for C-Net, free of charge.  You only have to be a registered system operator and
send him a letter with your name and return address to receive the disk.

Online Games

Adventure - A cool multi-player game where the user can create thier own
character name, pick a race, class and set of attributes in order to begin the
adventure that awaits your hero.  Users can build up their strength, money and
weapons by exploring the 6 deadly levels and killing creatures, or by battling
other users on the same quest as you.  Nicely thought out game.

Conquest - A new twist on the famous Empire online games seen on many other
BBS's.  User must buy and sell wheat, build armies, colonies, castles and other
good stuff.  Has many new options, addition of wizards and other tactics, make
this one a pretty involved game.  Really cool if several users play this one.

Empire v4.1 - The classic Empire game we played for years.  This is an oldy but
goody, especially when four or five users realy get going.

Mountain - A trivia king of the mountain style game where the users answer
trivia questions to build mana and power.  A little different, but a pretty cool
game to play if you like trivia style games.

Murder Motel - This one is kinda funny.  Your a murderer going into this hotel
loaded with weapons and other murderers.  Your goal is to find two objects that
fit together to make a weapon and try to kill everyone else in the hotel. 
Sounds easy?  Well, just remember they are doing the same thing, you have to
find the other people in the hotel and some found remedies or protection against
certain weapons.  Really neat game, users love it. 

Star Warrior - A trade wars style game, but not quite so invloved.  You travel
between planets, avoiding black holes and other obsticles as you land on
different planets to buy and sell goods, upgrade your ship with weapons, sheilds
and engines.  Battle with other users, confront the galatic police, etc.. 
Another pretty cool game for the users.

There are also tons of single player games available on the C-Net support BBS
(Cygnus X-1) as well as other C-Net BBS's.  All ya have to do is ask.

DS2 Network

Although not an internal part of C-Net 64 DS2 BBS, this program comes with the
latest release as an add on package to the BBS.  This was done for two reasons. 
First, DS2 Network was developed by someone else as a shareware program that was
meant for release with v3.0.  When Jim sheleved v3.0, Gary O'Brien released it
as shareware for all C-Net 64 DS2 BBS owners.  The second reason was because we
wanted the system operator to decide whether or not they want to run the
Network.  If not, there was no need to install it and waste the memory.

As well as having the ability to connect with other C-Net 64 DS2 BBS's and share
like message bases, email and other areas of the BBS, DS2 Network is now
compatible with CommNet.  CommNet is a joint effort between Image, C-Net 128 and
C-Net 64 DS2 to connect with each other, creating a much larger network with
three times the Commodore support.

Here's a few features of DS2 Network:

NetMail 		- Send email to any user on any BBS in the Network.  

NetSubs 		- Select 0 to 20 subboards to become Networked Subs

NetWall		- Graphiti Wall shared between Image and C-Net 64 DS2

NetClassifieds	- Lists articles to trade or sell in specific categories or
email someone who's selling or trading.

NetMatchmaker	- Fill out an application or search for others with your
interests to send email to.

NetNodes		- List of BBS's in the Network.  List with any
attribute, name, home node, phone number,etc..

NetCharges		- Not actually used, but keeps a running total of money
owed for sending netmail for each user

NetActivity		- Keeps a monthly total and percentage of all Network
traffic on your BBS.

NetLogs		- Keeps track of activity in the network, incoming and outgoing 				  
calls to your home node on a monthly basis.  Outgoing call logs keep running 
total of time online.

NetAuto-Maint	- Automatically weeds old messages in the message base, 				  
Netwall and NetClassifieds according to the number of days you 	set it for
	
DS2 Network is written to run automatically after the system operator configures
all the options.  It can be configured to call out on specific days of the week
or manually when the system operator can be there to watch it.  The system
updates the node list, networked subboard list and configured options
automatically to every system in the network.  Only one call is made to both
send and receive information.  The BBS that joins the network calls their Home
Node and sends a packet, then receives a packet.  The system then disconnects
and sorts the material.

Any BBS can be both a remote and a home node to other BBS's.  Each BBS can
configure their system to be as large or small as they like.  You can run a
NetMail only system, which means the only network traffic you'll get is NetMail
and updates, or you can run any combination of subboards, wall, classifieds,
matchmaker etc.  This control allows the system operator to control the size of
the packets they receive as well as the amount they spend each month on long
distance costs for the network, if any.  If your Home Node is local, of course
there are no LD costs.

The network program that comes with C-Net 64 DS2 BBS is in its unregistered
form.  The main difference between the unregistered and registered version is
that the registered version has the ability to send program updates, has a Net
Maps option and color menus.  Registration is $15.00 and comes with the
registered version of the program and a programmer reference guide for the
network.

Order and Support Information 

C-Net 64 DS2 BBS v2.5+ now comes with the BBS program, 6 Multi-Player online
games, Unregistered version of DS2 Network and an add on ANSI mod.  Also, the
owners manual and Programmers Reference Guide (a $19.95 value, now included
free).  Users running a previous version of C-Net 64 BBS can upgrade to C-Net 64
DS2 BBS v2.5+ for half price.

C-Net 64 DS2 BBS
v2.5+..............................................................	$59.95

Upgrades from previous versions......................................	$29.95

DS2 Network v3.04
(registration)..................................................	$15.00

Prices do not include shipping and handling.  The BBS is sent via registered
mail to ensure receipt of the program.  Within the US, this shipping fee is
$3.00.  Please make checks or money orders payable to the following:

C-Net 64 DS2 Software 
92 Lee Ave Suite N3
Newark, Ohio 43055

Technical Support and Ordering:	(614)/788-8568
Online BBS Support:			(614)/522-6563

Email:	

	DS2 Network/CommNet	Mitron @ Cygnus X-1
	Internet				mbendure@infinet.com
	WWW				http://www.infinet.com/~mbendure/cnet
