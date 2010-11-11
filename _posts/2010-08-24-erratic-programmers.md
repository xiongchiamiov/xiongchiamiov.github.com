---
layout: with-comments
title: Erratic Programmers
---

I am an erratic programmer. I flit around from project to project, never staying
long, even if I end up contributing for a long time overall.

This is why I love GitHub, git, and Ruby.

When I have an idea for a project, I can't be arsed to set up Subversion; `git
init` is all I need to start keeping revisions. After I've done a bit of
hacking, I need to be able to throw it up somewhere more safe than my computer
while minutes away from sleep.  For GitHub, that looks something like this:

1. Go to GitHub.com.
2. Click "New Repository".
3. Enter some half-arsed name and click "Create Repository".
4. Copy a line and paste it into my terminal.
5. `git push origin master`
6. `sudo shutdown -hP now`

I don't have time to deal with [Sourceforge's approval process]. I don't need to
worry about [Google Code's project cap]. Seriously, 25 projects? I'm up to 59 on
GitHub right now, with my 2nd year's anniversary around the corner.

[Sourceforge's approval process]: http://sourceforge.net/apps/trac/sourceforge/wiki/Get%20started%20with%20your%20new%20project
[Google Code's project cap]: http://code.google.com/p/support/wiki/WhatsNew#Project_creation_limit_raised

I expect my projects to be worked on for a few days, abandoned for a few months,
worked on for a day, abandoned for a month, and so on. GitHub understands this.
I see a potential improvement to someone's project, and I just click "Fork",
"Edit" (oh, simple web-based editing, you are awesome), "Commit", and send a
Pull Request. Whenever the original author gets around to logging in and viewing
his messages, he just has to go to his Fork Queue and pull in my change,
easy-peasy. If either of these processes took more than 3 minutes, we wouldn't
do them.

Let me repeat that for you.

If either creating and submitting a patch for a project or merging in that patch
takes more than 3 minutes, the erratic programmer won't do it. Do not
overestimate our attention span.

This is why easily-modifiable code is important. You hacked up a little script
to do something cool, without extensive testing, a spec, or any of those other
things that generally come with "real software". I go looking for something that
does X, find your script, and love it, except for the fact that it doesn't also
do Y. Golly gee, though, you wrote it in Ruby, so I can monkey-patch the class
to add Y functionality while still allowing people to install your original gem.

I believe there was an ending somewhere, but it's been replaced by some thoughts
about AI programmers. Send me a pull request if you find it.
