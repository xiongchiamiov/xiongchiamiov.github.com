---
layout: default
title: Why I Love Komodo Edit
---

Ever since I moved to Linux (winter break of my freshman year, so January 2008
or so), my editor of choice has been [Komodo Edit]. Although it has a certain
amount of popularity among Pythonistas, it is not nearly as popular as several
other editors, so I thought I'd discuss my reasons for using it. I've also been
considering moving to something else, but haven't been satisfied with other
choices yet, so this is a bit of a fishing trip (you can find contact info on me
over at, of all places, [the contact page]).

The winter break of 2009 (breaks are a great time to get things done), I took
the plunge and started learning basic vi keybindings. Komodo supports this
natively, and they are too well ingrained into my fingers for me to move away
from them. In fact, I use [Vimperator] on all of my computers as well to keep
the same thought process for my two most-used applications, and I'd love for
everything I use to share this common trait. So, for good or for bad, I *must*
have vi-like operation.

Komodo also has the right amount of stuff, but not too much. As seen below, my
window is generally fairly minimalistic.

![Komodo Edit](http://xiongchiamiov.github.com/media/images/posts/2010-03-18-why-i-love-komodo-edit/komodo_01.png)

I have line numbers (can't live without 'em), tabs so I can visually see what
files I have open at any given time, some other minor information, and some menu
buttons, which I find useful for accessing commands that I don't use frequently
enough to memorize the shortcuts to.

I can also split the screen vertically or horizontally, and move files easily
between the two sides, which is incredibly handy on my widescreen laptop. Since
I am using [a tiling window manager], I can simulate this to an extent, but it's
still a nice feature.

Ctrl+Shift+P unhides my project listing. For small projects, standard terminal
navigation is sufficient, but as the size and number of directories increases,
so does the value of being able to easily visualize it. I prefer to keep this
out of the way when I'm writing, so the ability to show and hide it quickly is a
must.

![Komodo Edit](http://xiongchiamiov.github.com/media/images/posts/2010-03-18-why-i-love-komodo-edit/komodo_02.png)

While I can, of course, set preferences for file encoding, indentation, and line
endings (and can change those on a per-language basis), Komodo will respect
those in the files that I edit. This is incredibly necessary when working on
different projects, each with their own rules. Any mixing of indentation will
give me green underlines (similar to those in Word indicating incorrect
grammar), and a ctrl+shift+8 will show me the whitespace characters so that I
can fix them. The same lines appear for differing line endings; ctrl+shift+7
displays them, and one of the menu options makes them consistent. Both of these
are things I've consistently had to fix on a recent group project, where all the
other members used either gEdit, Eclipse, or vim.

![Komodo Edit](http://xiongchiamiov.github.com/media/images/posts/2010-03-18-why-i-love-komodo-edit/komodo_03.png)

There is always code folding available at the places I want it, and it clearly
shows a fold without being distracting. Even more of a plus is that Komodo
restores the state of the folds in a document when I reopen it, so that I don't
have to refold all of the code I'm not interested in at the moment all the time.

![Komodo Edit](http://xiongchiamiov.github.com/media/images/posts/2010-03-18-why-i-love-komodo-edit/komodo_04.png)  
![Komodo Edit](http://xiongchiamiov.github.com/media/images/posts/2010-03-18-why-i-love-komodo-edit/komodo_05.png)

It was trivial to use a dark color theme for Komodo, although changing some
elements of the interface was [a bit more difficult]. Nonetheless, it is nothing
like [the annoyance] that is Eclipse.

I can use tab to complete words that I've been typing in the document (without
any special modification), or to complete tooltip options based on the languages
Komodo has them for. Having to use something other than tab is unacceptable,
since I've been trained by my editor, my shell, and my irc client to do so.

![Komodo Edit](http://xiongchiamiov.github.com/media/images/posts/2010-03-18-why-i-love-komodo-edit/komodo_06.png)  
![Komodo Edit](http://xiongchiamiov.github.com/media/images/posts/2010-03-18-why-i-love-komodo-edit/komodo_07.png)

Along these same lines, I'm auto-indented in when opening a block, and closing
keywords are either added automatically or pop up for completion.

![Komodo Edit](http://xiongchiamiov.github.com/media/images/posts/2010-03-18-why-i-love-komodo-edit/komodo_08.png)  
![Komodo Edit](http://xiongchiamiov.github.com/media/images/posts/2010-03-18-why-i-love-komodo-edit/komodo_09.png)  
![Komodo Edit](http://xiongchiamiov.github.com/media/images/posts/2010-03-18-why-i-love-komodo-edit/komodo_10.png)

What do I not like about Komodo? It's an X application, so, while it still has
functionality to edit files over FTP/SFTP/SCP (and even add them to projects),
it cannot be run in a [screen] session, detached, and reattached at another
location. Being based upon Gecko, it can also be a bit of a memory hog, although
I still avoid using swap with both it and Firefox (and a few other things)
running on one gig of RAM.


[Komodo Edit]: http://www.activestate.com/komodo_edit/
[the contact page]: /about_contact.html
[Vimperator]: http://vimperator.org/
[a tiling window manager]: http://awesome.naquadah.org/
[a bit more difficult]: http://community.activestate.com/faq/customizing-the-komodo-ui#comment-12166
[the annoyance]: http://stackoverflow.com/questions/96981/color-themes-for-eclipse/1248204#1248204
[screen]: http://www.gnu.org/software/screen/
