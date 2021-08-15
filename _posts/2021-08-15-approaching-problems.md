---
layout: with-comments
title: Approaching Problems
---

I've been thinking about post-mortem processes recently, as we've been
expanding the group of people involved in our post-mortems and we need to make
sure they're all prepared on how to make post-mortems effective and blameless.
One of the aspects is making sure we clearly separate identified *problems*
from potential *solutions*; most people tend to jump directly into ways to
prevent the incident from happening again, but that can unintentionally skip
better alternative solutions.  It can also lead to implementing solutions that
don't actually solve the initial problem, but that's a topic for another time.

I have a fairly structured approach to thinking about human error, which is
where almost every incident comes from if you dig deep enough.  I haven't heard
many other people lay things out this way, and I find it a helpful way to
consider the broad spectrum of possibilities, so I am writing it down rather
than relying on a series of ad-hoc conversations.

First off, we should dismiss the blame approach:  X made a mistake, so we
should fire X, or at least tell them not to make a mistake again.  The
so-called "Bad Apple Theory" has been repeatedly disproved; read *The Field
Guide to Understanding Human Error* by Sidney Dekker for detail on this
subject.  And simply "not making mistakes" is hardly better, even if it is a
common approach.  Maliciousness aside, the person involved made the mistake
because their view of the world told them it was the correct thing to do;
otherwise, they wouldn't have done it!  Therefore, we can't ask people to
simply not make mistakes, because they were already only doing things they
thought were correct.  We have to address the *systems* instead, then.

When I worked at reddit, we went had three different CEOs during a year.  One
interesting thing this taught me was how differently people can approach the
same problems.  I like to categorize these into **tooling** and **process**
improvements.

Let's use an illustration.  We're a small company built by a few senior
engineers.  As the company expands, we hire our first new engineer, a junior.
Things are going well until one day the junior engineer pushes a change into
production that breaks the site.

"Never hire anyone ever again", "never hire junior engineers", and "try to fix
the hiring process to only find engineers who don't make mistakes" are all
examples of strategies that are doomed to failure, so let's put those aside.

Tooling solutions are the ones engineers normally think of first.  The strategy
here is generally: improve our software so that it's impossible or difficult to
make mistakes.  The Japanese have a dedicated term for this, [poka-yoke].  Here
we might have our production change tool output the diff of what's going to be
changed in production, or add automated test coverage, or create alerting that
notifies us when we've broken production.

[poka-yoke]: https://en.wikipedia.org/wiki/Poka-yoke

Process solutions instead tackle the human aspect by changing how we work, and
are more natural to non-engineers.  For instance, we can train our new hires on
how the systems work, or have everyone telegraph their intended production
changes so another team member can verify the change makes sense.

Different organizations will be used to tackling problems in different ways.
Maybe we have multiple teams and want each team to only deploy their own
software; do we build a system that restricts their access (a tool), or log the
changes and give a stern talk to anyone who deploys another team's stuff (a
process)?  I find that the approach that works best will depend on the
situation, and so this categorization of potential solutions helps ensure that
we're looking at all of our options and can choose the one that's the fastest,
cheapest, or most effective.
