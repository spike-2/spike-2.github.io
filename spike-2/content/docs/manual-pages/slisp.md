---
title: "Slisp"
draft: false
categories:
    - Documentation
tags:
    - "Slisp"
    - Manual Pages
---

**Slisp is still in development and will be available in a future release of Spike.**

---

Slisp is a dialect of the [Lisp Programming Language](https://en.wikipedia.org/wiki/Lisp_(programming_language)) that runs directly from within Spike! This specific dialect is a decedent of [eLispsis](https://github.com/jwMaxwell/eLispsis), which is a minimal Lisp dialect build on NodeJS.

Lisp is a functional language. There are no variables. Everything is a function call. To learn a bit more about the basic syntax of Lisp, take a look at the [Lisp Wikipedia Page](https://en.wikipedia.org/wiki/Lisp_(programming_language)#Syntax_and_semantics).

## Message Format

To properly run Spike Lisp code, run commands with the following format, noting the newlines as well.
````md
$slisp
```lisp
(code)
```
````
## Available Operators
Operator | Description | Example
--- | --- | ---
`+` | Adds all elements within a list | `(+ 1 2 3)` => `6`
`-` | Subtracts all elements in a list, left to right | `(- 10 4 2)` => `4`
`*` | Multiplies all elements in a list | `(* 2 3 4)` => `24`
`/` | Divides all elements in a list, left to right | `(/ 144 12 3)` => `4`
`%` | Modulo all elements in a list, left to right | `(% 15 20 3)` => `0`
`^` | Returns x1 to the power of x2 ... to the power of n | `(^ 2 2 2 2)` => `256`  

## Available Functions

Function | Description | Example
--- | --- | --- 
`atom` | Returns `t` if the given value is an atom | `(atom 'hi)` => `t`
`quote` | returns a literal value rather than the evaluated value | `(quote (atom 'hi))` => `(atom 'hi)`
`car` | Get first element of list. | `(car '(1 2 3 4))` => `1`
`cdr` | Get list without first element. | `(cdr '(1 2 3 4))` => `(2 3 4)`
`eq` | Returns true if the two values are equal | `(eq 'g 'r)` => `()`
`cons` | Pushes an element to the front of a list | `(cons 'a '(b c d e))` => `(a b c d e)`
`cond` | Creates a conditional statement | `(cond ('() (print "this is false") ('t (print "this is true"))` => `This is true`
`print` | Print input | `(print '(1 2 3 4))`


## Definitions / Declarations
Name | Description | Example
--- | --- | ---
`set` | Define a variable | `(set x (cdr '(1 2 3 4)))`
`setq` | Define a quoted variable | `(set x 25)`
`defun` | Define a function | `(define sum (x y) (+ x y))`
`lamdba` | Define a lambda (anonymous) function | `(lambda (x) (cdr x)) '(a b c)`