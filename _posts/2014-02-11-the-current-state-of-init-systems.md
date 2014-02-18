---
layout: post
title: The current state of init systems
comments: true
---
Recently, the **init systems**'s world has been moving a lot. After many
discussions, *systemd* have good chances to be adopted as Debian's default init
system. But, for those who do not really know what it is and mean, this
information is pretty useless... or at least «just another news in a day».

###What's that init system ?
According to [Wikipedia](http://en.wikipedia.org/wiki/Init):
> \[...\] init (short for initialization) is the first process started during
> booting of the computer system. Init is a daemon process that continues
> running until the system is shut down. It is the direct or indirect ancestor
> of all other processes and automatically adopts all orphaned processes...


###Know the Linux startup process
To my eyes, this definition needs additional informations. In fact, to easily
understand the place and role of the init system in Linux, one might know
the Linux startup process. And as a picture is worth a thousand words, here is
one!

<img src="/public/linux-startup-process.jpg"
     alt="Linux Startup Process" width="100%"/>


First, note that the schema has been highly simplified. Only one blog post will
never suffice to describe the whole startup process.
As you may notice, the main parts of the schema are commented, but still need
some additional stuffs...

* BIOS: Once you turn on your computer, the first task it does is to run the
  BIOS (or *Basic Input/Output System*). Unlike following parts, this software
  is tied to the computer manufacturer and is part of the hardware.
  Its main task is to run tests on hardware and detect failures (no RAM, problem
  with the CPU...) BIOS is slowly being replaced by
  [UEFI](http://en.wikipedia.org/wiki/Unified_Extensible_Firmware_Interface)

* Boot loader: If nothing went wrong during the BIOS' tests, this one runs the
  boot loader from the MBR (Master Boot Record). Explained simply, the boot
  loader is just a software that you use to start an OS, or do some advanced
  tasks as an administrator (in case you reach some extrem cases). The runnable
  OSes can be others than Linux, you can even run your good'ol Windows (And even
  Windows have its own bootloader).

* Kernel loading: this is probably the darkest part of the process. Given that a
  «normal» user should not be able to run some critical tasks on the OS, this
  one start itself in kernel mode for loading device drivers, or a bunch of
  kernel modules. By the way, apart the security issue, i am sure you does not
  want to do all these by hand...


###You missed one, and what's that init system again?
The best part, or let's say, the *Human* part of the Linux startup process is
the **userland**. Once the kernel finished all its tasks, the userland space
just take over and run all the tasks that are possibly runnable by users without
too many risks. And that's where the **init system** step in.

This one has been created to execute all the early run tasks like mounting the
filesystem. Plus, it also manages all the process that will be spawned during
the machine's uptime until it gets shut down. Yes, even your *nginx* you
launched 5 minutes ago is managed by the init system, what makes it its parent.
So, init is the first process that is launched in userland (its PID is 1), and
is the parent of all other processes. If one die, it knows it. And if init is
killed, every other process dies with it. It is that simple.


###Why are there so many init systems?
Initially, the default init system where just named after **init**
(«init daemon» or «SysV init»); but it went old and its designs are not suitable
for our time anymore, so some replacements has been created.

However, from all the candidates, 3 has been widely used: **OpenRC**,
**upstart** and **systemd**. All of them are Free and Open Source softwares.

From now, i will explicitely name the init daemon by SysV init. If *init system*
is present, it means the generic initialization system (without distinction
between daemons.)

* OpenRC only works *with* the init system (usually Sysv init) and does not aim
  to replace it. One of its greatest features and advantages is that it is
  portable to non-linux distributions, so you can use script for Linux
  distributions on a BSD-based distribution for example.

* Upstart has been developed by Canonical as a replacement for Sysv init, this
  one having some design issues. The main difference between them, which is also
  a strength for Upstart, is that Upstart is a non-blocking init system. So
  if you start to tasks, the later run will not have to wait the first to finish
    before launching.

* The last one, systemd, is the future. In addition to the parallel starting of
  the processes, systemd is also a whole framework, as it comes with a logging
  system, a job sheduler (replacements for *syslog* and *cron*), and many other
  features/programs.


###Why is systemd winning the init war?
Since it announcement, systemd has been widely adopted. Practically all the
major Linux distribution now enable it by default as there init system
(Fedora, ArchLinux, RHEL 7 => CentOS, OpenSuse...) and it will be [choosen for
the next Debian release (Jessie)](https://lists.debian.org/debian-ctte/2014/02/
msg00402.html). After Debian decided to use systemd, Mark Shuttleworth announced
on [his blog](http://www.markshuttleworth.com/archives/1316) that this would be
also an decision for Ubuntu as a part of the Debian family.

But why does it succeed? IMHO, one key of its success is the set of features it
comes with. Instead of being a replacement for just Sysv init, it also comes
with a complete ecosystem. Plus, the systemd startup scripts are not written as
shell script but in a simple and powerful declarative language.

But apart the technical features, i think the biggest advantage it have against
its concurrent are not even technical. And i will finish on these:

* Documentation => systemd has an extensive documentation, from internal designs
  to usage and include configuration.

* Communication => If systemd is were it is now, IMO, it's because its
  developers has been «selling» their product to distributions. Fedora, which is
  really not a small distro, adopted it one year after the initial release as
  its default init system. And even [people at Spotify like it](https://bugs.
  debian.org/cgi-bin/bugreport.cgi?msg=3546;bug=727708).

* It has a growing community; which is to me one of the most important arguments
  when picking a solution.

Some comments has been added via reddit, here is the thread: [http://www.reddit.
com/r/linux/comments/1xtg4j/the_current_state_of_init_systems/](http://www.
reddit.com/r/linux/comments/1xtg4j/the_current_state_of_init_systems/)
