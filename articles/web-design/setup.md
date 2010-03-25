---
layout: default
title: Setup - A Proper Introduction to Web Design
---

<span class="nav">&laquo;[Previous] &sect; <strike>Next</strike>&raquo;</span>

Before getting started doing any coding, you need to have a proper environment
setup. Many guides will tell you that you can use any text editor you wish, and
recommend that Windows users use Notepad, and Mac users TextEdit. While it is
true that either of these will work, their simplistic nature will build bad
habits that we wish to avoid.

My [editor of choice] is [Komodo Edit], a free, multi-platform editor that
specializes in web and scripting language support. Go ahead and download and
install it, and we'll change a few things from the default configuration.

(As a side note, when installing Komodo on a fresh install of XP to create these
images, I had to install the [Microsoft Visual C++ 2005 SP1 Redistributable
Package] for Komodo to run.)

When you first start Komodo up, it looks a little busy:

![Komodo Edit](/media/images/articles/web-dev/komodo_01.png)

You can get to the preferences from the edit menu.

![Komodo Edit](/media/images/articles/web-dev/komodo_02.png)

First off, you'll want to uncheck all of the toolbars and startup panes. Using
them rather than the keyboard shortcuts will slow you down, and if you forget
the shortcut for any commands, they're all accessible via the menus.

![Komodo Edit](/media/images/articles/web-dev/komodo_03.png)

Next, I always tell Komodo to use tab characters, rather than spaces, for
indentation. This is a personal preference in a much-debated topic, but the
short of it is that using tabs allows you to change how large the indents in
your code are at any time. I generally use 4-space indents, but depending on
your screen resolution and preferences, you may want to change this at some
later time.

![Komodo Edit](/media/images/articles/web-dev/komodo_04.png)

Using tab to autocomplete words is amazing - once you have it, you won't be able
to live without it. Also, restoring file folds when you reopen files is handy to
get you back to where you were last time you edited. If you find that opening
files takes a long time, try unchecking this again.

![Komodo Edit](/media/images/articles/web-dev/komodo_05.png)

I find that a dark color scheme is easier on my eyes. You can play around with
the colors in here (and font sizes) to find something that works well for you.

![Komodo Edit](/media/images/articles/web-dev/komodo_06.png)

Since we'll be editing a lot of HTML files, it's useful to override the default
file encoding with the META tag. This won't really matter much, though, unless
you start using non-latin characters (things with accents, or any Asian
characters).

![Komodo Edit](/media/images/articles/web-dev/komodo_07.png)

That's it!  Now you can press ok to save those changes.

For whatever reason, two of the toolbars don't have options to deselect them in
the preferences. You can go ahead and get rid of them now by right-clicking on
the toolbar area.

![Komodo Edit](/media/images/articles/web-dev/komodo_08.png)

Now we're ready to start doing some work.

<span class="nav">&laquo;[Previous] &sect; <strike>Next</strike>&raquo;</span>

[Previous]: basic-theory.html

[editor of choice]: /2010/03/18/why-i-love-komodo-edit.html
[Komodo Edit]: http://www.activestate.com/komodo_edit/
[Microsoft Visual C++ 2005 SP1 Redistributable Package]: http://www.microsoft.com/downloads/details.aspx?FamilyID=200b2fd9-ae1a-4a14-984d-389c36f85647&displaylang=en
