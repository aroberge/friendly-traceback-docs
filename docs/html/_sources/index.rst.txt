
Bienvenue 환영합니다 Bienvenido - ようこそ Welcome  歡迎光臨
========================================================================

**Friendly tracebacks** - Simplified Python tracebacks translatable into
any language.

`Code on Github <https://github.com/aroberge/friendly-traceback>`_

.. warning::

    This is alpha software, currently in development. This documentation
    is almost certainly not up to date, but it should be enough to get
    you started.


In a nutshell
--------------

There exists many Python projects intended to supplement the information
given by Python traceback to make them more useful for advanced programmers.
Friendly-traceback is **not** one of these projects.

Friendly-traceback is aimed primarily at **beginners** and/or at users
who would like to get information about traceback in their own language.
Please, see the Design section for a complete description of the goals
of this project. But for now, let's have a quick look at a standard
Python traceback when using the REPL.

.. image:: images/python_indexerror.png
   :scale: 50 %
   :alt: Python IndexError

Not exactly the most helpful information for beginners ...

Here's the corresponding version from Friendly-traceback's REPL

.. image:: images/friendly_indexerror_en.png
   :scale: 50 %
   :alt: Friendly IndexError in English

The only thing that is shown in exactly the same way is the line showing
the exception name and a message.  Everything else can be made available
in other languages.


.. image:: images/friendly_indexerror_fr.png
   :scale: 50 %
   :alt: Friendly IndexError in French

About the version
-----------------

Typically, the version shown at the top will have the letter "a" at the end.
This means that the latest update to the documentation was made after
a release with a version number without the "a" was uploaded to Pypi,
and that we are working towards the next release.
As a result, some features shown here may be slightly different
from the version available from Pypi.

Contents
--------

.. toctree::
   :maxdepth: 2

    Usage <usage>
    Occasional lies <lies>
    Design <design>
    Custom exceptions and formatting <custom>
    Suggest an addition <suggest>
    Adding an Exception <adding_exception>
    Dealing with Syntax Errors <syntax_error>
    Friendly tracebacks - in English <tracebacks_en>
    Friendly tracebacks - in English (Python 3.6) <tracebacks_en36>
    Friendly SyntaxError tracebacks - in English <syntax_tracebacks_en>
    Friendly tracebacks - en Français <tracebacks_fr>
    Friendly tracebacks - in French (Python 3.6) <tracebacks_fr36>
    Friendly SyntaxError tracebacks - en Français <syntax_tracebacks_fr>
    Notes on translations - using gettext <translation_notes>
    Change Log <changelog>

.. todolist::
