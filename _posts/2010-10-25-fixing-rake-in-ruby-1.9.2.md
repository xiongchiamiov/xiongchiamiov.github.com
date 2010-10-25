---
layout: default
title: Fixing Rake in Ruby 1.9.2
---

When a task in Rake fails, Rake is supposed to simply tell me it failed and then
tell me to use the `--trace` option if I want to know more. However, tonight it
was acting as though I always called it with `--trace`:

	┌─[pearson@Bragi] - [~/temp] - [Sun Oct 24, 11:41]
	└─[$]> cat Rakefile 
	task :foo do
		fail
	end
	┌─[pearson@Bragi] - [~/temp] - [Sun Oct 24, 11:43]
	└─[$]> /usr/bin/rake foo
	(in /home/pearson/temp)
	rake aborted!
	
	/home/pearson/temp/Rakefile:2:in `block in <top (required)>'
	/usr/lib/ruby/1.9.1/rake.rb:634:in `call'
	/usr/lib/ruby/1.9.1/rake.rb:634:in `block in execute'
	/usr/lib/ruby/1.9.1/rake.rb:629:in `each'
	/usr/lib/ruby/1.9.1/rake.rb:629:in `execute'
	/usr/lib/ruby/1.9.1/rake.rb:595:in `block in invoke_with_call_chain'
	/usr/lib/ruby/1.9.1/monitor.rb:201:in `mon_synchronize'
	/usr/lib/ruby/1.9.1/rake.rb:588:in `invoke_with_call_chain'
	/usr/lib/ruby/1.9.1/rake.rb:581:in `invoke'
	/usr/lib/ruby/1.9.1/rake.rb:2041:in `invoke_task'
	/usr/lib/ruby/1.9.1/rake.rb:2019:in `block (2 levels) in top_level'
	/usr/lib/ruby/1.9.1/rake.rb:2019:in `each'
	/usr/lib/ruby/1.9.1/rake.rb:2019:in `block in top_level'
	/usr/lib/ruby/1.9.1/rake.rb:2058:in `standard_exception_handling'
	/usr/lib/ruby/1.9.1/rake.rb:2013:in `top_level'
	/usr/lib/ruby/1.9.1/rake.rb:1992:in `run'
	/usr/bin/rake:31:in `<main>'

I tried doing the reverse of the [make-Rake-always-trace trick][0], but that
didn't seem to have any effect.

I thought about digging through Rake's source to see what was happening, but
that was far more work than I wanted to do, and *could* do at this point in
time.

So, instead, I had a full write-up to StackOverflow, and moments from posting,
noticed that the include path was using 1.9.1, even though I had Ruby 1.9.2
installed. Then I remembered that Ruby 1.9.2 did some weird stuff with gems.

Eventually, I tried re-installing rake, from gem, rather than the version
included in 1.9.2.  This lead me to a different error:

	┌─[pearson@Bragi] - [~/temp] - [Sun Oct 24, 11:58]
	└─[$]> rake foo
	/usr/lib/ruby/1.9.1/rubygems.rb:340:in `bin_path': can't find executable rake for rake-0.8.7 (Gem::Exception)
		from /usr/bin/rake:19:in `<main>'

and then [the terrifying advice] from J. Random Blogger:

> Apparently 1.9.2 comes with a version of rake internally, but is unable to
> find it for some reason relating to the rake.gemspec file. Remove the file to
> fix this issue.

And you know what? It fixed it. I kept a backup just in case, but damn, that's
sketchy. Ruby on my system is starting to feel like the CPAN mess I have to deal
with at work - it's gotten to the point that anytime I touch something vaguely
related to Perl in yum, our software breaks, and I spend several hours in
quality time with the CPAN shell downgrading and reinstalling packages.


[0]: http://stackoverflow.com/questions/3002670/how-can-i-make-ruby-rake-display-the-full-backtrace-on-uncaught-exception
[the terrifying advice]: http://www.prestonlee.com/2010/09/24/upgrading-from-ruby-1-9-1-to-ruby-1-9-2/
