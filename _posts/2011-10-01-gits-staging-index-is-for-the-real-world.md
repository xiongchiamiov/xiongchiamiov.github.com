---
layout: with-comments
title: Git's Staging Index is for the Real World
---

I love git.  One thing I love most about it is [the staging index]:

  > With most other version control systems, there's 2 places to store data:
  > your working copy (the folders/files that you're currently using) and the
  > datastore (where the version control decides how to pack and store your
  > changes). In Git there's a third option: the staging area (or index). It's
  > basically a loading dock where you get to determine what changes get
  > shipped away.

This is a unique idea to git.  There are two primary arguments I've heard
against it:

1. It's needlessly complicated.
2. You should never be checking in a state you haven't tested.

While it's true that you now have an additional step, I hardly think it's a
needless one; this complaint seems to come mostly from Subversion users who are
trying to alias `svn commit` to `git add . && git commit && git pull && git
push`.

The second is quite a valid argument.  It's not generally a good idea to pull
only bits and pieces of what you've tested into your commit; it's the same
result as when you forget to add a file that you created (and your changes rely
upon).  I feel it's quite necessary to allow this, though, because

# I live in the real world. #

I know, it's crazy, but sometimes I have to deal with things that
*theoretically* should never happen if we were *completely* following Foobar
Programming, but the state of the world right now is that it's broken and I
have to fix it and our customers are calling and my boss is asking me why it
isn't done yet and I just **don't** feel this is the right time for a major
refactoring of the system.

Here's a real example: at work, we have a daemon system we wrote to process
queue requests.  On our development machine, the workers source their code from
one checkout of the code.  This means that any developer wanting to test
changes in the queue-processing system has to make changes to that one
directory.  This gets to be a bit annoying when multiple people have to do this
simultaneously.

Now, yes, this needs to be changed.  But I have 60 other tickets on me at the
moment, and I can't get them all done *right now*, so I have to deal with the
situation for a bit longer.  And if I was using Subversion, I'd have to remove
this other person's changes to this file, save the file, commit it, then revert
my removal, whereas right now all I have to do is run `git add -p`.

BTW, I *can* actually test my changes separate from theirs, now: I just have to
run `git stash --keep-index`, run my tests, `git stash pop` and continue on my
way.

Here's another reason I commonly use `git add -p`: differing test and
production environments.  There are a number of debug constants we've got set
to `true` in development, but really, *really* don't want to have that way in
production.  There are also changes that are necessary simply because the
development environment isn't set up completely the same as production.  Should
they be the same?  Sure, but that will require me to rebuild our entire
development infrastructure, and that ain't happening by Tuesday.

tldr: staging index helps me get shit done.

[the staging index]: http://gitready.com/beginner/2009/01/18/the-staging-area.html

