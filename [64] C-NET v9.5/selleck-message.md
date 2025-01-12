Sorry I missed you when you were compiling history for the documentary.  Congratulations on a great job.  Wish you had looked me up for a bit of
background on C-Net BBS for Commordore 64.  I still have a few artifacts from developing it including a dongle from version 10 and at least one
copy of the ML source code backup I kept around in case I needed to defend the copyright.

Around 1986 when I was getting ready to release C-Net v11.6 I asked the infamous Pit Bull from Ferndale, Michigan to beta test (Pit Bull is
greatly missed by everyone who knew him.  Regretfully, he commited suicide in the early 1990's.).  The hacker group that used to meet at his house
every Wednesday night was kidding with me, taking bets how fast they would be able to crack the program.  The smart money was on "two weeks".
Those guys really had me going!

The result was a bizarre obsession over the next month that had me writing and rewriting more and more convoluted ML code to try to hide and
encrypt the dongle checking routine in such a way that nobody would EVER find it.  Then I purposely corrupted and encrypted the ML files on the
installation disks and created a program that would fix certain critical errors on a Just In Time basis as the program ran.  That last was to
prevent system images from being taken by hardware cartridge "snapshot" utilities.

During that time I could easily have been commited.  I was living alone in a big house in Detroit with room darkening blinds on all of the
windows.  I was writing C-64 ML on an Amiga, using an emulator for rough testing, then sending the compiled ML to an actual C-64 for final
testing.  I did all of the programming and testing stark naked, a fact I have never mentioned to anyone up until now.  Near the end, the
anti-piracy crap became so cumbersome that if I made a modification that changed the size of the ML file by even one byte, I would have to rewrite
all of the encrypted modules and the JIT decorruptors... it was INSANE!  Without knowing it I created a military grade self-protection system,
just because a bunch of hackers were yanking my chain.

In the end, it took two years to crack C-Net 11.6 for Commodore 64, and by that time most of us had moved on to Amiga versions in order to use
multi-line cards and 28.8 speed modems.  The ironic thing is that the software protection was NEVER cracked.  Eventually somebody figured out that
the stupid dongle was actually nothing more than a sealed resin unit containing one resistor and one capacitor to make a tank circuit.  About 20
cents at Radio Shack is all it cost to make your own.

The secret key to the kingdom:  The mysterious installer ML module was just a BASIC program that had been compiled using PETSPEED.  I removed the
PETSPEED header and added an unconventional entry point.  There was some spoofing and blind alleys in that code, but as far as I know, nobody ever
tried using a PETSPEED decompiler on it.  There may still be some hackers in mental institutions who assumed that chunk was actually native ML and
tried to reverse engineer it.

Good times!

Jim Selleck
