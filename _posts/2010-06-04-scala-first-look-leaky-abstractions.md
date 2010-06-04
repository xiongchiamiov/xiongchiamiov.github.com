---
layout: default
title: Scala First Look - Leaky Abstractions
---

I just received a copy of [Programming in Scala] and am working my way through
it (slowly). There were a few things that struck me as odd to start with, but
the authors explain that they are a result of everything being extensible (in
the sense that standard operators are just predefined methods). Then, I came to
non-scalar datatypes.

	val array = Array("zero", "one", "two")
	println(array(0))
	
	val list = List("zero", "one", "two")
	println(list(0))
	
	val tuple = ("zero", "one", "two")
	println(tuple._1)

Wait, what?

Apparently someone else had the same reaction as me, as the section about tuples
ends with an explanatory infobox:

> You may be wondering why you can't access the elements of a tuple like the
> elements of a list, for example, with "pair(0)". The reason is that a list's
> `apply` method always returns the same type, but each element of a tuple may
> be a different type: `_1` can have one result type, `_2` another, and so on.
> These `_N` numbers are one-based, instead of zero-based, because starting with
> `1` is a tradition set by other languages with statically typed tuples, such
> as Haskell and ML.

Truth be told, I didn't even notice the 1-based indexing until I read this,
since I was so distracted by the incredible break in syntax conventions, and I
really dislike 1-based indexes.

This is one of the worst leaky abstractions I've seen in a while. The underlying
system doesn't allow the expected behavior, so I as a Scala programmer am thrown
off and confused by this seemingly unexplainable change. This is exactly the
kind of thing that [Matz] is referring to when he states that Ruby follows the
[Principle of Least Astonishment].


[Programming in Scala]: http://www.amazon.com/Programming-Scala-Comprehensive-Step-step/dp/0981531601/ref=sr_1_1?ie=UTF8&s=books&qid=1275683858&sr=8-1
[Matz]: http://en.wikipedia.org/wiki/Yukihiro_Matsumoto
[Principle of Least Astonishment]: http://en.wikipedia.org/wiki/Principle_of_least_astonishment
