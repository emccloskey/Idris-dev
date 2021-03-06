.. _sect-intro:

************
Introduction
************

In conventional programming languages, there is a clear distinction
between *types* and *values*. For example, in `Haskell
<http://www.haskell.org>`_, the following are types, representing
integers, characters, lists of characters, and lists of any value
respectively:

-  ``Int``, ``Char``, ``[Char]``, ``[a]``

Correspondingly, the following values are examples of inhabitants of
those types:

-  ``42``, ``’a’``, ``Hello world!``, ``[2,3,4,5,6]``

In a language with *dependent types*, however, the distinction is less
clear. Dependent types allow types to “depend” on values — in other
words, types are a *first class* language construct and can be
manipulated like any other value. The standard example is the type of
lists of a given length [1]_, ``Vect n a``, where ``a`` is the element
type and ``n`` is the length of the list and can be an arbitrary term.

When types can contain values, and where those values describe
properties (e.g. the length of a list) the type of a function can
begin to describe its own properties. For example, concatenating two
lists has the property that the resulting list’s length is the sum of
the lengths of the two input lists. We can therefore give the
following type to the ``app`` function, which concatenates vectors:

.. code-block:: idris

    app : Vect n a -> Vect m a -> Vect (n + m) a

This tutorial introduces Idris, a general purpose functional
programming language with dependent types. The goal of the Idris
project is to build a dependently typed language suitable for
verifiable *systems* programming. To this end, Idris is a compiled
language which aims to generate efficient executable code. It also has
a lightweight foreign function interface which allows easy interaction
with external ``C`` libraries.

Intended Audience
=================

This tutorial is intended as a brief introduction to the language, and
is aimed at readers already familiar with a functional language such
as `Haskell <http://www.haskell.org>`_ or `OCaml <http://ocaml.org>`_.
In particular, a certain amount of familiarity with Haskell syntax is
assumed, although most concepts will at least be explained
briefly. The reader is also assumed to have some interest in using
dependent types for writing and verifying systems software.

Example Code
============

This tutorial includes some example code, which has been tested with
Idris version . The files are available in the Idris
distribution, and provided along side the tutorial source, so that you
can try them out easily, under ``tutorial/examples``. However, it is
strongly recommended that you can type them in yourself, rather than
simply loading and reading them.

.. [1]
   Typically, and perhaps confusingly, referred to in the dependently
   typed programming literature as “vectors”
