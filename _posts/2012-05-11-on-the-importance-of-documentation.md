---
layout: with-comments
title: On the Importance of Documentation
---

It's your first day at Boppin' Burgers.

After changing into your uniform and shaking hands with your fellow employees,
you're sent off by Bill, your manager, to go do some work.  "Don't worry,", he
says.  "Here's an order we just finished.  Just make 'em like this.".

You look at the burger: slightly toasted bun, pattie slightly off-center,
cheese dripping over the edge.  You're practically hopping with the excitement
of creating these delicious meals for so many people.

At first, things go smoothly - a few orders are placed and you slap burgers
onto buns.  But then a customer complains that their burger didn't have pickles
on it.  *Pickles?  I didn't know we were supposed to put pickles on a #2.*
"Oh, we didn't put any on that one we gave you at the beginning because the
customer requested no pickles." explains Carl, the coworker you've been told to
ask any questions of.

Periodically, you get a request for chopped (rather than sliced) onions.
Dutifully you grab a knife and chop the onion slices into small pieces before
depositing them onto the burger.  After doing this several times, Carl notices
and stops you.  "We get that request often enough that we keep a jar of
pre-chopped onions over here." he says, grabbing the jar from a cupboard.  You
stealthily dispose of the bowl you had been putting extra chopped onion in.

Four months later, Diana joins the Boppin' Burgers band.  When she asks for
your feedback on her first burger, you nod approvingly and slide the pattie
off-center a tad.  "Why do we need to do that?" Diana asks.  "I don't know."
you respond, shrugging.  "It's just how we do things around here."

---

All of these problems could be fixed by perfect communication - if you were
live-blogging every detail of your work and Carl was reading it, he would've
pointed you towards the onion jar the first time you needed it.  However, most
companies are not staffed by Borg drones, which is why we created [Dozuki] -
Carl can spend a little bit of paid time writing out all the steps of creating
a burger, and then new employees need only follow the step-by-step directions.

But internal documentation is just as vitally important for software companies
as it is for those in the foodservice or manufacturing industries.  The primary
problem with using live code as documentation is that no live code is an ideal
example - it won't use every option that exists, and it'll have special-case
behavior that only makes sense in its specific context.  More importantly,
these things are usually not self-evident - you don't know that you need to be
asking questions, or what questions to be asking.

Just as an example burger created for a customer is inferior to burger-making
instructions, learning how to use a library by looking at its use in an
application will lead to incorrect assumptions and imperfect knowledge that
documentation could prevent.  Application examples illustrate a partial set of
options, often without adequate descriptions of the reasoning for those options
or the behavior of their interactions with each other; good documentation shows
off *all* options, one at a time, with detailed reasoning for their use.

Yes, documentation requires upkeep, but so does code - if you don't want to do
any maintenance, don't change anything.  In most environments, the work put
into writing documentation will be vastly less than what you gain - why do you
think software vendors have Frequently Asked Questions lists?

If you're looking to reduce training overhead, eliminate bugs, improve code
cohesion, avoid reinventing the wheel - give documentation a try.  You just
might get addicted.

[Dozuki]: http://dozuki.com

