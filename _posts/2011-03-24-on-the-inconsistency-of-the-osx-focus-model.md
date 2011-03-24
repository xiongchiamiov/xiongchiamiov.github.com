---
layout: with-comments
title: On the Inconsistency of the OS X Focus Model
---

I recently switched jobs.  My new work computer is a MacBook, so I am once
again working primarily on OS X, something I haven't done in a few years.  Now,
don't get me wrong - I haven't gone and installed [Arch Linux] on it yet, so I
obviously find it decent enough to spend hours of my life with.  However, there
are a few things that are just incredibly irritating about the OS - and the
focus model is one of them.

My standard working setup is to use two desktops (spaces) for most work.  The
first has a terminal on the right for editing and a Firefox window on the left
for testing.

![Example of my desktop, as described in the previous paragraph](/media/images/posts/2011-03-24-on-the-inconsistency-of-the-osx-focus-model/desktop_01.png)

The second desktop has a Firefox window (or perhaps several, tiled) available
for querying of... well, whatever.

![Example of my second desktop, as described in the previous paragraph](/media/images/posts/2011-03-24-on-the-inconsistency-of-the-osx-focus-model/desktop_02.png)

Here is a common scenario for me:

1. Hack hack hack in terminal.
2. Switch to second desktop to look something up.
3. Switch back to first desktop and start typing.

Unfortunately, this doesn't work very well in OS X - my keystrokes are instead
sent to Desktop 1's Firefox window!

You see, in OS X, focus is determined by *application*, rather than by
*window*.  While this doesn't make very much sense to me (in my mind, the last
thing focused on a desktop should be focused once again when I switch back to
it), I suppose it does make a certain amount of sense to, shall we say,
"normal" people.  I'm hardly representative of their primary target audience,
particularly as a [tiling window manager][awesome] user.

The real problem I have with the focus model, however, is that it isn't
consistent.  If I want to open a new Firefox window on a blank desktop, I have
to:

1. Switch to the desktop.
2. Focus Firefox (cmd+tab, Spotlight, Quicksilver, dock, etc.).
3. cmd+n

If focus is truly defined by application, I should be able to have Firefox
previously focused (say, by browsing the web), then switch to the new desktop
and open a new window, skipping step 2 entirely.  However, focus switches to
Finder.

And no, it's not just something special about Finder; in my first example,
switching to the second desktop automatically focuses Firefox because there
isn't a Terminal window open on that desktop.  If I cmd+tab, however, I get
focus switched to Terminal, even if there are other non-Firefox windows on that
desktop.  Beh.


[Arch Linux]: http://archlinux.org
[awesome]: http://awesome.naquadah.org/

