---
layout: with-comments
title: Why Python Encourages Maintainable Systems
---

I love [Python].  I don't think it's the right answer for everything, but I do
act as its advocate for many new projects.  Since most of my programming has
been spent working with legacy systems, I am primarily concerned with
maintainability, and Python is built on two ideas that directly benefit that
cause: explicitness and a culture of documentation.

# Explicitness

If you run `import this` in a Python console, you'll get [the Zen of Python] -
a series of guiding principles for the language.  First is "beautiful is better
than ugly", and immediately following is my favorite:

> Explicit is better than implicit.

Explicitness is a core part of Python; it's been conciously taken into account
when designing the language.

[I've written previously][Python's modules] on Python's modules; let's just say
that it's very explicit and gives me a hard-on, and we'll leave it at that.

While Python is not statically-typed, it is *strongly-typed*.  A string is a
string, even if it happens to have numbers in it, so if you want to treat it as
an integer, you must first explicitly convert it as such using `int()`.  This
helps prevent bugs that surface in weakly-typed languages such as C and PHP.

Perhaps the most obvious example of Python's obsession with explicitness is
`self` - the most hated part of Python other than using indentation to
determine program structure.  In Java, a seemingly benign assignment

    foo = 'bar'

could either be assigning to a local variable or an instance variable.  Worse,
the action of this code can change completely by altering other code around it!

Python requires the instance to be explicitly listed as a parameter to class
methods, and any alterations to instance variables **must** go through that
variable.  Non-Pythonistas think this is crazy.  I think [it has very good
reasons for existing][explicit self] and we're the only sane ones.  Sigh.

[Python]: http://www.python.org
[the Zen of Python]: http://www.python.org/dev/peps/pep-0020/
[Python's modules]: http://changedmy.name/2011/02/16/why-pythons-modules-are-badass.html
[explicit self]: http://neopythonic.blogspot.com/2008/10/why-explicit-self-has-to-stay.html

# A Culture of Documentation

The Python community, as a whole, loves to write documentation.  In fact, they
love to write *good*, nay, **great** documentation, just as much as Rubyists
write unit tests for even the simplest programs.  It's just a part of the
culture.  But how did it end up this way - by accident?  Indeed not, as the
language itself encourages documentation through a number of means.

At a meta level, while much discussion happens on the mailing lists, important
decisions about Python end up as [PEPs].  PEPs have several purposes, [one of
which is][PEP-whatis] to document the arguments for and against various
proposals, and the rationale used to choose one.  When there's a question of
why something is the way it is, there's a PEP with the corresponding answer.

At a level closer to implementation, Python uses a construct called
[docstrings].  These are comments that are recognized by the Python parser as
documentation for a module, class, or function, and bundled as part of the code
they describe.  Rather than having to dig through a complex webpage of
documentation, a developer wishing to receive some information on a particular
object need only pass it to the `help()` function to receive the documentation
specified in its docstring.  Since this is incredibly handy and doesn't require
any special tools, developers are encouraged to incorporate them into their own
code, whichs leads to happier programmers down the road.

[PEPs]: http://www.python.org/dev/peps/
[PEP-whatis]: http://www.python.org/dev/peps/pep-0001/#what-is-a-pep
[docstrings]: https://en.wikipedia.org/wiki/Docstring#Python

# Conclusions

Should you rewrite your project in Python?  [Almost certainly not][rewrites].
But if the maintainability of a new project years in the future is of concern
to you, please take a look at Python and consider what it can do for you.

[rewrites]: http://programmers.stackexchange.com/questions/6268/when-is-a-big-rewrite-the-answer/

