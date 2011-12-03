---
layout: with-comments
title: The Relationship Between Static Typing and Dependency Resolution
---

They seem similar, to me.

In a statically-typed language, you specify that whoever's using your code
better give you an `AbstractBullshitFactoryFactory` or else there'll be hell to
pay.  Similarly, a packager for a package manager with dependency resolution
will tell the package manager that dammit, you *need* `cups` installed or else
things just won't work.

Contrast this to a dynamically-typed language (where you're responsible for
whatever you pass in; if it doesn't work, that's your own damn fault) and a
package manager that lets you install whatever package you want, whether or not
it relies upon things you don't have.

Parallels can be drawn between Java's interfaces and package manager's
`provides` clause.

Now, the big difference for me is that [my package manager][Pacman] has a
`--nodeps` option, while I'm not aware of any statically-typed languages that
let me, as a programmer using a library, override type constraints.  Also,
automatic downloading of dependencies makes for significantly less work for me,
while static type checking does no such thing.

[Pacman]: http://www.archlinux.org/pacman/pacman.8.html

