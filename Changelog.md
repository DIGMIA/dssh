29. 6. 2015
===========

Moved to [Github](https://github.com/DIGMIA/dssh). Only latest version is in Github, if you need older versions, you can find them [here](http://flz.sk.cx/dssh/).


DSSH 1.1k released 1.2.2010
============================

 - Switched from Groovy to BeanShell. This usually requires rewriting
   of dssh.groovy, but very simple tweaks are needed.  This caused
   memory footprint to drop significantly and load time is twice as
   fast.
   
 - Added Solaris platform support
   
DSSH 1.1i released 27.11.2008
============================

 - Parameter -v is more verbose than before: It prints what authentication
   method did succeed.  Does not try to authenticate using su or ena,
   if agent has no password for that particular user. When using -v,
   it explains what's wrong.
   
DSSH 1.1h released 20.11.2008
============================

 - Added Linux amd64 support, thanks to Michal 'anti' Klempa.

DSSH 1.1g released 4.8.2008
============================

 - Added scp mode by popular request (just add -s and it should work
as normal scp command). Recursive mode is not yet supported, neither
are "su" sessions (when using InteractiveSuSession, dssh acts like
normal interactive session, i.e. it does not log in as root, when
PermitRootLogin no is on server and you script it via
InteractiveSuSession). Direct copying from or to root account are
supported when PermitRootLogin is yes, so in this way, it is not
less powerful than scp itself.

 - Ported DSSH to latest Trilead SSH library (which is a successor of
Ganymed SSH). It is the same codebase, just package names changed
and few feature were added. It also contains a much faster SHA1
algorithm. I also decided to include patch against stock Trilead
SSH, althrough it's not a license requirement, it is a good idea
if you would ever wanted to port DSSH to later version of Trilead
SSH library yourself.

DSSH 1.1f released 29.7.2008
============================

 - Added batch mode by popular request (-B)

DSSH 1.1e released 11.6.2008
============================

 - Added warning if older Java is found during installation, showing
user where to set path to Java 1.6

 - Added Mac OS X 10 Java 6 support (official version), added JRE
autodetection for OS X

DSSH 1.1d released 14.5.2008
============================

 - Fixed RSA key authentication (we've been using DSA all this time,
so no one noticed it).  Several minor platform support fixes.

DSSH 1.1b released 17.12.2007
=============================

 - Minor bugfix (use orighost for fetching of passwords, in case you
are behind nat and need password authentication). Should not affect
99% of users.

DSSH 1.1a released 4.12.2007
============================

 - Added support for FreeBSD 7

DSSH 1.0z released 27.11.2007
=============================

 - Added support for Leopard Java 6 preview from open source java6 porting effort. Tested with 64-bit version on Leopard. Make sure you have correct path to java6 in /etc/dssh/dssh.opts.

DSSH 1.0y released 13.8.2007
============================

 - Add InteractiveEnaSession, which should allow executing commands as "ena" user on Cisco ASA 552x. We use it for automatic collection of "show running-config" among other things.

DSSH 1.0x released 16.7.2007
============================

 - Nicer error messages

 - Correct return values from commands

 - Allow to force interactive mode and stay logged after executing command (parameter -I)

 - Added paramter for verbose connects (-v)

 - Can surpress output for InteractiveSuSession (enabled by default, disable with -O)

 - Several bugs fixed
