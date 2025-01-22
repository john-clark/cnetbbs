
File date: 10/10/2001  
  Updated:  8/31/2002, 9/9/2004, 10/26/2006  
   Typist: Ryan Sherwood (Pinacolada)

_This is a manual for programming Image BBS v1.2(A) applications on the Commodore 64. It was retyped based on the only surviving printed copy I had. I was missing a few pages; plus, my Okimate 20 chewed up a few lines here and there. I'll do the best I can to extrapolate any missing information and add comments, which will go in_ [square brackets]. _Overall, I'm hoping it should be pretty accurate - all typos should be squashed, and none added._

_I'm not sure where to get the original copy..._

_For now, I can be reached on the Internet at_ [sym_rsherwood@yahoo.com](mailto:sym_rsherwood@yahoo.com)_._

_I admit, I got a little lazy on the last part of the BASIC listing. It appears the original writers did too. Any additional fact-finding would have to be done on the original distribution files, as my BBS as it stands now is heavily modified._

# Index

> [Preface](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-index.html#preface)
> 
> Chapter I: [General Information](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap1.html#generalinfo)
> 
> > [The Function Keys](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap1.html#fkeys)
> > 
> > [The Drive Designators](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap1.html#drives)
> > 
> > [Time and Date Format](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap1.html#timedate)
> > 
> > [Carrier Loss](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap1.html#carrierloss)
> > 
> > [Access Levels](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap1.html#accesslevels)
> > 
> > [Plus Files (+.*)](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap1.html#plusfiles)
> > 
> > [ML Modules (++ *)](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap1.html#plusplusfiles)
> > 
> > [Mini Plus Files](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap1.html#miniplusfiles)
> 
> Chapter II: [BASIC Subroutines](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap2.html#basicsubs)
> 
> Chapter III: Machine Language Subroutines
> 
> > [Jump Table (& commands)](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap3-2.html)
> > 
> > [Memory Map](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap3-2.html#memlocs)
> > 
> > [Using Modules](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap3-3.html#usingmodules)
> > 
> > [Using ML Modules](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap3-3.html#usingmlmodules)
> > 
> > [RS232 Routines](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap3-3.html#rs232)
> > 
> > [Swapper](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap3-3.html#theswapper)
> > 
> > [The Light Bar](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap3-3.html#thelightbar)
> > 
> > [The System Editor](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap3-3.html#theeditor)
> 
> Chapter IV: [Disk File Formats](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap4.html)
> 
> > [The User File](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap4.html#uconfig)
> > 
> > [The System Data File](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap4.html#edata)
> > 
> > [Statistics](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap4.html#barstats)
> > 
> > [Boot Files](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap4.html#bd_data)
> > 
> > [U/D Directories](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap4.html#ud_dirs)
> > 
> > [Sub-Board Directories](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap4.html#sub_boards)
> > 
> > [Sub-Board/Library Data](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap4.html#e_sub)
> > 
> > [E-Mail](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap4.html#email)
> 
> Chapter V: [Variable Usage](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap5.html)
> 
> > [Temporary Storage Variables](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap5.html#temporarystorage)
> > 
> > [Reserved String Variables](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap5.html#reservedstrings)
> > 
> > [Reserved Integer Variables](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap5.html#integervariables)
> > 
> > [Reserved Floating Point Variables](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap5.html#floatingpoint)
> > 
> > [Arrays](http://cbbsoutpost.servebbs.com/dragonseye/projects/imageprg-chap5.html#arrays)

# Preface

This manual assumes the [user has a good working knowledge of] the BASIC programming language. If you find that you have trouble with areas on BASIC, it is recommended that you refer to a good programming book, such as the Commodore 64 Programmer's Reference Guide, published by Howard W. Sams & Company.

The main purpose of this manual is to familiarize the reader with areas of Image that may be accessed in order for the reader to write modifications or modules to enhance their systems.

The scope of this book is intended to include: BASIC subroutines, reserved system variables, important areas of memory in use, disk file handling, execution and use of "mini plus-files" and data formats of various disk files.

This manual was made with every intent to provide a readable, accurate, and exciting way to program Image like never before. Enjoy the manual.

New Image Software

Welcome to the world of programming IMAGE BBS! This manual is designed to allow both the novice and advanced programmer the ability to program IMAGE BBS modules. We will cover five major areas of IMAGE BBS: general information, the BASIC program, machine language routines, disk file formats, and variable usage charts. Also included you will find a special question and answer section of the most often asked questions and the answers to those questions. [Note: I never saw that section.]

IMAGE BBS will support virtually all hardware available for the C64, including the Lt. Kernal (c) hard drives and the CMD HD series hard drives. Also, the SwiftLink (c) RS-232 cartridge by Dr. Evil. [Note: SwiftLinks have been replaced by Turbo232 cartridges, sold by Maurice Randall of [Click Here Software](http://www.ia4u.net/%7Emaurice/). His order site is located at [http://www.cmdrkey.com](http://www.cmdrkey.com).]

IMAGE BBS is a modular type program consisting of both BASIC and machine language modules. A main BASIC module ("im") and a main machine language module ("ml 1.2") both reside in main memory at all times. Also used are BASIC modules (+.*) and machine language (++*) modules.

The purpose of this manual is to provide you with necessary subroutines and variable considerations to make your own modules or modify the existing system to suit your needs.

I would like to thank all of those who worked hard in taking NEW IMAGE SOFTWARE to where it stands today.

DON GLADDEN (C Tuna) for the original BASIC program.

RAY KELM (The Professor) the ML whiz-kid, for the ML.

FRED DART (The Chief) for hours upon hours of work and always being available for support. [R.I.P.]

JOHN MOORE (Little John) for continuous sleepless nights spent to better the software and its subsystems. Also for the much awaited 128 version.

BOB LEARY (Dr. Bob) for countless hours of work wracking my brains trying to get this manual done.

NISSA for providing undue support to all those sysops in their time of need.
