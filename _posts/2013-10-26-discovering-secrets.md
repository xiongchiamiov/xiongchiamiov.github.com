---
layout: with-comments
title: Discovering Secrets
---

I use [LastPass] as my password manager of choice.  One of the features
available to LastPass users is [password sharing], and one of the features of
password sharing is the ability to choose whether the sharee will be able to
view the password.

Despite the strong language in the sharing dialog ("password will remain a
secret" vs. "password will be obtainable"), the LastPass help article (which
I'm sure most users will never read) notes at the very bottom that

> Savvy end users could potentially access the password if they capture it
> using advanced techniques during the login process

Savvy end users, eh?  I wondered just what was required to expose a shared,
"secret" password, and decided to experiment.

[LastPass]: https://en.wikipedia.org/wiki/Lastpass
[password sharing]: https://helpdesk.lastpass.com/features/sharing/

# Setup

First, I created a new LastPass account.  This is free, so that was no problem.

Secondly, in my normal LastPass account, I created a new credential, entitled
"testing shared passwords", with a password of "sharedpassword".  I shared this
credential with my test account, with the default visibility option (password
will remain a secret) set.

# Attempt 1: Bypass Edit View

Viewing the credential through the LastPass website didn't provide very much:

![](/media/images/posts/2013-10-26-discovering-secrets/01.png)

so I logged in to the Chrome plugin, which provides a much more useful "edit"
view:

![](/media/images/posts/2013-10-26-discovering-secrets/02.png)

Ok, well, let's right-click on the password box and click "Inspect Element",
and see what we find.

![](/media/images/posts/2013-10-26-discovering-secrets/03.png)

Mmhmm, ok, and what might the value of that box be?

![](/media/images/posts/2013-10-26-discovering-secrets/04.png)

You can also get that value by navigating to "Properties" in the right-side box
on the Elements tab:

![](/media/images/posts/2013-10-26-discovering-secrets/05.png)

**Result: success.**

# Attempt 2: Bypass Auto-fill View

Since example.com is not an actual site with user accounts, I redirected
example.com to localhost in my `/etc/hosts`, then created an `index.html` with
only the contents `<input type="password" id="password" />` and started up a
local webserver with `sudo python -m SimpleHTTPServer 80`.  This gave me a
simple page, with nothing but the LastPass-filled field:

![](/media/images/posts/2013-10-26-discovering-secrets/06.png)

This proved to be vulnerable in exactly the same way as the plugin edit page.

![](/media/images/posts/2013-10-26-discovering-secrets/07.png)

Remember that in a real attack, the site would be directly accessible; the
attacker does not have to create a fake version of the site and host it
locally.

**Result: success.**

# Attempt 3: Falsifying the Host

While we've shown the client is insecure, what can we do on the server-side?

There are a myriad of ways to create a simple web application; I decided to use
[Flask].

For this attack, the attacker *does* need to redirect the target credential's
site in `/etc/hosts`:

    127.0.0.1 example.com

I then created a simple Flask application that would pretend to be example.com,
but log any POSTs to the console:

    #!/usr/bin/env python
    
    from flask import Flask, request
    
    app = Flask(__name__)
    
    @app.route('/', methods=['GET', 'POST'])
    def index():
       if request.method == 'GET':
          return '''
    <form method=post action='/'>
       <input type="password" id="password" name="password" />
       <input type=submit>
    </form>
          '''
       else:
          for (key, value) in request.form.items():
             print '%s: %s' % (key, value)
          return ''
    
    if __name__ == '__main__':
       app.run(port=80, debug=True)

When run and submitted to, we indeed see the password:

    [$]> # root privileges are required to open ports 1024 and below.
    [$]> sudo ./example_com.py
     * Running on http://127.0.0.1:80/
     * Restarting with reloader
    127.0.0.1 - - [26/Oct/2013 13:59:02] "GET / HTTP/1.1" 200 -
    password: sharedpassword
    127.0.0.1 - - [26/Oct/2013 13:59:37] "POST / HTTP/1.1" 200 -

**Result: success.**

[Flask]: http://flask.pocoo.org/

# Attempt 4: Sniffing the Traffic

And of course, if the connection is not encrypted, packet-analysis tools like
Wireshark can easily pull form data out of a request:

![](/media/images/posts/2013-10-26-discovering-secrets/08.png)

**Result: success.**

# Conclusions

LastPass's secret shared passwords are nothing of the sort; not only are they
not a feature, the illusion of secrecy is enough to make me label them as an
anti-feature.

LastPass's fault lies not in a failure to properly secure a system, but rather
in implementing a system impossible to secure.  They could force TLS
connections to both encrypt the network traffic and provide a reasonable
assurance the destination server is actually owned by the proper authority, and
the LastPass vault could be adjusted to not display the password at all (like
the website).  But at the end of the day passwords are meant to be entered into
websites - and once the user receives that HTML, they can do anything they want
to it, including pulling out passwords.

