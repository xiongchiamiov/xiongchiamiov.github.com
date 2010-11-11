---
layout: with-comments
title: vi Necessities
---

If you do any sysadminning at all, you need to know the very basics of vi, as
it's about the only editor (ed being the other) that's almost guarenteed to be
installed on any UNIX machine you come across. It also happens to be ingrained
into the UNIX way, as evidenced by applications from visudo to NetHack. :)

Evoke vi from the commandline with an optional filename after it:
`vi 2010-03-24-vi-necessities.md`.

Navigate through the file using your familiar arrow keys.

When you reach a point in which you wish to either insert or delete text, press
`i` to enter "Insert mode", type as normal, then press `Esc` to return to
"Normal mode". You may or may not be able to use the arrow keys while in insert
mode.

When you are finished editing the file, type `:wq` and hit enter to write the
changes to the file and exit vi. If you wish to exit without saving changes, use
`:q!` instead.

This is the minimum required.
