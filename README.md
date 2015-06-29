DSSH
====

DSSH is Digmia Secure Shell. It was written as a direct replacement for OpenSSH client for our use. DSSH adds SSH over SSH tunelling capabilities (for example to log in to network which is behind by firewall that supports SSH), scripting support (using BeanShell), advanced agent (which allows storing of passwords) and "su -" interactive logging for machines, which have disabled direct root login.

All of this was done to enable automated scripting and logging to lots of machines based on a few simple rules.

It uses Trilead SSH library (slightly patched, included).

Requirements
============

DSSH requires:

 * a terminal emulator (Windows command prompt will not work for this purpose, so only UNIX-like systems are currently supported)
 * Java runtime environment (at least 6.0)

Supported platforms
===================

Out of the box these platforms are supported:

 * Mac OS X on x86_64 (other platforms don't have Java 6 support)
 * Linux on x86 and amd64/x86_64
 * FreeBSD 7
 * Solaris 10

Installation and usage
======================

Please see documentation in the tarball. Alternatively, you can read introduction and dssh.bsh example (highlighted for viewing , downloadable)

Common problems
===============

If you change IP addresses (for example when using dssh on a laptop computer, that is connected to several networks), you will probably find out, that dssh takes quite a long time to connect to an agent (it looks like it hung up), or ends with an error message. This is because RMI server (in this case dssh-agent) sends it's hostname to dssh client, which then tries to connect back. If you have different IP addresses, or different hostnames, this is what you would see. I recommend adding -```Djava.rmi.server.hostname=localhost``` to ```JAVAOPTS``` in your ```dssh.opts``` (by default in ```/etc/dssh``` or ```~/.dssh```). This is a limitation of Java RMI, not DSSH itself.

Use cases
=========

 * Collect configuration parameters from Cisco routers which require "ena" login
 * Log in to servers, which have ```PermitRootLogin``` disabled directly as root (by typing su - and password automatically), while preserving exit status
 * Tunnel through several connections to get to target server
 * Add custom logic such as advanced logging

