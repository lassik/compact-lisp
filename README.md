# Compact Lisp

**A simple subset of Common Lisp.**

## Introduction

Compact Lisp is a language roughly equivalent in features to standard
Scheme (R5RS or R7RS-small) or the core of Emacs Lisp. However, all
features are taken from Common Lisp and nothing is added.

This means that all Compact Lisp programs are also Common Lisp
programs. They can be loaded as-is into one of the many existing
Common Lisp implementations.

## Motivation

The goals of Compact Lisp are as follows.

* Enable the making of radically simpler Common Lisp implementations
  for scripting purposes.

* Do our part to modernize Common Lisp by emphasizing the more modern
  parts of the language and deprecating the parts that show their age.

* Find common ground between Common Lisp and other Lisp dialects in
  the interest of future interoperability.

## Features

* Lisp-2.
* Lexical and dynamic variables.
* Lexical closures.
* signal, error, handler-case, unwind-protect.
* Symbols and keywords.
* Symbol packages.
* Optional, rest, and keyword arguments.
* Reduced destructuring-bind.
* Reduced defstruct.
* Reduced format.
* Lists.
* Vectors, strings, characters.
* Sequence API.
* Hash tables.
* Subtyping (type-of, typep).
* setf.
* Macros.
* Multiple values.

## Missing features

* Pairs are optional. (Lists may be vectors.)
* Pairs, when present, may not be mutable.
* Classes and methods.
* Arrays other than vectors.
* Lexical tags (tagbody, return, return-from).
* Dynamic tags (catch, throw).
* Continuable signals.
* The handler-bind macro.
* The loop macro.
* Many format directives.
* Programmable reader (readtables).
* Programmable printer.
* Printer "fresh line" feature.
* &aux arguments.
* Ratios.
* Complex numbers.
* short-float, single-float, double-float, and long-float types.
* Bitvectors.
* Pathname objects. (Namestrings are used.)
* Symbol macros.
* Uppercase symbols. (The Compact Lisp reader is always case sensitive.)
