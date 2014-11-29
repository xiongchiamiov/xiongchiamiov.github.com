This is my blog.  There are many like it, but this one is mine.

## Hacking

To keep things tidy, [Bundler] is used for the Ruby dependencies:

    [$]> bundle install --path env
    [$]> bundle exec jekyll serve

If changing CSS, you'll need to follow a few steps as well:

    [$]> npm install -g grunt-cli
    [$]> cd media/css/ribs
    [$]> npm install
    [$]> grunt watch

[Bundler]: http://bundler.io/

