---
layout: default
title: Tree Traversal of Wikipedia
---

I often hear computer-sciencey nerds taking informal polls to see if more of
their friends browse Wikipedia using [breadth-first] or [depth-first] traversal
strategies. You should all be aware by now of how these trees are generated
(below, [xkcd #214]).

![The Trouble with Wikipedia](http://imgs.xkcd.com/comics/the_problem_with_wikipedia.png "&#39;Taft in a wet t-shirt contest&#39; is the key image here.")

Anyways, the difference between those two is simply whether new tabs are opened
next to the current tab, or on the far right.

![Tab Mix Plus preferences](/media/images/posts/2010-04-09-tree-traversal-of-wikipedia/tab-mix-plus_01.png)

Much more interesting, to me, is the difference between depth-first (also called
preorder) and [postorder] traversal, which boils down to whether or not the root
(the article you are currently reading) is visited (completely read) before its
children (the links you open as you read). Proponents of depth-first ridicule
the postorderers' skittish attention, while the latter retort back that they
prefer to actually *understand* what they're reading.

Now, since I use the amazing [navigation popups], I can get an idea of what
something is without having to leave the article I'm reading.  gg.

[breadth-first]: http://en.wikipedia.org/wiki/Breadth-first_search
[depth-first]: http://en.wikipedia.org/wiki/Depth-first_search
[xkcd #214]: http://xkcd.com/214/
[postorder]: http://en.wikipedia.org/wiki/Postorder_traversal
[navigation popups]: http://en.wikipedia.org/wiki/Wikipedia:Tools/Navigation_popups
