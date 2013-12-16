---
layout: post
title: My awesome Linux environment&#58; from apps to dotfiles
comments: true
---

Since i switched from Windows to Linux, i have been using *Ubuntu*, *Fedora*, then
Ubuntu again, before choosing this last for almost 4 years. In these for years,
i've been using multiple apps, before and after being interested in computer
science, even if, as you can imagine, it changed a lot of my habits.

Today, i'm using **Archlinux**. Yes, i leaved my lovely Ubuntu since 6 months now.
The main reason was that, as a developer, i hated on the fact that last
packages' versions were almost never available. And i had to search for hours
for a PPA to install some packages, before realizing i got the wrong version.

But, we are not there to talk about my hatred of the late Ubuntu packages
availability. Contrariwise, i will talk about the tools i use in my daily life.

# I see code everywhere
![GVim, the most powerful editor](/public/gvim-django.png)

Even if i know it quite a long time, i beginned using **Vim** since only 6 months.
If you want to join the Vim users, you should use GVim, which is a Vim version
with a graphical interface. By using this, you could learn at your rhythm and
use the mouse for almost all tasks (i think ...).

It is an awesome text editor, and i really don't regret using it. It have all i
need for coding, editing all sort of files, and even if i wont probably use it
for languages like Java, i will always use it for those like Python or Perl.

# Desktop environments

Having used Ubuntu for years, when Gnome was still the desktop manager, i never
changed. I spent a little time testing Unity but i finally returned to Gnome.
Now, it's Gnome Shell but the break have not been too hard for me. It's pretty
easy to use, and the desktop switching is THE feature i love for coding.

Next to Gnome Shell, i use the Awesome window manager occasionally to see how it
works and test some of the capabilities. It's highly configurable and could even
help me learning Lua so maybe i will swich from Gnome Shell to it one day. If
they stop breaking the API at each release.

# Probably my favourite GUI programs ... 
* Chromium

    **Chromium** is the base of the Google Chrome web browser. It's open source and
    heavily improved by the community. Being the codebase of Chrome, it's not a
    lot different of it. The missing parts are the PDF reader (Adobe Reader),
    and the NSA backdoors. It supports Chrome Extensions.

* Transmission

    **Transmission** is probably the tool i liked the most in Ubuntu, where it
    stands as the default Torrent/Magnet client.

* Mozilla Thunderbird

    To my eyes, it's the most featured graphical e-mail client on Linux. I tried
    to use Mutt (a command-line one) but i did not last long. The main problem
    that i could have with it, is that it's not highly configurable ... :/

* Gnome Terminal & Terminator

    What's a Linux user without a terminal emulator ? Nothing. That's why i
    spend the most of my time (or almost) trying to find THE terminal that will
    change my life. But for the moment, i only found these two. **Gnome
    Terminal** is the terminal of the Gnome project and **Terminator** is a
    terminal multiplexer, in that you can have multiple terminals in only one 
    window. They both worth a try.

# Command Line Tools Rocks.
I write code a lot. And versionning, testing librairies and writing unit tests
have become parts of my life.
* For versionning, i'm using **Git**, because it rocks and because i want to
  know it more deeply too.

* As a Python developer, testing librairies, and their support of Python's
  versions is the daily life now. So i use **Virtualenv** to test multiple
  versions of librairies or Python versions. They are all sandboxed so their is
  no way to break my other projects.

  I discovered unit tests this year as an intern @ [Kozea](http://kozea.fr
  "Kozea"). They were using *nose* as the unit testing tool, so i adopted it. I
  should take the time to test some other tools one of these days.

By the way, i love IRCs, and i use **IRSSI** for it.

# Keep calm and write .dotfiles 
These files changed my life. Customizing almost all my tools so that i can use them
without losting time even increased my motivation for learning and working. It
started with *.zsh*, the configuration file for the **Zsh shell**. Then it was
the turn of **Irssi**, my favourite IRC client. Anyway, writing these made me
gain a lot of productivity. And, even if you don't know how to write your
dotfiles, Github is a great source of inspiration. And community-driven
frameworks like [OhMyZsh](http://github.com/robbyrussell/oh-my-zsh) or [Github's
dotfiles](http://dotfiles.github.io) can help you setting your workflow up
more easily.


# The closing thoughts
Switching from tool to tool these last year helped me gain in productivity and,
ironically, lazyness. I realized how powerful and useful were the Open Source
culture and i learned a lot from only watching repos on Github (dotfiles, cool
projects, useful tools, etc) ...

If you have any idea of tools that's worth testing, let me know ;)
