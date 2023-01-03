# Compact Lisp: Omitted features

This document enumerates all those features of Common Lisp which were
omitted from Compact Lisp. A rationale is given in each case.

## 5.3 The Data and Control Flow Dictionary

Function FUNCTION-LAMBDA-EXPRESSION

Function COMPILED-FUNCTION-P

Constant Variable CALL-ARGUMENTS-LIMIT

Constant Variable LAMBDA-PARAMETERS-LIMIT

Special Operator PROGV

Special Form SETQ

Macro PSETQ

Special Operator BLOCK

Special Operator CATCH

Special Operator GO

Special Operator RETURN-FROM

Macro RETURN

Special Operator TAGBODY

Special Operator THROW

Function EQUALP

Macro CCASE

Macro CTYPECASE

Macro MULTIPLE-VALUE-BIND

Special Operator MULTIPLE-VALUE-CALL

Macro MULTIPLE-VALUE-LIST

Special Operator MULTIPLE-VALUE-PROG1

Macro MULTIPLE-VALUE-SETQ

Accessor VALUES

Function VALUES-LIST

Constant Variable MULTIPLE-VALUES-LIMIT

Macro NTH-VALUE

Macro PROG, PROG*

Macro PROG2

Macro SHIFTF

Macro ROTATEF

Condition Type CONTROL-ERROR

Condition Type PROGRAM-ERROR

* Function `equalp`

> Equalp is convenient, but since the rules for equality testing seem
> arbitrary it obfuscates code. It's probably better if programmers
> say what they mean more directly.

## 9.2 The Conditions Dictionary

Condition Type STYLE-WARNING

Condition Type SERIOUS-CONDITION

Condition Type CELL-ERROR

Function CELL-ERROR-NAME

Condition Type STORAGE-CONDITION

Function CERROR

Function INVALID-METHOD-ERROR

Function METHOD-COMBINATION-ERROR

Function SIGNAL

Condition Type SIMPLE-CONDITION

Function SIMPLE-CONDITION-FORMAT-CONTROL, SIMPLE-CONDITION-FORMAT-ARGUMENTS

Function WARN

Condition Type SIMPLE-WARNING

Function INVOKE-DEBUGGER

Function BREAK

Variable *DEBUGGER-HOOK*

Variable *BREAK-ON-SIGNALS*

Macro HANDLER-BIND

Macro IGNORE-ERRORS

Macro DEFINE-CONDITION

Function MAKE-CONDITION

System Class RESTART

Function COMPUTE-RESTARTS

Function FIND-RESTART

Function INVOKE-RESTART

Function INVOKE-RESTART-INTERACTIVELY

Macro RESTART-BIND

Macro RESTART-CASE

Function RESTART-NAME

Macro WITH-CONDITION-RESTARTS

Macro WITH-SIMPLE-RESTART

Restart ABORT

Restart CONTINUE

Restart MUFFLE-WARNING

Restart STORE-VALUE

Restart USE-VALUE

Function ABORT, CONTINUE, MUFFLE-WARNING, STORE-VALUE, USE-VALUE

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

## 13.2 The Characters Dictionary

Type BASE-CHAR

Type STANDARD-CHAR

Type EXTENDED-CHAR

Function CHAR=, CHAR/=, CHAR<, CHAR>, CHAR<=, CHAR>=, CHAR-EQUAL, CHAR-NOT-EQUAL, CHAR-LESSP, CHAR-GREATERP, CHAR-NOT-GREATERP, CHAR-NOT-LESSP

Function CHARACTER

Function ALPHA-CHAR-P

Function ALPHANUMERICP

Function DIGIT-CHAR

Function DIGIT-CHAR-P

Function GRAPHIC-CHAR-P

Function STANDARD-CHAR-P

Function CHAR-UPCASE, CHAR-DOWNCASE

Function UPPER-CASE-P, LOWER-CASE-P, BOTH-CASE-P

Function CHAR-INT

Function CODE-CHAR

Function CHAR-NAME

Function NAME-CHAR

## 14.2 The Conses Dictionary

System Class CONS

Type ATOM

Function CONS

Function CONSP

Function ATOM

Function RPLACA, RPLACD

Accessor CAR, CDR, CAAR, CADR, CDAR, CDDR, CAAAR, CAADR, CADAR, CADDR, CDAAR, CDADR, CDDAR, CDDDR, CAAAAR, CAAADR, CAADAR, CAADDR, CADAAR, CADADR, CADDAR, CADDDR, CDAAAR, CDAADR, CDADAR, CDADDR, CDDAAR, CDDADR, CDDDAR, CDDDDR

Function COPY-TREE

Function SUBLIS, NSUBLIS

Function SUBST, SUBST-IF, SUBST-IF-NOT, NSUBST, NSUBST-IF, NSUBST-IF-NOT

Function TREE-EQUAL

Function LIST-LENGTH

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

* Function `mapc`
* Function `mapcar`
* Function `mapcan`

> Use `map` instead.

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

* Function `set-exclusive-or`

> Rarely used.

* Function `nunion`
* Function `nintersection`
* Function `nset-exclusive-or`
* Function `nset-difference`

> Destructive.

* Function `pairlis`

> Rarely used.

* Function `assoc-if-not`

> Deprecated in Common Lisp.

* Function `rassoc`
* Function `rassoc-if`
* Function `rassoc-if-not`

> Rarely used.

## 15.2 The Arrays Dictionary

System Class ARRAY

Type SIMPLE-ARRAY

System Class BIT-VECTOR

Type SIMPLE-BIT-VECTOR

Function ARRAY-DIMENSION

Function ARRAY-DIMENSIONS

Function ARRAY-IN-BOUNDS-P

Function ARRAY-RANK

Function ARRAY-ROW-MAJOR-INDEX

Function ARRAY-TOTAL-SIZE

Function ARRAYP

Accessor ROW-MAJOR-AREF

Function UPGRADED-ARRAY-ELEMENT-TYPE

Constant Variable ARRAY-DIMENSION-LIMIT

Constant Variable ARRAY-RANK-LIMIT

Constant Variable ARRAY-TOTAL-SIZE-LIMIT

Function SIMPLE-VECTOR-P

Accessor BIT, SBIT

Function BIT-AND, BIT-ANDC1, BIT-ANDC2, BIT-EQV, BIT-IOR, BIT-NAND, BIT-NOR, BIT-NOT, BIT-ORC1, BIT-ORC2, BIT-XOR

Function BIT-VECTOR-P

Function SIMPLE-BIT-VECTOR-P

Type SIMPLE-VECTOR

Accessor SVREF

Function VECTOR-POP

Accessor FILL-POINTER

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

Type BASE-STRING

Type SIMPLE-STRING

Type SIMPLE-BASE-STRING

Function SIMPLE-STRING-P

Accessor SCHAR

Function NSTRING-UPCASE, NSTRING-DOWNCASE, NSTRING-CAPITALIZE

* Accessor `char`
* Accessor `schar`

> Rarely used; name mentions chars.

* Function `string/=`

> Rarely used; name is confusing to people coming from other languages.

* Function `string-not-equal`
* Function `string-not-greaterp`
* Function `string-not-lessp`

> Rarely used. Names are weird.

* Function `string-capitalize`

> Rarely used; complex.

## 17.3 The Sequences Dictionary

* Function `fill`

> Rarely used.

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

* Function `replace`
* Function `substitute`
* Function `substitute-if`

> Confusing; rarely needed; can be emulated using other functions.

> People usually need to replace subsequences, and especially
> substrings, matching a given pattern. None of these functions do
> that.

* Function `nsubstitute`
* Function `nsubstitute-if`

> Destructive.

* Function `delete`
* Function `delete-if`
* Function `delete-duplicates`

> Destructive.

* Function `merge`

> Destructive, rarely used.

## 18.2 The Hash Tables Dictionary

Function HASH-TABLE-REHASH-SIZE

Function HASH-TABLE-REHASH-THRESHOLD

Function HASH-TABLE-SIZE

Macro WITH-HASH-TABLE-ITERATOR

Function SXHASH

## 19.4 The Filenames Dictionary

System Class PATHNAME

System Class LOGICAL-PATHNAME

Function PATHNAME

Function MAKE-PATHNAME

Function PATHNAMEP

Function PATHNAME-HOST, PATHNAME-DEVICE, PATHNAME-DIRECTORY, PATHNAME-NAME, PATHNAME-TYPE, PATHNAME-VERSION

Function LOAD-LOGICAL-PATHNAME-TRANSLATIONS

Accessor LOGICAL-PATHNAME-TRANSLATIONS

Function LOGICAL-PATHNAME

Variable *DEFAULT-PATHNAME-DEFAULTS*

Function PARSE-NAMESTRING

Function WILD-PATHNAME-P

Function PATHNAME-MATCH-P

Function TRANSLATE-LOGICAL-PATHNAME

Function TRANSLATE-PATHNAME

Function MERGE-PATHNAMES

## 22.4 The Printer Dictionary

Macro FORMATTER

Function WRITE, PRINT, PPRINT

Function WRITE-TO-STRING

Function COPY-PPRINT-DISPATCH

Function PPRINT-DISPATCH

Local Macro PPRINT-EXIT-IF-LIST-EXHAUSTED

Function PPRINT-FILL, PPRINT-LINEAR, PPRINT-TABULAR

Function PPRINT-INDENT

Macro PPRINT-LOGICAL-BLOCK

Function PPRINT-NEWLINE

Local Macro PPRINT-POP

Function PPRINT-TAB

Standard Generic Function PRINT-OBJECT

Macro PRINT-UNREADABLE-OBJECT

Function SET-PPRINT-DISPATCH

Variable *PRINT-ARRAY*

Variable *PRINT-BASE*, *PRINT-RADIX*

Variable *PRINT-CASE*

Variable *PRINT-CIRCLE*

Variable *PRINT-ESCAPE*

Variable *PRINT-GENSYM*

Variable *PRINT-LEVEL*, *PRINT-LENGTH*

Variable *PRINT-LINES*

Variable *PRINT-MISER-WIDTH*

Variable *PRINT-PPRINT-DISPATCH*

Variable *PRINT-PRETTY*

Variable *PRINT-READABLY*

Variable *PRINT-RIGHT-MARGIN*

## 23.2 The Reader Dictionary

Function MAKE-DISPATCH-MACRO-CHARACTER

Function READ-PRESERVING-WHITESPACE

Function READ-DELIMITED-LIST

Accessor READTABLE-CASE

Function SET-DISPATCH-MACRO-CHARACTER, GET-DISPATCH-MACRO-CHARACTER

Function SET-MACRO-CHARACTER, GET-MACRO-CHARACTER

Function SET-SYNTAX-FROM-CHAR

Macro WITH-STANDARD-IO-SYNTAX

Variable *READ-BASE*

Variable *READ-DEFAULT-FLOAT-FORMAT*

Variable *READ-EVAL*

Variable *READ-SUPPRESS*

Variable *READTABLE*
