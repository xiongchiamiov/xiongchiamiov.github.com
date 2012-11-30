---
layout: with-comments
title: Ubiquitous Programming Problems
---

I am very much a supporter of the [open-source] movement.  An essay on the
moral obligation to open-source your software has been rattling around in my
head for the past few weeks, and while I was mulling this over in the shower
this morning, I realized something: most of my programmer colleagues don't
open-source their work because they don't *have* any work to open-source.

This might sound strange - a programmer doesn't have any programs?  But many
people only ever write code for their employer, which takes licensing out of
their hands.  The question, then, is: why don't they write anything outside of
work?

Whether it's good for a programmer to write code outside of work is a
heavily-debated subject, focusing on building programming chops vs. becoming a
well-rounded individual.  I'm not concerned with *intentional* choices though -
rather than asking "Why don't you program in your spare time?  It's good for
you!" I'm asking "How can you *not* program in your spare time?".

When I first got introduced to programming, my enthusiasm quickly died off.  I
made a program that spits out the numbers one to ten - great, and so what?  But
web development, oh, was that different!  With some basic HTML lessons I could
*make my own web pages* - something only gods could do!  Suddenly my universe
expanded, providing options I never considered possible previously.  Much of
my joy of programming comes from a continuation of this feeling - there are now
so many problems in my life that I have the power to fix.  Even if I choose not
to, it makes me cope better with buggy or unfriendly software I use - if I
complain about it, I'll have to fix it or make a replacement, so sometimes I
choose to just tone down the grumbles. :)

Many of these problems are very small, which makes them great for an hour's
hacking.  For instance, I use development builds of [my music
player][Clementine] and was having troubles with it sometimes not reporting the
music I played to the statistics-gathering website [Last.fm].  I could keep
refreshing my profile page to see if tracks were added, but that required a
browser window, flash running, waiting for the page to reload, and just seemed
too heavy a solution.  So, I spent a little time pulling tracks out of the RSS
feed Last.fm helpfully provides and made [lastfm-tail].  It's quite simple, but
solves the problem exactly (I use it nearly every day), and since I had no
reason not to, I made it publically available, both as source on Github and
easily installable as a Ruby gem.

My life is filled with problems like this, and I can't help but see the
programming solutions to them.  Why doesn't everyone?

----

I'm also interested in the general consideration of this trait: is it good,
bad, or insignificant when evaluating a programmer?  There are companies that
publically state they favor candidates with open-source involvement - is this
one of the reasons?

[open-source]: http://en.wikipedia.org/wiki/Open-source
[Clementine]: http://www.clementine-player.org/
[Last.fm]: http://last.fm
[lastfm-tail]: https://github.com/xiongchiamiov/lastfm-tail

