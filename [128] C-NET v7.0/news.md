Monday, November 16, 1998

Patch Releases 1G and 1H are now available for download.

---

Sunday, November 8, 1998

Patch Releases 1E and 1F are now available for download.

---

Saturday, October 24, 1998

Patch Release 1D is now available for download.

---

Wednesday, October 21, 1998

Patch Release 1B and 1C are now available for download.

---

Thursday, October 15, 1998

Patch Release 1A is now available for download.

---

Wednesday, October 14, 1998

Patch Release 1 is now available for download. There are a number of important fixes in PR1 so I recommend your apply it to your v7 system as soon as possible. Read the "RUNME" program for descriptions of the changes to each program.

---

Friday, October 9, 1998

Didn't think I'd be updating this so soon. It is has been brought to my attention that the WRAPTOR.SDA program that was made available on the C-NET 128 v7.0 download page and intended to be used by you to "unwrap" the C-NET 128 compressed files IS NOT compatible with Wraptor V3. I have therefore replaced the file with a copy of Wraptor V3. Thanks to Tom for the good-eye.

According to the Wraptor V3 documentation it is OK to distribute this file to a "friend" that needs to unwrap of file you have wrapped with Wraptor V3 as long as you tell them that Wraptor is available from Loadstar (see the Commodore Related Links page for their web address) where you can also find many other great programs for the Commodore 64 & 128. So I'm telling you.

---

Tuesday, October 6, 1998

Well it's a little after midnight now and v7 is almost packed up and ready to go. All of the v7 files will be available for download by this morning! Remember to read all of the documentation. C-NET 128 v7 is very different then v6 especially if you plan to network with other BBS' successfully. There are 3 new network files that will have to be in place on a v6 BBS in order for a v7 BBS to network with it. The files NET-TRANS6.9S, NET-MAIL and NET-UNPACK replace the current network programs; PRG.NET-TRANS, PRG.NET-MAIL and PRG.NET-UNPACK.

Other sections you should definitely read are the sections on Backgroun Information (2.0), Software Installation (4.0), and Electronic Mail (10.0).

I'm sure there are things I've missed in v7 and to that end I am already planning a patch release for later this year. I look forward to your questions and comments.

---

Saturday, August 22, 1998

It's been a while since my last update. Unfortunately obligations at work have kept me away from my hobby. The good is news is I've found some time recently to fix a lingering bug in v7 where the messages bases were being corrupted. With this bug squashed I should be able to move full-steam ahead! By the way, the Year 2000 fix and the new SysOp Interface has been completed in this version.

I am removing the mirror-site on AOL. It's tuff enough keeping this site up-to-date.

If you have any questions regarding the status of C-Net 128 please e-mail me.

---

Thursday, March 12th, 1998

The first C-Net v7.0A Alpha Test diskettes are shipping out this week, read more about this in the C-Net 128 v7.0A Alpha Test Area. A new version of PRG.NET-TRANS has veen released for C-Net 128 v6.6S BBSs, check it out in the Download Support area.

Now that V7 is on its way the next major modification will be to make C-Net 128 Year 2K compliant. This again looks to be a major modification involving a number of Basic 7.0 and Machine Language program changes. I don't expect it to be done before the end of 1998. (Nothing like waiting to the last minute.)

Some good news also is that K. Lee Loftiss a very good C-Net 128 programmer has resurfaced. You will see Lee's name in many REM statements throughout the C-Net Basic code especially in the Networking programs. Lee was working on V7 when C-Net belonged to RMS Software but had to place the project on hold because of other obligations. I have been in communication with Lee and he is sending the source code for the work he did on his V7 of C-Net. Some pretty nifty stuff that I might try to throw in with the Year 2K fix for a new version of C-Net 128, maybe V7.5 or possible even V8 (doesn't that sound cool, like "C-Net 128 V8 - Gotta Have it"). Anyway, I'll see what can be done. Till next time.

---

February 3rd, 1998

Thought I'd provide a little "troubleshooting help" for anyone having difficulties installing and launching C-Net 128 V6.6S for the first time. I just want to take you through some basic steps and point out a few things. First of all, V6.6S DOES NOT come preconfigured. This means you must select option number 2 "System Configuration" from the menu after you boot the INTRO file. You cannot immediately launch the system because none of the relative User Data files have been created yet. Now some of you might be saying "Well I tried System Configuration but I keep getting the message 'Error: string too long in line 502' and then it falls into a loop." Well, the reason System Configuration is giving that error message is because it's finding a SYS.DEF file which was included (accidentally) with the file CNET128SYS1.SDA. Here's what you need to do to get arround that problem.

1. Delete the file SYS.DEF
2. Boot the INTRO file and select option #2 "System Configuration"
3. C-Net will not find the SYS.DEF file and you’ll get a message ‘System not configured’. Hitting RETURN at this point will bring you to the Configuration menu.
4. Assuming your disks are formatted already you can skip option 1.
5. Select option 2 ‘System parameters’. You’ll notice the Device number for ‘the SYSTEM disk’ is set at 0. Since C-Net normally boots from device 8, edit this value changing it to an 8. You can edit any other parameters at this time as needed. SAVE YOUR CHANGES.
6. You can now select option 3 ‘Create user data files’. Create at least 10 user accounts to start with.
7. You can now quit ‘System Configuration’ and reboot C-Net 128.

---

December 30th, 1997

Greetings and a Merry Christmas and Happy New Year to all! Well, all the shareware files for C-Net 128 V6.6S have been uploaded and all the links are finally working. Thanks to everyone who tested the downloading.

I've added two new options off the main menu, "C-Net 128 V7.0A Alpha Test" and the "Download Support Area", which will be online soon. The "Alpha Test" area will have the new programs required for C-Net version 7 and will be a use at your own risk for those brave souls willing to help in the testing of version 7. What will be different about version 7 you might be wondering. Version 7 will have two very important enhancements; first we're going to break the 2400 BPS barrier and second a Year 2000 date fix. These enhancements are not minor and will require many changes to the existing programs, so please be patient. The second new option is an area where you can download the latest enhancements to the V6.6S files. We have a number of good programmers working on C-Net in their spare time cleaning up code, fixing bugs and making enhancements. These programs will be available for download after they have been "C-Net Approved".

1998 should be a banner year for C-Net 128, so stay tuned.

---

November 22nd, 1997

I received my replacement C-128 today so we're back in business! I've uploaded the CNET128ML.SDA file to the downloads area as a test to see if the files can be downloaded intact. The process for getting these files up here is first to create the .SDA file using the C-128, then transfer the file from the Commodore to the PC using "Big Blue Reader" and then uploaded to the Web. I now want to test the process in reverse (Download, Trasnfer from PC to Commodore and then decompress) to test the integrity. If all goes well the rest of the files required for C-Net 128 V6.6S should follow shortly.

---

November 10th, 1997

We now have all the latest C-Net 128 files that will be included in the V6.6S Sharware release. Many thanks to Ron Fick, SysOp of The Batcave BBS for his work. I've started to compress the files into self-extracting archives that will be available for download from this Web site as well from participating C-Net SysOps. Unfortunately due to a bad power port the work has come to a screeching halt. I expect to have a replacement computer here by the end of this week or by the latest early next week. So the V6.6S files should be available for download by November 21st at the latest. Sorry for the delay but it was unavoidable.

---

October 2nd, 1997

All rights to C-Net 128 were transferred from RMS Software to me as of Oct. 1, 1997.

As of Oct. 2, 1997 I have released C-Net 128 V6.6 as Shareware. If you have never heard of Shareware or uncertain of the conditions regarding Shareware then please click on this Shareware Link.
