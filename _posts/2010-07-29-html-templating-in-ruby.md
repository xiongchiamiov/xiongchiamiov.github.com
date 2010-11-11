---
layout: with-comments
title: HTML Templating in Ruby
---

(or "Why I moved a project to Python")

I have [a relatively simple project][funi-license-mirror] that requires me to
scrape off a few paragraphs from a website, then print 'em out in a nice HTML
page.  Well, right now it's not so nice:

![](http://imgur.com/JhQRU.png)

which is why I decided to make an actual full-fledged HTML page, with `<body>`
tags and everything!

Since I didn't really want to output HTML directly from Ruby, I went looking for
a nice, simple HTML templating system.

First up was [mustache]. It was a nice and simple `Mustache.render
IO.read("funi.html"), :entries => entries` until I remembered that Mustache
doesn't allow *any* logic in templates, which meant that I couldn't iterate over
my entries in a loop and do whatever to them.  Out.

Second was [haml]. I got my template all coverted over, and then plugged in a
line similar to what I was using in another project: `puts haml :index, :entries
=> entries`.  `NameError`?  Huh?

So, it appears that the [Sinatra] folks added a `haml` method. That's fine, I
can just call haml programmatically, and... what the hell is this? How do I
freakin' call haml?

You see, all of the haml documentation covers how to write templates in haml,
with none of it describing how to actually render the damn things. Any docs I
could find on that were Rails-specific, which is utterly unhelpful for a script
like this. I spent a while digging through the haml source before giving up in
frustration. Seriously, guys. No.

Ah, [liquid], my Smarty-like friend. Put the template back to HTML and through
in a `puts Liquid::Template.parse(IO.read "funi.html").render('entries' =>
entries)`, and we're good to go.

`Liquid error: undefined method 'to_liquid' for #<Nokogiri::XML::NodeSet:0x9baf0c0>`?
But I'm not printing out anything from a `NodeSet`; I throw it into a loop, and
make the appropriate calls to get a string for you to digest. Oh, that's right -
now I remember why I gave up on you on another project.

You see, liquid bills itself as being a "secure" templating system, which means
that it's fucking annoying to use.  You end up with shit like this:

	# a bunch of bullshit liquid requires
	module Nokogiri
		module XML
			class NodeSet
				def to_liquid
					self
				end
			end
			class Element
				def to_liquid
					self
				end
			end
		end
	end

just so you can use freakin' `NodeSet`s in your template. I'm not taking any of
that.

Well, let's see if [the ruby toolbox] has anything else interesting. Hmm,
there's [erector]:

	require 'erector'
	
	class Hello < Erector::Widget
		def content
			html do
				head do
					title "Hello"
				end
				body do
					text "Hello, "
					b @target, :class => 'big'
					text "!"
				end
			end
		end
	end
	
	Hello.new(:target => 'world').to_html

Lol no.

So yeah, I got fed up with this nonsense and ported over to Python so that I
could use [Jinja], which is a shame, because I really like [Nokogiri]. But hey,
do what works, right?

(As a side note, one of the reasons I like Nokogiri is that it has actual
documentation, rather than just API docs slapped up, like most Ruby projects.
The Python community tends to treat documentation very seriously (while Rubyists
feel the same vigor towards unit tests), which makes it rather difficult to use
anything that's not well-documented after having programmed in Python for a bit.
That was one of my main problems with Android (and Rails, a few years ago), and
it's gotten to the point that I almost automatically dismiss any framework or
library that doesn't have pages of well-written documentation.)


[funi-license-mirror]: http://github.com/xiongchiamiov/funimation-license-mirror
[mustache]: http://mustache.github.com/
[haml]: http://haml-lang.com/
[Sinatra]: http://www.sinatrarb.com/
[liquid]: http://www.liquidmarkup.org/
[the ruby toolbox]: http://ruby-toolbox.com/categories/template_languages.html
[erector]: http://erector.rubyforge.org/
[Jinja]: http://jinja.pocoo.org/2/
[Nokogiri]: http://nokogiri.org/
