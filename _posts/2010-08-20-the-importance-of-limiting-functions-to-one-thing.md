---
layout: default
title: The Importance of Limiting Functions to One Thing
---

One of the reasons I love dynamically-typed languages is that they tend to allow
a programmer to use old unmaintained code in ways the original author didn't
anticipate. This is especially important if you're trying to interface with a
library that the user will likely already have installed previously, so you'd
rather not vendorize it (include it in your source directly).

Using a dynamically-typed language doesn't automagically preclude you from this
problem, however; there are still a number anti-patterns that will lead to
curses called down upon your name some unspecified time in the future.

I recently came across some code in the following form:

	<div id="foo"><?php echo thingies_table('foo') ?></div>
	<div id="bar"><?php echo thingies_table('bar') ?></div>
	<div id="baz"><?php echo thingies_table('baz') ?></div>
	
	[snip]
	
	function thingies_table(parameter) {
		[get a list of thingies from the database]
		[do some stuff to the list]
		
		return build_table(thingies);
	}

Now, this isn't nearly as bad as the more common version:

	<div id="foo"><?php thingies_table('foo') ?></div>
	<div id="bar"><?php thingies_table('bar') ?></div>
	<div id="baz"><?php thingies_table('baz') ?></div>
	
	[snip]
	
	function thingies_table(parameter) {
		[get a list of thingies from the database]
		[do some stuff to the list]
		
		print build_table(thingies);
	}

but it's still not good.

You see, I wanted to combine the results of several `thingies_table`s into one,
something like

	<div id="foo-bar-baz">
		<?php
		$foo = thingies_table('foo');
		$bar = thingies_table('bar');
		$baz = thingies_table('baz');
		print build_table(array_merge($foo, $bar, $baz));
		?>
	</div>

This, however, isn't possible with `build_table` inside `thingies_table`, which
is why it should be pulled out, either into another function or the `<div>` code
itself.

Be considerate to your successor and limit each function to only doing one
thing.
