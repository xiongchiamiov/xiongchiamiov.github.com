---
layout: with-comments
title: A Software Maintenance Course
---

I love [my department]. I really do. I hear complaints from students elsewhere
about having mostly theory-only classes, feeling like they're receiving a Java
certification, not touching on functional languages, not doing any team
projects, not learning about version control, and I can proudly say that we do
not have those issues.

Now, it's not perfect, certainly. But, I have much hope that it will continue to
improve.

This year, a new course has been added in front of 101, denoted by the course
number 123. The actual implementation differs depending on the professor, but
the important thing is that students are now being introduced to programming
through tools that make it easy to make cool stuff, rather than looping through
C arrays (woo!).

I was one of many people who whined and complained about the way things were,
and am now convinced that maybe, just maybe, someone will listen to me once
again if I leave my shadowy lurking place.

So, here it is:

> We need a course for undergraduate students that teaches software maintenance.

Sounds like a blast, doesn't it?

## Most software development is maintenance.

I believe this. Anecdotally, my (rather limited) job experience has been
primarily modifying code other people wrote, rather than making shiny new
systems. [Some studies] have been done to support this, too; the ones in the
link there are all rather old, though, so I'd be interested in seeing some new
information.

Anyways, while the university should not be merely training students to be nice
employment-ready drones, it should be giving them the tools to succeed in the
rest of their career, and maintenance looks to be a significant portion of their
future.

## Working with someone else's old code helps you write better new code.

I believe this, too (oh, I see! You write down the points that you *believe*!).
People generally say that reading code makes you a better programmer (references
forthcoming), and it sure as hell helps if it's not your own code. 'Cause then
it's like, cheating, y'know. You don't get better at writing by only reading
your own books.

But yes, having to modify code that is foreign to you teaches you what things
are important to code comprehension, and what aren't. In the words of Zed Shaw,
you should avoid [coding like an asshole].

> I find that good people tend to write good, compasionate code, and assholes
> write total asshole code. Their code beats you over the head with their
> nerd-cock. Everything is clever. There's no consistent style, or if there is
> it's the style of someone who doesn't care if you can read it. It's all about
> them, not you, and that makes them an asshole.
>
> ...
>
> You see, assholes don't care whether other people can read their code. What
> they love is if you have to struggle to read their pieces of dense idiotic
> shit. To them, punctuation, style, indentation, spacing, or comments are just
> not necessary. You have to be able to read it the way they wrote it and fuck
> you if you can't. They're going to be different whether that helps you or not
> because goddammit, that's what they fucking want to do and fuck you if you
> complain.

In school, the majority of our projects are 10-week one-offs. You get an
assignment, hack on it for a bit, then turn it in and toss it in the trash right
when the whole thing is starting to fall apart.

A few quarters ago I worked on [a project] for my AI course. It was in C++. I
had never programmed in C++ before, nor did I receive any instruction other than
"oh, it's like C, but with classes" from the "C++ expert" on our team. Now,
don't get me wrong - they're great guys. But this project was showing just how
badly it needed to be re-architected and re-written because none of us knew what
the hell we were doing, but we turned it in and went on with our merry little
lives.

When people don't have to clean up messes, they don't learn to avoid making them
in the first place. A friend of mine is on a team that had a heated debate about
choice of implementation language. While the new and upcoming language some
members wanted to use is, well, new and upcoming, it's lacking in tools,
documentation, and most importantly, well-developed libraries. I've used
libraries that someone hacked out in a weekend and stuck up on GitHub - and
ended up having to maintain them myself or remove the use of them in my project.
But these people don't know better, and don't really care, either. So, inflict
pain upon them and perhaps they'll learn to be a bit more compassionate.

## So, how do we do it?

An excellent question, my friends, and one I had no answer to when I started
writing this page.

A little Googling led me to [a paper] describing a course at the University of
Western Ontario, apparently given in late 1999 or early 2000. Unfortunately,
most anything else is either [as old as me and much too long to read][0],
[talking about a class without a practical project][1], or [behind irritating
paywalls][2]. Pah.

Basically, I see our course being something like the SE Capstone series, albeit
not as long or tied up in requirements documents and nonsense. After students
are in teams (either of their own choosing or the professor's), present them
with a number of potential projects, both things that companies want done and
needy open-source projects. Let the teams choose on what they wish to work and
let them loose.

The thing that bothers me most about this design is that it tends towards large
modifications. In my (again, very limited) experience, most of my work has been
to do a little this and a little that, jumping around the codebase like
caffeinated double dutch champion. The majority of open-source projects are like
that, too; newcomers take ownership of something from the issue tracker and hack
it out, then move on to the next.

This sort of approach to coursework seems anatagonistic to grading, however, and
I've been assured that our classes need to be graded, not merely educational.
So, I suppose we stick with Approach #1, unless any of you have a genius idea.

So that's it, my grand plan. If this finds its way to you (I'll assume it did
since you're reading this), leave me a comment below with any thoughts you have,
or, if you feel like it, come find me on campus somewhere and chat for a bit. I
love chatting about this sort of thing.


[my department]: http://www.csc.calpoly.edu/
[Some studies]: http://www.stsc.hill.af.mil/crosstalk/1997/07/maintenance.asp
[coding like an asshole]: http://oppugn.us/posts/1276150607.html
[a project]: https://github.com/xiongchiamiov/virus-td
[a paper]: http://docs.google.com/viewer?url=http://reversingproject.info/wp-content/uploads/2009/05/experiences_with_a_software_maintenance_project_course.pdf
[0]: http://docs.google.com/viewer?url=http://www.sei.cmu.edu/reports/89em001.pdf
[1]: http://www.cis.udel.edu/~pollock/879.testing/syllabus.html
[2]: http://www.computer.org/portal/web/csdl/doi/10.1109/SEDC.1997.592440
