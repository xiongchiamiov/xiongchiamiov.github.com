---
layout: with-comments
title: On Being a Volunteer Sysadmin
---

It's kinda hard to do.

The actual process isn't difficult (you just do work, like you would normally),
but finding out how to contribute is much more of a PITA than it should be.
Most notably, it's more difficult than it is for programmers.

The open-source software movement has grown over the last 30 years to be
continually easier to join, at least from a technical perspective.  For simple
changes, you can submit a set of changes to someone else's code, in a manner
that gives them (and any other interested parties) a notification and an easy
way to review the changeset, without using anything more than a browser (hooray
for Github!).  That's awesome!

Getting your code up onto a shared platform is insanely easy, too.  Github
allows a free account to have infinite open-source repositories; this, combined
with the lack of oversight (you just put in a name, hit create, and push your
repo) has lead to an increasing democratizing of open-source: instead of only
sharing a few select projects that the author feels are high-quality or useful
to many others, coders are increasingly sharing everything they make - and
finding more people want to use it than they ever suspected!

But as a sysadmin, life is not so cheery.  Yes, you're a sysadmin, so life is
never as cheery, but issue at hand is that of contribution.  For instance, take
a look at [Skud]'s current project, [Growstuff].

The Growstuff repository [has had][Growstuff contributions] people hacking away
at it for a couple months.  Non-core members have been contributing using the
magical Github fork button.  Things are great!

But then take a look at, oh, [this wiki page on their shared development
environment][Growstuff hack-server].  It's filled with [apologies] to the
programmers for things that haven't been done yet, [a list] of half-filled
instructions for manually creating a user account, and [a plea] for someone to
spend just a little time making this all better.  But how would I do so?  The
server is a one-of-a-kind environment - I can't fork it and submit a pull
request after I've done some setup.  To make the changes, I need to have root
access on a shared box - something you want to be very careful about handing
out.

And thus, projects start to pick up programmers, and suffer from a lack of good
system administration.  Such is the world.

[Skud]: http://infotrope.net/about/
[Growstuff]: http://growstuff.org/
[Growstuff contributions]: https://github.com/Growstuff/growstuff/contributors
[Growstuff hack-server]: http://wiki.growstuff.org/index.php/Hosted_hack_environment
[apologies]: http://wiki.growstuff.org/index.php?title=Hosted_hack_environment&oldid=1097#Setting_up_your_hack_environment
[a list]: http://wiki.growstuff.org/index.php?title=Hosted_hack_environment&oldid=1097#Sysadmin_notes
[a plea]: http://wiki.growstuff.org/index.php?title=Hosted_hack_environment&oldid=1097#TODO

----

At [iFixit], we use [Amazon's web services][AWS] to host all of our content.
One of the primary differences between cloud services and a standard VPS-based
solution is that any of your machines may disappear at any given time - poof!
This is generally cited as a disadvantage, but I prefer to see it in a more
positive light - accepting this as a fact of the system forces you to avoid
hand-crafted servers and embrace automation.

A server that is configured entirely using a configuration management tool is
one that can be forked.  It may seem like more work than to just set it up by
hand, but as is often the case with open-source, you'll often find many people
wanting to make contributions, but stumped at how to go about doing so.  It can
even be useful internally; as we've been moving our server configuration out of
a proprietary system into a git repository, developers have been empowered to
make pull requests for changes they want, but I haven't had time to get to.
Even if you distrust developers with root access, this system works - you only
need give them elevated privileges on the testing server they spin up, and any
changes still need to be pulled in to the canonical branch after they've been
proposed, which gives you a chance to review them and make suggestions.

So here's the point of all this: you need to open-source the server
configuration for your open-source project.  Yeah, you really do.  The upfront
investment isn't as bad as you think, and the payoff will be worth it.  There's
an army of sysadmins lurking in the shadows, waiting to be someone's
super-hero.  Open up and let us share - you might be surprised at how well it
works.

[iFixit]: http://www.ifixit.com
[AWS]: http://aws.amazon.com

