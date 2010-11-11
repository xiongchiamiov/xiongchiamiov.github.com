---
layout: with-comments
title: Open-Source vs. Opened-Source
---

Increasingly, companies are starting to realize the benefits of open-source
software. While you effectively lose the ability to sell the software itself,
you get free *fantastic* testers, who will even sometimes contribute patches to
fix issues that they discover. Any large OSS project has at least one person who
has put tremendous effort into writing helpful documentation, too, which tends
to be sorely lacking in proprietary systems.

I've noticed some companies attempt to tap into this without fulling
understanding that open-source is not merely an issue of licensing, but a
**viewpoint**, almost a development methodology in itself.

In most OSS projects, there is a leader (or a core team) who has to approve
**every** change to the code. Aside from the benefits of inherent code review,
this means that a sufficiently strong-willed leader can set strict rules (for
instance, all changes to the API must be accompanied by a corresponding change
in the documentation) that really, honest-to-goodness, *must* be followed for
your code to make its way into the official version.

Developers who contribute to projects in their spare time tend to code a lot
(and read lots of code from people much better than them!), so you also tend to
get higher-quality code on average in OSS than from run-of-the-mill "software
engineers".

Anyways, in the past few years I've seen more projects "open-sourced", with
companies hoping to get the community to fix all the problems created by their
crappy programmers.

As much as I love Komodo Edit, it is a perfect example of this. Although
[ActiveState tries] to encourage community
participation, **every single** [open bug] (and there are a lot!) is owned by a
foo@activestate.com. This is not the sign of a healthy community, and OpenKomodo
has been around since 2007.

![](/media/images/posts/2010-04-22-open-source-vs-opened-source/komodo_bugs.png)

Take a look at something like Django or Rails, though:

![Django's impact graph on GitHub](/media/images/posts/2010-04-22-open-source-vs-opened-source/github_django.png)
![Rails's impact graph on GitHub](/media/images/posts/2010-04-22-open-source-vs-opened-source/github_rails.png)

Each of those different colors represents a different person making commits,
with the size being directly related to the number of lines changed. This, my
friends, is working open-source.

[ActiveState tries]: http://www.openkomodo.com/
[open bug]: http://bugs.activestate.com/buglist.cgi?query_format=specific&order=relevance+desc&bug_status=__open__&product=Komodo&content=
