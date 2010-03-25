---
layout: default
title: Basic Theory - A Proper Introduction to Web Design
---

<span class="nav">&laquo;[Previous] &sect; [Next]&raquo;</span>

First, we need to have a very, *very* basic understanding of what exactly is
happening when you visit a web page. Either by clicking a link or typing the
address directly into your browser's address bar, you send a request for a
certain <defn>URI</defn> to a webserver. The server interprets this address and
sends back some data that your browser can understand. For our purposes, this
will generally be <defn>HTML</defn>, although there will also be images, CSS,
and Javascript.

Since we will be writing HTML directly (rather than writing programs that
generate it), there's no need for special web server software; you can do all of
this on your home machine with minimal setup.

<dl>
	<dt>URI</dt>
	<dd>
		Uniform Resource Locator. An address we use to identify a location.<br />
		Example: http://changedmy.name/articles/ .
	</dd>
</dl>

<dl>
	<dt>HTML</dt>
	<dd>
		HyperText Markup Language. The primary type of code we use to design
		webpages.
	</dd>
</dl>

HTML (and the other things I mentioned, as well) is interpreted by the browser
to create what you view and interact with. This leads to one of the most
important issues in web design - your code will look different to different
people.

Traditionally, compilers and interpreters (roughly speaking, the programs that
turn your code into something we can use) have been rather strict about what
they will accept as input, leading to much frustration on the part of beginner
programmers. During the browser wars of the 90s, then, the makers of the two
most popular browsers began to insert code into their products that would
attempt to "figure out" what programmers meant when encountering mistakes in the
code, in the hope that, as more and more incorrectly-coded websites appeared,
users would choose the browser that appeared to work more often. While Microsoft
won that war, we are still dealing with the after effects, one of which is that
the webpage you can spent many hours painstakingly crafting may look completely
broken when viewed by someone else.  Yay!

Also, since we are guaranteed a small number of fonts from machine to machine,
and screen resolutions vary from large-screen televisions to cellphones, we have
to build incredibly flexible designs. This is actually good, because it forces
us to focus on the user, someone we often have a tendency to forget.

So, if you're still feeling up to the challenge, let us begin!

<span class="nav">&laquo;[Previous] &sect; [Next]&raquo;</span>

[Previous]: intro.html
[Next]: setup.html
