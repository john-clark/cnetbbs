| Feature Name | Purpose/Description 
| -- | -- 
| Connectivity: TermLink | Allows incoming calls on one BBS port to access and utilize another port’s modem to call out to other locations. Access to this feature may be configured by the SYSOP for each user/access group, and it may be configured so that only local outbound calls can be made to avoid potential abuses and/or “terrifying” long distance bills.
| Connectivity: JoinLink | Allows a seamless interconnection between multiple CNet/_PRO_ systems for such things as MultiUser Chats which can span the planet via internet-hosted JoinLinks!
| BugReport | A command to allow sysops (and users if the sysop chooses) to file bug reports with ZenMetal Software.
| Connectivity: FTN-FTP | you can now get your FIDONET (FTN) mail across internet FTP!
| Update Check\* | A command for Internet-connected CNet’s to automatically check and download updates. We are working on scripting to allow updates to be automatically installed.

 _\*This feature was originally written by Kelly Cochran, and as he refused to allow the source and/or executables to be included with CNet/PRO, this feature has needed to be removed for the time being._
 
_In the future, all programming integrated into CNet will either be done IN HOUSE, or officially released by the third-party author to avoid this sort of thing from happening in the future. We apologize for the loss of the above feature, and we hope to write a replacement for it in the future. For the time being, updates will be posted on the official web site(s) as they are created/released._

| | |
| -- | -- 
| ARexx Support | Native AREXX scripting for easy door and ARexx script creation. Native ARexx support allows access to all CNet/_PRO_ functions and as a result, allows automation of nearly every facet of BBS operation!
| “CNet/C” Door Support | A powerful CNet/_PRO_\-Specific programming interface for easy C door programming. CNet/C doors are far more likely to survive the upgrade process, as they would adhere to the CNet/_PRO_ SDK’s programming standards.  |
| AmigaDOS Door Support  | CNet/_PRO_ Supports AmigaDOS doors that use standard I/O. Many utilities that can be executed in a standard AmigaDOS Shell window can also be run from within CNet/_PRO_!  |
| Security: Access Flags | 32 access levels for common user configurations. If required, every user account may be customized regardless of the user access level on an individual basis by way of additional account-specific access flags.  |
| Connectivity: Maximum BBS Ports  | Up to 100 user-accessible ports (Dial-up and Telnet access included).  |
| Connectivity: Telnet Support | Telnet client and service daemon, so that users may telnet to and from internet sites and LAN terminals. |
| Connectivity: NNTP Protocol Support  | Direct support of NNTP (Usenet) newsgroup importing into CNet message conferences. |
| Connectivity: User-Configurable EMail | The ability to distribute mails in user-defined folders. Each user may create as many folders as they like, with a sysop-defined limit of the total mail size and number of mails. For ease of use, users may choose to only have a single mail slot/folder (“InBox”) to reduce confusion, or many mail slots/folders to aid in classifying long-term email storage.
| Connectivity: EMail “Trashcan” support | When a user deletes a message, it is moved to his personal trashcan folder, where it will remain until he empties his/her trashcan. If the user deletes a message by accident they may simply go to their trashcan folder, then move the accidentally killed mail back to their INBOX, or to any other personal folder they prefer.
| Security: Intercept Mail Processing (IMP) | IMP allows incoming mail to be “trapped” according to SYSOP-configurable criteria, and processed in a number of ways. Current processing includes importing to: “mailing list subboards,” processed via ARexx or AmigaDOS script or forwarded support of “carbon copy” mail and forwarding of mail to an internet address.
| Inter-User Chat (IUC)  | IUC allows user-to-user chat in “line mode” or full-screen mode. The “Join” command allows multi-user conference chat, and the “JoinLink” feature allows those multi-user chat areas to span across multiple linked CNet/_PRO_ systems…either connected via modem or across the planet via telnet connections over the internet!
| Security: Logging | Logging of most commands for easy system administration.
| Security: Port Capturing | This feature adds the capability to “capture” an exact copy of everything a user does while on your system. It can be enabled or disabled for each user either manually or automatically. No more worries about what “troublesome users” may have been up to while you weren’t around to keep them in check!
| Connectivity: CNetIRC | A native IRC client (based on the popular IRC-II) so that users may join Internet Relay Chat servers and channels, including our own irc.cnetbbs.net\* server where they may join the channel #cnet. CNet Amiga’s IRC client also support DCC send and receive.


 _\*Please note: As of this writing, CNet/PRO no longer has an IRC server accessible at the above noted address. When/if this changes, it will be updated here._

| | |
| -- | --  
| Connectivity: CNetFTP | A native internet FTP (File Transfer Protocol) client to allow your users access to files available on the internet or any host accessible via the FTP protocol. |
| Organization:  | Up to 65535 file/message/door areas. |
| Connectivity:  | NULL modem support for serial LAN access.  |
| Connectivity: CNetSMTPd  | CNetSMTPd is a native SMTP service daemon that sits on the TCP/SMTP port and accepts incoming mail sent to your system or it’s users, as opposed to POP3 which must connect to a remote pop3 server to retrieve internet mail.

 _NOTE: A POP3 inetd daemon is available for CNet from a 3rd party CNet door developer._

[http://www.aminet.net/package.php?package=comm/tcp/hotwayd-0.5.3.lha](http://www.aminet.net/package.php?package=comm/tcp/hotwayd-0.5.3.lha) _and available at_ http://hotwayd.sourceforge.net/

_The following options are also available:_

[http://www.aminet.net/package.php?package=comm/mail/Relay.lha](http://www.aminet.net/package.php?package=comm/mail/Relay.lha)<br>[http://www.aminet.net/package.php?package=comm/tcp/AmiTCP-popd.lha](http://www.aminet.net/package.php?package=comm/tcp/AmiTCP-popd.lha) <br>[http://www.aminet.net/package.php?package=comm/tcp/maildaemons.lha](http://www.aminet.net/package.php?package=comm/tcp/maildaemons.lha) 

| | |
| -- | -- 
| System:  | Account caching for FAST account lookup. |
| \*Classify\* | Users have a personal FILES directory which is used to hold their decoded mail attachments and file that they have received from FTP sites.  |
| CNet Commander\* | CNet Commander is a directory utility used for “direct” file access and for users’ personal FILES directory maintenance. |
| Security: Suspending User Access | Easy individual account suspension, should you need to temporarily (or permanently) suspend a particularly troublesome user from logging in. |
| MailTask | MailTask is an EMail server which operates in the background. This means that a user does not have to wait for outgoing mail to be sent. A MailTask GUI is present for the sysop to monitor the number of netmail, local mail and bounced mails sent/received, among other statistical data. |
| FileTask | Background file testing tests uploaded files and notifies users of corrupt archives. Background testing is done as parallel background tasks and the number of parallel/simultaneous tests to allow is SYSOP configurable. |
| Organization: Archive Testing and Transformation | CNet supports automated archive processing which includes default “XScripts” for the testing and transformation\* of all archives received by the system. Archive Testing and/or Transformation may also be started at any time on individual files, if the user has appropriate access permissions.

**Archive Transformation:**

The ability for the SYSOP to automatically convert archives from any pre-defined archive format to any other archive format of the SYSOP’s choosing.<br>Each subboard’s default archive format is SYSOP configurable.<br>An example of this would be in the support of multiple computer platforms within your Files bases, such as: 

 Amiga archives would default to the .LzX or .LhA archive formats for highest reliability and compatibility among Amiga users.<br>PC-Based archives would default to .ZIP files.  

File transformation can be configured (via XScripts) to use system RAM for the fastest processing speeds, or can be processed in a dedicated directory on the hard drive for added protection against loss of data, or simply to keep that 700Meg archive from overrunning your 32 Meg of available memory. 😉 

 Custom XScripts can be created by the SYSOP for ANY AmigaDOS-based Archiver to transform ANY “Initial” archive type to ANY “Preferred” archive format, and to allow for virus-checking, addition of fileid.diz file descriptions or BBS ad text files, and MORE!

---

ORIGINAL DESCRIPTION: Background file transformation, in which uploaded files are converted to the System Operator’s preference, separately configurable for each file conference/area. One file area may be selected to convert files to LHA format while another may be converted to ZIP or ARJ format for support of files formats of different/alternative platforms. Simultaneous transforming is implemented and the sysop has the ability to limit the number of simultaneous background transforms to allow.

| | |
| -- | -- 
| Organization: Drives and Partitioning | CNet/_PRO_ does not limit you to keeping your files on a single partition. File areas support both multiple hard drives and multiple drive partitions to suit your particular storage requirements. Individually configurable, each subboard can be set to use a single drive or partition to centralize related files, or spanned across multiple devices or partitions to allow greater total storage capacity.<br> CNet/_PRO_ will automatically store files on the drive or partition with the most available free space, eliminating worries about errors due to running out of available HD space on a single device, while enhancing the total available storage space without users ever needing to consider which drive they need to send their uploads to!
| Local and Remote File Viewing | Configurable local and remote “viewers” for examining the contents of individual text files, listing archive contents, or viewing text files directly from within archives.
| Inter-User: OnLine Messaging (OLM) | OLM capability allows connected users to send a 1-4 line message to a user logged into your system on other ports. “Broadcast” OLMs are also possible in which users may write single OLMs that are sent to all ports<br>OLM’s are particularly useful to SYSOPs in informing users of system maintenance events which may temporarily affect the system’s performance, or require users to log off an individual BBSPort to be performed.<br>Broadcast OLM’s could be used to notify ALL connected users of an impending maintenance or software upgrade-required reboot, for example.
| CRONTask | A “Cron” editor to schedule time variable events.<br>e.g.: Set JoinLink to connect to another system at midnight every Friday night, run auto-maintenance nightly 3:00AM, while another task may be executed at 10 PM. |
| \*Classify\* | Appicon, AppMenu and Commodities Exchange support. Both mail-task and the CNet Control window may be Iconified, menufied or hidden so that changing workbench preferences does not result in a message stating, “please close all windows, workbench is resetting.” This also reduces Workbench clutter. Appicons may be positioned and saved at precise locations on your Workbench.  |
| Automatic EMail Notification | Mailscan at login, which notifies users if they have new mail as soon as they login.<br>Feedback/NewUser scan at logon which notifies maint users if there is new user mail or feedback pending is included as a logical extension to this feature. |
| Yank-Task  | Yank-Task is a background process to facilitate QWK and text-based offline reading. BlueWave format is planned and will be implemented in the CNet 5.x series. |
| “GO” Commands  | Users may jump directly to a favorite conference/area/subboard by using CNet/_PRO_‘s SYSOP-configurable GO command.<br>e.g. ‘GO files’ or ‘GO uploads’ to get to the upload or file-transfer areas. |
| ARexx Support  | Native ARexx support is included for many system functions, allowing the creation of games, utilities or automation of system processes…or for any other uses you can dream up!  |
| Guest Accounts | Guest user support is built in for users who just want to quickly “browse” the publicly available system areas before joining as an official member and creating a permanent account of their own. |
| FILE_ID.DIZ support  | This feature extracts pre-existing file descriptions from uploaded archives and by default, uses this information to create a “short description” which may be viewed by users as they scan through the files bases. |
| Orphan Files Adoption  | SYSOPs can add many files to the system at once by simply placing the files to be added into a given location and issuing the “Adopt Orphans” command. |

| | 
| -- 
| **Additional Features** |
| Easy configuration of user/system limits, file/byte credit ratios, defaults and users via both online editors and offline GUI-based editors. |
| Support for long device names such as “squirrelserial.device”. |
| Mail-sorting by name, subject and date. Descending or Ascending order. 
