# Compact Lisp

## 1. Introduction

2.4.1 Left-Parenthesis

2.4.2 Right-Parenthesis

2.4.3 Single-Quote

2.4.4 Semicolon

2.4.5 Double-Quote

2.4.6 Backquote

2.4.7 Comma

2.4.8 Sharpsign

    dispatch char  purpose                  dispatch char  purpose
    Backspace      signals error            {              undefined*
    Tab            signals error            }              undefined*
    Newline        signals error            +              read-time conditional
    Linefeed       signals error            -              read-time conditional
    Page           signals error            .              undefined***
    Return         signals error            /              undefined
    Space          signals error            A, a           undefined***
    !              undefined*               B, b           binary rational
    "              undefined                C, c           undefined***
    #              undefined***             D, d           undefined
    $              undefined                E, e           undefined
    %              undefined                F, f           undefined
    &              undefined                G, g           undefined
    '              function abbreviation    H, h           undefined
    (              simple vector            I, i           undefined
    )              signals error            J, j           undefined
    *              undefined***             K, k           undefined
    ,              undefined                L, l           undefined
    :              uninterned symbol        M, m           undefined
    ;              undefined                N, n           undefined
    <              undefined***             O, o           octal rational
    =              undefined***             P, p           undefined***
    >              undefined                Q, q           undefined
    ?              undefined*               R, r           undefined***
    @              undefined                S, s           structure
    [              undefined*               T, t           undefined
    \              undefined***             U, u           undefined
    ]              undefined*               V, v           undefined
    ^              undefined                W, w           undefined
    _              undefined                X, x           hexadecimal rational
    `              undefined                Y, y           undefined
    |              undefined***             Z, z           undefined
    ~              undefined                Rubout         undefined

2.4.9 Re-Reading Abbreviated Expressions

## 2. Syntax

## 3. Evaluation and Compilation

## 4. Types and Classes

## 5. Data and Control Flow

Function APPLY

Macro DEFUN

Accessor FDEFINITION

Function FBOUNDP

Function FMAKUNBOUND

Special Operator FLET

Special Operator LABELS

Special Operator MACROLET

Function FUNCALL

Special Operator FUNCTION

Function FUNCTIONP

Constant Variable LAMBDA-LIST-KEYWORDS

Macro DEFCONSTANT

Macro DEFPARAMETER

Macro DEFVAR

Macro DESTRUCTURING-BIND

NOTE: Restricted syntax.

Special Operator LET

Special Operator LET*

Special Operator UNWIND-PROTECT

Constant Variable NIL

Function NOT

Constant Variable T

Function EQ

Function EQL

Function EQUAL

Function IDENTITY

Function COMPLEMENT

Function CONSTANTLY

Function EVERY

Function SOME

Function NOTEVERY

Function NOTANY

Macro AND

Macro COND

Special Operator IF

Macro OR

Macro WHEN

Macro UNLESS

Macro CASE

Macro ECASE

Macro TYPECASE

Macro ETYPECASE

Macro PROG1

Special Operator PROGN

Macro DEFINE-MODIFY-MACRO

Macro DEFSETF

Macro DEFINE-SETF-EXPANDER

Function GET-SETF-EXPANSION

Macro SETF

Macro PSETF

Condition Type UNDEFINED-FUNCTION

## 6. Iteration

Macro DO

Macro DO*

Macro DOTIMES

Macro DOLIST

## 7. Objects

(Intentionally left blank.)

## 8. Structures

Macro DEFSTRUCT

Function COPY-STRUCTURE

## 9. Conditions

Condition Type CONDITION

Condition Type WARNING

Condition Type ERROR

Condition Type PARSE-ERROR

Condition Type STORAGE-CONDITION

Macro ASSERT

Function ERROR

Macro CHECK-TYPE

Condition Type SIMPLE-ERROR

Macro HANDLER-CASE

## 10. Symbols

System Class SYMBOL

Type KEYWORD

Function (symbolp object) => generalized-boolean

Function (keywordp object) => generalized-boolean

Function (make-symbol name) => new-symbol

Function (gensym &optional x) => new-symbol

Getter (symbol-function symbol) => contents

Setter (setf (symbol-function symbol) new-contents)

Function (symbol-name symbol) => name

Function (symbol-package symbol) => contents

Accessor SYMBOL-VALUE

Function BOUNDP

Function MAKUNBOUND

Condition Type UNBOUND-VARIABLE

## 11. Packages

System Class PACKAGE

Function EXPORT

Function FIND-SYMBOL

Function FIND-PACKAGE

Function FIND-ALL-SYMBOLS

Function IMPORT

Function LIST-ALL-PACKAGES

Function RENAME-PACKAGE

Function SHADOW

Function SHADOWING-IMPORT

Function DELETE-PACKAGE

Function MAKE-PACKAGE

Function UNEXPORT

Function UNINTERN

Macro IN-PACKAGE

Function UNUSE-PACKAGE

Function USE-PACKAGE

Macro DEFPACKAGE

Macro DO-SYMBOLS, DO-EXTERNAL-SYMBOLS, DO-ALL-SYMBOLS

Function INTERN

Function PACKAGE-NAME

Function PACKAGE-NICKNAMES

Function PACKAGE-SHADOWING-SYMBOLS

Function PACKAGE-USE-LIST

Function PACKAGE-USED-BY-LIST

Function PACKAGEP

Variable *PACKAGE*

Condition Type PACKAGE-ERROR

Function PACKAGE-ERROR-PACKAGE

## 12. Numbers

## 13. Characters

System Class CHARACTER

Function CHARACTERP

Function CHAR-CODE

Constant Variable CHAR-CODE-LIMIT

## 14. Lists

System Class LIST

System Class NULL

Function LIST, LIST*

Function LISTP

Function MAKE-LIST

Macro PUSH

Macro POP

Accessor FIRST, SECOND, THIRD, FOURTH, FIFTH, SIXTH, SEVENTH, EIGHTH, NINTH, TENTH

Function ENDP

Function NULL

Function APPEND

Function REVAPPEND

Function BUTLAST

Accessor REST

Function ASSOC, ASSOC-IF

Accessor GETF

Macro REMF

Function INTERSECTION

Function ADJOIN

Macro PUSHNEW

Function SET-DIFFERENCE

Function SET-EXCLUSIVE-OR

Function SUBSETP

Function UNION

## 15. Vectors

System Class VECTOR

Function (**make-array** length &key element-type initial-element adjustable fill-pointer displaced-to displaced-index-offset) => new-array

NOTE: length must be an integer, cannot be a list.

NOTE: &key initial-contents omitted.

Function (**array-element-type** array) => typespec

Function ARRAY-HAS-FILL-POINTER-P

Function ARRAY-DISPLACEMENT

Function (**vector** &rest objects) => vector

Function (**vector-push** new-element vector) => new-index-p

Function (**vector-push-extend** new-element vector) => new-index

NOTE: &optional extension omitted.

Function (**vectorp** object) => generalized-boolean

## 16. Strings

System Class STRING

Function (**string** x) => string

Function (**string-upcase** string) => cased-string

Function (**string-downcase** string) => cased-string

NOTE: &key start end omitted.

Function (**string-trim** character-bag string) => trimmed-string

Function (**string-left-trim** character-bag string) => trimmed-string

Function (**string-right-trim** character-bag string) => trimmed-string

Function (**string=** string1 string2) => generalized-boolean

Function (**string<** string1 string2) => mismatch-index

Function (**string>** string1 string2) => mismatch-index

Function (**string<=** string1 string2) => mismatch-index

Function (**string>=** string1 string2) => mismatch-index

Function (**string-equal** string1 string2) => generalized-boolean

Function (**string-lessp** string1 string2) => mismatch-index

Function (**string-greaterp** string1 string2) => mismatch-index

NOTE: &key start1 end1 start2 end2 omitted.

Function (**stringp** object) => generalized-boolean

Function (**make-string** size &key initial-element) => string

NOTE: &key element-type omitted.

## 17. Sequences

System Class sequence

Function (**copy-seq** sequence) => copied-sequence

Getter (**elt** sequence index) => object

Setter (setf (**elt** sequence index) new-object)

Getter (**subseq** sequence start &optional end) => subsequence

Setter (setf (**subseq** sequence start &optional end) new-subsequence)

Function (**map** result-type function &rest sequences+) => result

Function (**reduce** function sequence &key key from-end initial-value) => result

NOTE: &key start end omitted.

Function (**count** item sequence &key key test) => n

NOTE: &key from-end start end test-not omitted.

Function (**count-if** predicate sequence &key key) => n

NOTE: &key from-end start end omitted.

Function (**length** sequence) => n

Function (**reverse** sequence) => reversed-sequence

Function (**sort** sequence predicate &key key) => sorted-sequence

Function (**stable-sort** sequence predicate &key key) => sorted-sequence

Function (**find** item sequence &key from-end test start end key) => element

NOTE: &key test-not omitted.

Function (**find-if** predicate sequence &key from-end start end key) => element

Function (**position** item sequence &key from-end test start end key) => position

NOTE: &key test-not omitted.

Function (**position-if** predicate sequence &key from-end start end key) => position

Function (**search** sequence-1 sequence-2 &key from-end test key start1 start2 end1 end2) => position

NOTE: &key test-not omitted.

Function (**mismatch** sequence-1 sequence-2 &key from-end test key start1 start2 end1 end2) => position

NOTE: &key test-not omitted.

Function (**concatenate** result-type &rest sequences) => result-sequence

Function (**remove** item sequence &key test key) => result-sequence

NOTE: &key from-end test-not start end count omitted.

Function (**remove-if** test sequence &key key) => result-sequence

NOTE: &key from-end start end count omitted.

Function (**remove-duplicates** sequence &key test key) => result-sequence

NOTE: &key from-end test-not start end omitted.

## 18. Hash Tables

System Class HASH-TABLE

Function (**make-hash-table** &key test) => hash-table

NOTE: &key size rehash-size rehash-threshold omitted.

Function (**hash-table-p** object) => generalized-boolean

Function (**hash-table-count** hash-table) => count

Function (**hash-table-test** hash-table) => test

Getter (**gethash** key hash-table &optional default) => value

NOTE: Extra value present-p not returned.

Setter (setf (**gethash** key hash-table &optional default) new-value)

NOTE: default is evaluated but its value is ignored.

Function (**remhash** key hash-table) => generalized-boolean

Function (**maphash** function hash-table) => nil

Function (**clrhash** hash-table) => hash-table

## 19. Filenames

Function (**namestring** pathname) => namestring

Function (**file-namestring** pathname) => namestring

Function (**directory-namestring** pathname) => namestring

Function (**host-namestring** pathname) => namestring

Function (**enough-namestring** pathname &optional defaults) => namestring

## 20. Files

Function DIRECTORY

Function PROBE-FILE

Function ENSURE-DIRECTORIES-EXIST

Function TRUENAME

Function FILE-AUTHOR

Function FILE-WRITE-DATE

Function RENAME-FILE

Function DELETE-FILE

Condition Type FILE-ERROR

Function FILE-ERROR-PATHNAME

## Streams

## 22. Printer

Function PRIN1

Function PRINC

Function PRIN1-TO-STRING

Function PRINC-TO-STRING

Condition Type PRINT-NOT-READABLE

Function PRINT-NOT-READABLE-OBJECT

Function FORMAT

NOTE: Reduced syntax.

* ~% Newline
* ~% Tilde

    ~n% outputs n newlines.
    ~n~ outputs n tildes.

* ~B Binary
* ~O Octal
* ~D Decimal
* ~X Hexadecimal

    ~mincol,padcharB
    ~mincol,padcharO
    ~mincol,padcharD
    ~mincol,padcharX

* ~F Fixed-Format Floating-Point
* ~E Exponential Floating-Point
* ~G General Floating-Point

    ~w,d,k,overflowchar,padcharF
    ~w,d,e,k,overflowchar,padchar,exponentcharE
    ~w,d,e,k,overflowchar,padchar,exponentcharG

* ~A Aesthetic
* ~S Standard

    ~mincol,colinc,minpad,padcharA
    ~mincol,colinc,minpad,padcharS

* ~Newline Ignored Newline

## 23. Reader

System Class READTABLE

Function COPY-READTABLE

Function READ

Function READ-FROM-STRING

Function READTABLEP

Condition Type READER-ERROR

## System Construction

## Environment
