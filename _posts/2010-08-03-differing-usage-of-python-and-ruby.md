---
layout: with-comments
title: Differing Usage of Python and Ruby
---

I love using Ruby for quick one-off scripts that don't even deserve to be placed
in a file. For instance, I did something rather stupid the other night (deleted
all the .specification files of my installed RubyGems), and, while my gems all
still worked fine, `gem` has no idea they existed, which is a Bad Thing.

Anyways, I wanted to reinstall all of my gems:

	┌─[pearson@Bragi] - [~] - [Tue Aug 03, 01:42]
	└─[$]> ls /usr/lib/ruby/gems/1.9.1/gems 
	addressable-2.1.2            do_sqlite3-0.10.2   linecache19-0.5.11  ruby_core_source-0.1.4
	ansi-1.2.2                   erasmus-0.0.3       liquid-2.1.2        ruby-debug19-0.11.6
	api_cache-0.2.0              extlib-0.9.15       maruku-0.6.0        ruby-debug-base19-0.11.23
	archive-tar-minitar-0.5.2    facets-2.8.4        mechanize-1.0.0     rubyforge-2.0.4
	bluecloth-2.0.7              fast-stemmer-1.0.0  mg-0.0.8            rubygems-update-1.3.7
	bson-1.0.4                   gemcutter-0.6.1     mime-types-1.16     ruby-prof-0.7.3
	builder-2.1.2                gherkin-2.1.5       mongo-0.18.3        ruby-prof-0.8.2
	cheat-1.3.0                  gherkin-2.2.0       mongo-1.0.6         showoff-0.2.4
	classifier-1.3.3             gist-1.2.1          mongo_ext-0.18.3    sinatra-1.0
	columnize-0.3.1              git-1.2.5           mongo_ext-0.19.3    stemmer-1.0.1
	compass-0.10.3               gli-1.1.1           net-scp-1.0.2       syntax-1.0.0
	contest-0.1.2                haml-3.0.15         net-ssh-2.0.23      term-ansicolor-1.0.5
	crack-0.1.8                  hoe-2.6.1           nokogiri-1.4.3.1    test-unit-2.1.1
	cucumber-0.8.5               httparty-0.6.1      octopi-0.2.8        thor-0.14.0
	curb-0.7.7.1                 hub-0.0.0           open4-1.0.1         thoughtbot-shoulda-2.11.1
	data_objects-0.10.2          jekyll-0.6.2        polyglot-0.3.1      ticgit-0.3.6
	diff-lcs-1.1.2               jeweler-1.4.0       rack-1.2.1          ticgit-2010.02.08
	directory_watcher-1.3.2      json-1.4.3          rake-0.8.7          treetop-1.4.8
	dm-aggregates-0.10.2         json_pure-1.2.0     rdiscount-1.6.5     trollop-1.16.2
	dm-aggregates-1.0.0          json_pure-1.4.3     rdoc-2.5.9          turn-0.7.0
	dm-core-0.10.2               light_mongo-0.4.0   RedCloth-4.2.3      xml-simple-1.0.12
	dm-core-1.0.0                limgur-2.0.0        repl-1.0.0          yard-0.5.8
	dm-mongo-adapter-0.2.0.pre3  linecache-0.43      rest-client-1.6.0

While I probably could have done this with sed, Ruby's a bit more familiar to
me, and allows me to play around in `irb` to make sure I've got things right.

	sudo gem install $(ruby -e 'Dir.entries("/usr/lib/ruby/gems/1.9.1/gems").map {|d| d[/[A-z-]+/]}.map {|d| d.chop if !d.nil?}.each {|d| puts d}')
	sudo gem install do_sqlite3 linecache19 open4 ruby-debug19 ruby-debug-base19

and that was it.  Awesome.

The same thing in Python would've been something like

	import os
	import re
	files = os.listdir("/usr/lib/ruby/gems/1.9.1/gems")
	files = [re.match(r"([A-z-]+)", file).group()[:-1] for file in files]
	for file in files:
		print file

or, in one-line style:

	python -c 'import os; import re; for file in os.listdir("/usr/lib/ruby/gems/1.9.1/gems"): print re.match(r"([A-z-]+)", file).group()[:-1]'

...except for the fact that I apparently can't put `for` statements on one line
if they're after anything else.

Anyways, I prefer Python (over Ruby) for any program that has me working with
another programmer, either directly or through a (small) library. You see,
Python has wonderful things like docstrings and `help()`, as well as a community
that values documentation so much they actually write it. Write documentation?
Willingly?  Crazy, I know, but it really spoils you.

With Ruby, you often end up with some API documentation thrown up, and that's
about it. Even [the Ruby core docs] (which are pretty good) have nothing on [the
Python equivalent]. And hell, the Python module for regular expressions not only
has [a rather long section] detailing the meaning of various characters in
regexes, but has a link to [a full-fledged regex guide]. This kind of
documentation fanaticism trickles down to the one-man libraries in a way that
makes me not cringe when having to learn how to call someone else's code in a
way that it does what I want.

[the Ruby core docs]: http://ruby-doc.org/core/classes/String.html
[the Python equivalent]: http://docs.python.org/library/string.html
[a rather long section]: http://docs.python.org/library/re.html#regular-expression-syntax
[a full-fledged regex guide]: http://docs.python.org/howto/regex.html#regex-howto

So yeah, when it comes to writing things by myself, I love Ruby. But sometimes,
[the values] I share with the Python community makes it worth putting up with
crap like [len].

[the values]: http://www.python.org/dev/peps/pep-0020/
[len]: http://effbot.org/pyfaq/why-does-python-use-methods-for-some-functionality-e-g-list-index-but-functions-for-other-e-g-len-list.htm
