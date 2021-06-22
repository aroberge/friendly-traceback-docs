.. _import_all:

.. todo::

   This is just a first draft that will need more work.


Why ``import *``?
==================

In many pages of this documentation, you will see that I suggest to use
something like ``from friendly.X import *``.
This is often mentioned as being a bad practice, since it
"pollutes" the current namespace with various names whose origin become
difficult to trace.

If you have tried the **friendly** console, or read the previous
pages in this documentation, you will have seen various useful
functions such as ``what()``, ``where()``, ``why()``, etc., which
can be used in an interactive mode.  You can think of these
functions as useful additions to Python's builtins, such as ``dir()``,
``vars()``, etc.
These functions are meant to be used in interactive sessions.

The usual suggested alternatives to importing everything
are the following:

1. Import only what's needed. For example::

       from friendly.X import what, where, why


2. Import as a namespace; something like::

       from friendly import X
       # or
       import friendly.X as Y


One problem with the first suggestion is that **friendly** has **many**
other functions that are potentially useful. So this might
require another import statement, ``from friendly.X import something_else``
when wanting to use ``something_else``. Trying to import **all** the
possibly relevant functions by explicitly naming them
in a single import statement is not really practical.

Using the second alternative means that,
instead of simply writing ``why()``, one might have
to write something like ``X.why()``.  A potential problem with
this second approach is that ``friendly.X`` might contain many
other names, such as ``__path__``, ``__spec__``, etc., as well
as other functions which are meant to be used only within
module ``X`` which are not useful but would show up when doing something like
``dir(X)`` or ``help(X)``.

When creating a special module ``friendly.X`` for a specific
environment, such as ``friendly.idle`` to be used with Python's IDLE,
I define ``__all__`` so that only the relevant objects are imported
when doing ``from friendly.X import *``.

If you do not wish to do so, I suggest instead the following::

    from friendly.X import Friendly
    # or
    from friendly.X import Friendly as some_other_name

``Friendly`` is a special object which includes all the
potentially useful functions as methods.

.. warning::

    This might not be true. As I write this, ``Friendly`` does
    not include ``run``, ``install``, and possibly others.


By this, I mean that ``Friendly.why()`` is equivalent
to writing ``why()``.
``Friendly`` is also imported if you do ``from friendly.X import *``.

As mentioned previously, [:ref:`friendly_object`], ``Friendly``
can be used to easily obtain a list of useful functions, without
needing to consult the documentation.

