---
layout: with-comments
title: Why Python's Modules Are Badass
---

I like learning new languages. While I may not agree with all of the designers'
decisions, every non-[esoteric] language provides things to learn from.

One of my favorite things about Python is its approach to modules and
namespaces.

[esoteric]: http://en.wikipedia.org/wiki/Esoteric_programming_language

# Creating a module is easy

In the simplist cases, nothing special is needed. Want to use a class `Foo`
defined in `awesome.py`? Just `from awesome import Foo` and you can utilize
`Foo` in your code.

Adding directories doesn't complicate your life much; create an empty file named
`__init__.py` in a directory and you've got a module. For instance, given this
directory structure

	my_program.py
	lib/__init__.py
	lib/awesome.py

and building upon the previous definitions, `my_program.py` can use the statement `from lib.awesome import Foo` to make our
`Foo` class available.

# Explicitness leads to maintainability

Here's a common situation in older PHP code:

	require('user.php');
	require('authenticate.php');
	require('util.php');
	
	if (logged_in()) { // Where is logged_in() defined?

Code navigation features or search tools can alleviate the irritation this
causes, but it's a solved problem! In Python, you're likely to see something
like

	from user import User
	from authenticate import logged_in, login
	from util import time_since_login
	
	if logged_in(): // logged_in is defined in authenticate.py

# 'As' promotes flexibility

Python allows you to import modules under different names. Say you're developing
some application that uses the `cpickle` module.

	import cpickle
	
	data = cpickle.load('file.pickle')

In an effort to make your application more "enterprisey", your boss orders it
moved over to the JVM, using Jython. But alas! `cpython` is a module written in
C, and therefore not available on Jython. Do not fear - one line changed
switches your program over to the pure-Python `pickle` module:

	import pickle as cpickle
	
	data = cpickle.load('file.pickle')

# Notes and technicalities

If you want to clobber your namespace with everything defined in a module, you
can use the `from foo import *` syntax. This is commonly done when working with
GUI toolkits, but you're liable to get lynched if you use this syntax more than
once in a file.

Any code in `__init__.py` is run when a module is imported. I've seen this used
to provide a succinct API for users while retaining code separation for the
developers, like so:

	# __init__.py
	from foo import Foo
	from bar import Bar

The way a language like Lua would change the name of an imported "module" is to
change the assignment operation:

	pickle = require('cpickle')

You can do something similar in Python, too, but it's more direct to just use `as`.

Also, Python being Python, you can modify the `globals()` and `locals()` dictionaries
if you really want to (and occasionally there's reason to). So, things can
easily be introduced into your namespace through other methods, although they
usually aren't.
