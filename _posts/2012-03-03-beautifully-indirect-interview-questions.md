---
layout: with-comments
title: Beautifully Indirect Interview Questions
---

As I'm graduating soon, I've been interviewing with a number of companies.  One
of them had a wonderful way of getting to know my opinion on testing without
asking me directly.  After all, if asked "Do you think testing is important?",
pretty much everyone will say yes.  In practice, though, we see that most code
ends up with a distinct lack of tests.

In my case, I can see the benefits of testing, but the codebases I've worked
with have had, at best, extremely sparse tests on the unit level.  Several have
been at the point where tests are rather difficult to write, since any
functions that do exist are hundreds of lines long and do many, many things all
mixed together.

I'm a pragmatic person - I write unit tests when they save me time (for
instance, in a log parser with a number of different variations on the format).
Most of the time, "good enough" testing can be done much quicker by hand, and
any important issues are caught by higher-level Selenium tests.

Now, having full test coverage gives you a rather nice benefit - you can deploy
at any time with confidence.  This benefit, however, disappears when your test
coverage dips below 100% - then you still need to go around testing things to
make sure shit ain't broke.  I've never had the opportunity to work on a
project like that, so I'm not test-driven; the reason I stress documentation so
much is because I've used both projects with excellent documentation (Django)
and those with absolutely none (\*cough\*).

But I digress.

## The Questions ##

> You're a consultant who has just come in to a company.  How do you get a
> rough feel for their code quality?

I mentioned first that I'd look through their VCS logs, mostly because I really
like VCSs, but also because you can get a good rough feel for how many bugfixes
vs. hotfixes vs. features are happening.  After that, though, I'd pick a
function on the site and try to follow the code that handles that action.
Since this is generally how I've worked ("X is broken; fix it."), it's
understandable that this is what I'm most interested in.

As a sidenote, this is also why I like the explicitness of, say, Django's URL
mapping - I go through the list of regexes until I find one that matches the
URL, then I look at the function that's listed.  This is beautiful when you
don't know where to look in a large project and you don't want to waste time
guessing and searching.

Of course, the answer the interviewer was looking for was that I'd look for
test coverage.

> You said you've been using Product X; what would you improve about it?

Product X has no tests.  The answer is to add tests.  I didn't even know it
didn't have tests (I don't expect an open-source project to have them), so I
talked instead about something that's more important to the sysadmin part of
me.

> I was looking at [lastfm-tail] on your GitHub.

We talked a little about it, and I said I was pretty satisfied; it's likely I
won't make any more changes.

This short little script has no tests.  I don't plan on writing any tests for
it, since it's far easier to just run it, and since I use it on a daily basis,
I'm likely to find any bugs that I'd think to test for.

[lastfm-tail]: https://github.com/xiongchiamiov/lastfm-tail

## And The Lesson For Today Is... ###

It wasn't until after the interviews that I noticed what these questions were
driving at.  This is excellent.

There are a lot of good things to do as a programmer.  Unfortunately, you can't
do them all, so you have to prioritize them.  Similarly, a company needs to
have priorities.  One of the reasons for an interview process is to try and see
how well the two match up.

Notice that these questions don't have right answers.  I mean, there are
answers that you're looking for, but a candidate will just see them as being a
matter of opinion, which they're more likely to give freely than in a situation
where they feel you're looking for a particular thing.

