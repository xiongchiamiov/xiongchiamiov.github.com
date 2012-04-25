---
layout: with-comments
title: What Can the iPad Teach Us About Software Engineering?
---

Software engineering is interesting.  You see, first computer science sprouted
out of math as a way to solve a bunch of problems that were previously
computationally infeasible.  As we stretched the limits of computation more and
more, though, we started to run into problems with these large systems we had
created.  So, reluctantly, the mathematicians turned to those smug
know-it-alls, the engineers.

But software is inherently a completely different ballgame.  That it's all
virtual has a number of implications; the one I want to talk about today is
maintenance.

See, most traditional engineering projects go through a predictable (and
sensible) lifespan - they're designed, they're built, they're used, they're
retired.  We've tried doing this with software, but the problem is that, due to
its unique nature, we *can* continue modifying it after its built, oftentimes
while people are still using it!  Can you imagine the foundation of your office
building being replaced while you're still in it?  Frightening!  But since we
have the capability to do this with software, we *must* - if our relentless
desire to craft a better product doesn't do it, the features and fixes our
managers and clients request will.

This shift to flexible long-term thinking requires a fundamental shift in how
we view construction.  Let's look at a real-world parallel for a moment.

## The iPad 3

There's been a slight bit of drama over Apple's latest tablet; while we at
iFixit aren't too thrilled about [the over-reliance on glue][0], [some are
arguing][1] it leads to a better product for consumers.

[0]: http://ifixit.org/1863/three-ways-we-hoped-the-ipad-would-be-better-but-wasnt/
[1]: http://techcrunch.com/2012/03/19/should-apple-make-the-ipad-user-serviceable-nope-thats-anti-consumer/

Fresh out of the assembly line, this is true.  Not only does the lack of
fastening tabs make a slightly thinner product, but it is likely easier for
Apple to produce, theoretically leading to lower prices.

[But this is an extremely short-term view][2].  When the battery starts losing
life, you'll be hard-pressed to replace it.  Wanted to pass on your old device
to your kid?  Sorry, bud, but this is a consumable device.

[2]: http://ifixit.org/1927/techcrunch-is-full-of-it-repair-is-exactly-what-consumers-need/

## Software is Not Consumable

Software lasts [a very, very long time][3], and some poor sod is going to have
to maintain it.  Not only is it discourteous to program with a consumable-based
mental model, it's bad business sense.

[3]: http://seeker.dice.com/jobsearch/results/US/Cobol-Developer

Rich Hickey, in his talk [*Simple Made Easy*][4], presented a graph of
development speed on a project when following the "easiest" method vs.
designing for simplicity.

[4]: http://www.infoq.com/presentations/Simple-Made-Easy

![](/media/images/posts/2012-03-30-what-can-the-ipad-teach-us-about-software-engineering/easy-vs-simple.png)

Now, this graph is completely made up, but it represents his experience, and it
seems not uncommon for others to agree with it.

Where does this leave us?  We have to take our engineering lessons with a bit
of skepticism - will this actually work for *us*?

And for chrissake, don't [glue your programs together][5].

<object data="http://www.youtube.com/v/BgjeCn901Iw?version=3&hl=en_US"
type="application/x-shockwave-flash" width="650" height="409"></object>

[5]: http://en.wikipedia.org/wiki/Coupling_(computer_science)

