auto-dictionary-mode
====================

An automatic dictionary switcher for Emacs spell checking

[![Build Status](https://travis-ci.org/nschum/auto-dictionary-mode.png?branch=master)](https://travis-ci.org/nschum/auto-dictionary-mode)

Add the following to your .emacs file:

    (require 'auto-dictionary)
    (add-hook 'flyspell-mode-hook (lambda () (auto-dictionary-mode 1)))

Then just type.  When you stop for a few moments `auto-dictionary-mode' will
start evaluating the content.

You can also force a check using `adict-guess-dictionary`, whether or not
`auto-dictionary-mode` is enabled.

If you're unhappy with the results, call `adict-change-dictionary` to
change it and stop automatic checks.

You can use `adict-change-dictionary-hook` to hook into any of these changes,
or `adict-conditional-insert` to insert text (like signatures) that will
automatically conform to the language.

This fork introduces an alternative way of language detection.  
Instead relying on a hard-coded list of common words,  
it will launch multiple ispell processes on a chunk of text and  
select the dictionary that reported the highest number of correct words.  
Customize variable the `adict-dictionary-list-ispell` to set the list of  
dictionaries you want to use.  

You can install it with following el-get recipe:  
```
(:name auto-dictionary-ispell
       :website "https://github.com/813gan/auto-dictionary-mode"
       :description "auto-dictionary-mode fork that supports all dictionaries available for ispell"
       :type github
       :pkgname "813gan/auto-dictionary-mode")
```
