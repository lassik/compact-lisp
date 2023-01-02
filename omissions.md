# Compact Lisp: Omitted features

This document enumerates all those features of Common Lisp which were
omitted from Compact Lisp. A rationale is given in each case.

## 5.3 The Data and Control Flow Dictionary

* Function `equalp`

> Equalp is convenient, but since the rules for equality testing seem
> arbitrary it obfuscates code. It's probably better if programmers
> say what they mean more directly.

## 10.2 The Symbols Dictionary

* Function `gentemp`

> Deprecated in Common Lisp.

* Variable `*gensym-counter*`

> Rarely used.

* Function `copy-symbol`

> Rarely used.

* Accessor `symbol-plist`
* Accessor `get`
* Function `remprop`

> Symbol properties are rarely used.

* Function `set`

> Deprecated in Common Lisp.

## 11.2 The Packages Dictionary

* Macro `with-package-iterator`

> Rarely used.

## 12.2 The Numbers Dictionary

* Function `/=`

> Rarely used. The name is confusing to people coming from other
> languages.

* Function `ffloor`
* Function `fceiling`
* Function `ftruncate`
* Function `fround`

> Rarely used.

* Function `sinh`
* Function `cosh`
* Function `tanh`
* Function `asinh`
* Function `acosh`
* Function `atanh`

> Rarely used.

* Function `gcd`
* Function `lcm`

> Rarely used.

* Function `boole`
* Constant Variable `boole-1`
* Constant Variable `boole-2`
* Constant Variable `boole-and`
* Constant Variable `boole-andc1`
* Constant Variable `boole-andc2`
* Constant Variable `boole-c1`
* Constant Variable `boole-c2`
* Constant Variable `boole-clr`
* Constant Variable `boole-eqv`
* Constant Variable `boole-ior`
* Constant Variable `boole-nand`
* Constant Variable `boole-nor`
* Constant Variable `boole-orc1`
* Constant Variable `boole-orc2`
* Constant Variable `boole-set`
* Constant Variable `boole-xor`

> Rarely used.

* Function `logandc1`
* Function `logandc2`
* Function `logeqv`
* Function `lognand`
* Function `lognor`
* Function `logorc1`
* Function `logorc2`
* Function `logxor`

> Rarely used.

## 14.2 The Conses Dictionary

* Function `copy-list`

> copy-seq does this and more.

* Function `list-length`

> Rarely used; subset of `length`.

* Function `last`

> Omitted due to its confusing name. You'd think it returns the last
> item, but it actually returns the last pair.

* Tree functions

> Rarely used.

* Function `nconc`

> Not necessary. Standard Scheme only has `append` and nobody
> complains.

* Function `nbutlast`

* Function `nreconc`

* Accessor `nth`

> elt does the same thing more generically.

* Function `nthcdr`

> Name refers to conses.

* Function `ldiff`
* Function `tailp`

> Rarely used.

> Tailp may not be the best tool for any job.

* Function `member`
* Function `member-if`

> The names are misleading: "member" sounds like it would just
> return the element, but in fact it returns the tail of the list
> starting at the element.

> Getting the tail is rarely needed. Usually one just wants the
> element. Find/find-if and position/position-if do that, and they
> work on all types of sequences, not just lists.

* Function `member-if-not`

> Deprecated in Common Lisp.

* Function `mapl`
* Function `maplist`
* Function `mapcon`

> Rarely used.

* Function `acons`

> Rarely used; name mentions conses.

* Function `assoc-if-not`

> Deprecated in Common Lisp.

* Function `copy-alist`

> Rarely used; deals with conses, not lists.

* Function `get-properties`

> Rarely used; complex; getf can do the same.

* Function `nunion`
* Function `nintersection`
* Function `nset-exclusive-or`
* Function `nset-difference`

> Rarely used.

* Function `pairlis`

> Rarely used.

* Function `assoc-if-not`

> Deprecated in Common Lisp.

* Function `rassoc`
* Function `rassoc-if`
* Function `rassoc-if-not`

> Rarely used.

## 15.2 The Arrays Dictionary

* Function `arrayp`

> Use vectorp.

* Accessor `aref`

> Use elt.

* Accessor `svref`

> Use elt.

* Function `adjust-array`
* Function `adjustable-array-p`

> Rarely used; complex.

* Constant Variable `array-rank-limit`

> Has no use case. In a dedicated Compact Lisp implementation it would
> always be 1. In a Common Lisp implementation it would be bigger, but
> you couldn't make use of the bigger values in portable Compact Lisp
> code.

* Function `upgraded-array-element-type`

> Rarely used; makes complex stipulations about the type system.

* Constant Variable `array-dimension-limit`
* Constant Variable `array-total-size-limit`

> Rarely used; name mentions arrays.

* Function `array-in-bounds-p`

> Rarely used; name mentions arrays.

## 16.2 The Strings Dictionary

* Accessor `char`
* Accessor `schar`

> Rarely used; name mentions chars.

* Function `string/=`

> Rarely used; name is confusing to people coming from other languages.

* Function `string-not-equal`

> Rarely used.

* Function `string-capitalize`

> Rarely used; complex.

## 17.3 The Sequences Dictionary

* Function `count-if-not`
* Function `find-if-not`
* Function `position-if-not`
* Function `substitute-if-not`
* Function `nsubstitute-if-not`
* Function `remove-if-not`
* Function `delete-if-not`

> Deprecated in Common Lisp.

* Function `map-into`

> Confusing; rarely used.

* Function `nreverse`

> Destructive.

* Function `nsubstitute`
* Function `nsubstitute-if`

> Destructive.

* Function `delete`
* Function `delete-if`
* Function `delete-duplicates`

> Destructive.
