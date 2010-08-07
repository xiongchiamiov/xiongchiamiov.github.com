---
layout: default
title: Moving to vim
---

I really want to move from Komodo to vim. Sure, [I love Komodo], but sometimes
it can just be freakin' annoying.

So, here's a list of things I want vim to be able to do for me to switch:

* <strike>Display line numbers</strike> [done](#display-line-numbers)
* Split screen horizontally or vertically, and move files between the two
* Show a tree-based overview of a directory (preferably with the ability to open files from there).  Showing and hiding this quickly is important.
* <strike>Use the indentation already present in a file</strike> [done](#use-indentation)
* Use the line-endings already present in a file
* Show me when indentation is mismatched, or allow me to turn on whitespace characters easily.
* Code folds are created automatically based on syntax/indentation/braces/whatever.
* I can complete words that I've typed previously.
* Tab completion.
* Tooltips or similar remind me of function parameters.
* I'm presented with valid choices for css rules.
* Autocompletion of braces, parens, end blocks, etc.

Updates will be made to this page as I find answers.

<a name="display-line-numbers"></a>
# Display Line Numbers

	set number

<a name="use-indentation"></a>
# Use the Indentation Already Present in a File

With [DetectIndent] installed,

	let g:detectindent_preferred_indent=4
	autocmd BufReadPost * :DetectIndent

<a name="show-mismatched-indentation"></a>
# Show Mismatched Indentation

With [IndentConsistencyCop] installed,


[I love Komodo]: /2010/03/18/why-i-love-komodo-edit.html
[DetectIndent]: http://www.vim.org/scripts/script.php?script_id=1171
[IndentConsistencyCop]: http://www.vim.org/scripts/script.php?script_id=1690
