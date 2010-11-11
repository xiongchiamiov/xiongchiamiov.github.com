---
layout: with-comments
title: Postfix in a Functional Language
---

One of my issues with Scheme was that I found myself having to think ahead and
write backwards. For instance, given these (fairly simple) English instructions:

> Multiply 5 times 5, and 3 times 2, then add them together, and subtract from 5.

you're likely to end up with code something like this:

	(- 5
	  (+ (* 3 2)
	     (* 5 5)))

Backwards, backwards, backwards!

In postfix, however, you get this:

	(((5 5 *)
	  (3 2 *)
	  +)
	  5 -)

or, if you assume only two arguments for each operator,

	5 5 *
	3 2 *
	+
	5 -

which reads more like standard procedural code:

	a = 5 * 5
	b = 3 * 2
	c = a + b
	return 5 - c

(or so).  Easier for me to grok.

[It seems] that there are very few programming languages that use postfix other
than those used primarily for calulators, which is a shame.


[It seems]: http://en.wikipedia.org/wiki/Reverse_Polish_notation#Current_implementations
