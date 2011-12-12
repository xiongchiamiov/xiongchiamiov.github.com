---
layout: with-comments
title: IDEs are Uncohesive
---

I dislike IDEs.  I enjoy being able to swap out pieces of my development
toolchain, bit by bit, without having to wait for someone to write a new
plugin.  I am a grumpy Unix programmer.

---

This Fall quarter, I took a class about software design.  Yes, yes, the course
title is "Individual Software Development", but that's not at all what it was
about.  We discussed [CRC cards], [Design Patterns], [Design-by-Contract], and
all sorts of ways to [make your programs better][0].

One of these was cohesion.

It's a generally accepted idea in software engineering that your programs
should be cohesive; that is, each part should do one thing and those different
parts should all work nicely together.

You might recognize this as one of the most well-known parts of [the Unix
Philosophy]:

 > Write programs that do one thing and do it well.

IDEs are completely in violation of this principle - they do *everything* a
programmer might want an application to do, and the same issues arise as with a
poorly-cohesive method.

Remember [that convenient method][var_dump] that calculates a value and then
prints it out?  It's a little bit of a pain now that you want the value, but
don't want to send it to `stdout` just yet.

Remember that nifty way to manage versioning of files inside your editor?  It's
a little bit of a pain now that you want to use [Fossil] instead of CVS.

It frankly astounds me that programmers would apply a lesson to one part of
their professional life without applying it to another.  In fact, many of them
will vehemently defend both positions.

Save your future self - make all your tools tightly cohesive.

[CRC cards]: http://en.wikipedia.org/wiki/Crc_cards
[Design Patterns]: http://en.wikipedia.org/wiki/Software_design_pattern
[Design-by-Contract]: http://en.wikipedia.org/wiki/Design_by_contract
[0]: http://en.wikipedia.org/wiki/Design_by_contract
[the Unix Philosophy]: http://en.wikipedia.org/wiki/Unix_philosophy
[var_dump]: http://php.net/manual/en/function.var-dump.php
[Fossil]: http://fossil-scm.org/index.html/doc/trunk/www/index.wiki

