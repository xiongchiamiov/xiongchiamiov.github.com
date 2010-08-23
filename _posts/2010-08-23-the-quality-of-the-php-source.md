---
layout: default
title: The Quality of the PHP Source
---

I ran across [this gem] in the PHP source today:

	/* MD% crypt implementation using the windows CryptoApi */

It worries me that a commit where a `5` is replaced with `%` made it through, even if it is only in a comment.

[this gem]: http://github.com/php/php-src/blob/b40a054cf117d4e6a001e80e9e9ff120afddee82/ext/standard/php_crypt_r.c#L97
