---
layout: with-comments
title: Small git Repos are Ok!
---

I love git. Every project I start has begins with a `git init`, and most of them
end up on GitHub, which is why [I have] so many freakin' repos there. Well,
that's not actually all of the reason, although it is a big one. The other two
are that I have a tendency to use git for things [it's not really designed
for][wallpapers], and that I have create new repositories willy-nilly. It's
actually the latter that I want to talk about today.

I often come across people who group lots of unrelated files into one
repository, either because that's how they happen to be on their filesystem, or
they have an adverse reaction to small repositories. I have a feeling that this
is due to prior usage of subversion and the difficulty of creating projects on
[certain project-hosting sites], although I can't be sure. Perhaps due to the
fact that I was introduced to mercurial and git before subversion plays a part
in my differing view.

I am a proud [Arch Linux] user, and as part of that I maintain [a few] fairly
unimportant packages for the Arch User Repository (AUR). Since I always like
being able to see just what changed in pkgbuilds, I version all of mine with git
and host them on GitHub. All of them are single-file repositories. I prefer to
keep them separate, though, for a few reasons:

* If someone wants to take over one of my packages, they can do so without
  getting all of the other crap.
* I can generate nice changelogs.

While the latter can still be done on a per-file basis, pkgbuilds *can* contain
other files (usually patches), and I'd rather not back myself into a corner
unneccesarily.

Summary: more of [this][perl-net-smtp-tls], less of [this][tools], and don't
criticize me for being [a hypocrite][config].


[I have]: http://github.com/xiongchiamiov
[wallpapers]: http://xiongchiamiov/wallpapers
[certain project-hosting sites]: http://sourceforge.net/
[Arch Linux]: http://archlinux.org
[a few]: http://aur.archlinux.org/packages.php?K=xiong.chiamiov&SeB=m
[perl-net-smtp-tls]: http://github.com/xiongchiamiov/AUR--perl-net-smtp-tls
[tools]: http://github.com/taoufix/tools
[config]: http://github.com/xiongchiamiov/config
