---
layout: with-comments
title: Software Engineering in Systems Administration
---

I am [a Web Operations Engineer][web-ops].  While this encompasses a broad
spectrum of duties, it boils down to ensuring [ifixit.com] spends as little
time in failure states as possible.  Or, to be more colloquial:

> Ensure shit works.

While there are obviously technical problems abounding in such a technical
context, my interest lies more in the *human factors* of failure - an interest
that leads to a rather perverse desire to read books about airplane crashes and
nuclear powerplant meltdowns.

In university, I switched from a computer science degree program to software
engineering.  At the time, this was driven by a desire to skip low-level
hardware courses, but I grew to appreciate my choice for different reasons.
Computer science, I tell incoming students and their parents, is a field
focused on trying to make computers work better; software engineering wants to
make computer scientists work better.

Software engineering is the application of engineering principles to the
mathematically-derived field of computer science.  It turns out that one of the
big beefs engineers have with mathematicians is that the latter tend to ignore
real-world uncertainties.

People are uncertainties.

People are all different.  People get tired.  People misunderstand
instructions.  People have imperfect memories.  People are distracted by an
upcoming birth, an impending divorce, or even just the football game on later
tonight.

People make mistakes, and mistakes lead to failure.

Most sysadmins tend to approach problems from a very technical perspective - a
customer reports that they can't upload images, investigation shows users were
no longer able to successfully upload images because the image processing job
was throwing errors because there was a divide-by-zero error because the height
was zero because a variable name was mistyped.  Fix the typo, image uploads
resume, on to the next task.

I, however, am interested in something further, the **real** root causes of
problems.  Why did the developer not notice this typo?  Why did no one in code
review or quality assurance notice it, either?  Why didn't any of our tools
help them see it before production, and why didn't any of our tools help *me*
see it once it got there?

The problem stemmed from a human mistake - a simple misstep on the keyboard.
Recognizing that humans make mistakes all the time, and building tools to deal
with it, ah, now that's software engineering.

In my university, software engineering was seen as a path for future managers -
you trade a few technical courses for ones that just talk about people.  "Bah!
Computer-science-lite!" they say.

But I contend that anyone making computer programs for people to use must
understand how those people use computers, or doom themselves to failure.  And
after all, aren't humans just the most complex machines on the planet?

Save a life; study humans.

[web-ops]: http://omniti.com/seeds/what-is-web-operations
[ifixit.com]: http://www.ifixit.com

