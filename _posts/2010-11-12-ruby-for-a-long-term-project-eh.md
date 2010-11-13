---
layout: with-comments
title: Ruby for a long-term project? Eh...
---

The other night, my housemate and I were discussing language choices for a
project, and he mentioned Ruby.  I surprised him by stating,

> I wouldn't let you start a team project in Ruby.

People who have talked with me might find this a bit strange. I love Ruby, use
it in quite a few of my projects, and will tell anyone who listens about how
Ruby takes the best parts of several different languages and combines them into
something that's just *fun*.

But while it's an amazing language to write one-off scripts that I don't expect
anyone other than me to hack on, there are some serious flaws that prevent me
from recommending it for anything meant to live for a while.

## Matz doesn't understand version numbers

Seriously. People shouldn't be stuck on 1.8 because trying to run things on 1.9
breaks them. Upgrading from 1.9.0 to 1.9.2 shouldn't [break the primary build
tool]. Redmine shouldn't [require] very specific versions of Ruby and Rails to
work.  We have this thing called [Semantic Versioning], y'know.

[break the primary build tool]: /2010/10/25/fixing-rake-in-ruby-1.9.2.html
[require]: http://www.redmine.org/wiki/redmine/RedmineInstall
[Semantic Versioning]: http://semver.org/

## The gem ecosystem is becoming CPAN

Five different modules that all do what you want, but in an incredibly buggy and
not quite correct way? And they haven't been updated in 5 years? Yeah...

## Ruby == Rails ?

It's damned difficult to find a good Ruby RSS feed that doesn't spend (at least)
half its time talking about Rails. I use Ruby. I don't use Rails. This seems
incomprehensible to some people.

## Rails is a buzzword

Rails has done great things. I may disagree with it philosophically on some
things, but no one can deny that it has brought a new focus on
programmer-friendly frameworks for the web.

However, it became very hyped and buzzwordy, which normally is followed by a
rush of not-particularly-skilled programmers wanting to Do Cool Stuff Now. You
then end up with a particularly bottom-heavy triangle of people in the
community, usually with a proportionate amount and quality of code. That's what
prompted [Zed's famous rant].

[Zed's famous rant]: http://web.archive.org/web/20080103072111/http://www.zedshaw.com/rants/rails_is_a_ghetto.html

## Explicitness is not the name of the game

Okay, this is more of a reason to use Python than a reason not to use Ruby. But
in a Python project, if someone uses a function or class, I can take a look at
where it was imported from (unless they did a `from foo import *`, which is
almost always a Bad Thing), then just follow the path directly to a file, since
module names are based directly on directory and file names. Ruby provides more
flexibility in that you can define any module in any file, and even reopen
modules to monkeypatch things in. While this additional flexibility could be
useful in certain circumstances, it generally means I have to spend more time
searching around for the defining code. It also means you can't do cool stuff
like iPython's `foo??`, which shows the code for `foo`. Between that and
docstrings, you're set to explore unknown code while in the [REPL].

Similar deal with lack of keyword arguments.

[REPL]: http://en.wikipedia.org/wiki/REPL

Now, could these things be fixed? Theoretically yes, but I think that you have
to have the right mindset to start off with to avoid a huge uphill battle. And
really, if Matz hasn't made a commitment to version stability by now, then it's
indicative of a lack of care in that department, which doesn't bode well for the
future.

Ruby is my 10-year old son - he's a blast to play cops and robbers with and take
caving, but I'm sure as hell not putting him in charge of the household
finances.
