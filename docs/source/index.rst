
Bienvenue 환영합니다 Bienvenido - ようこそ Welcome  歡迎光臨
========================================================================

**Friendly tracebacks** - Simplified Python tracebacks translatable into
any language.

`Code on Github <https://github.com/aroberge/friendly-traceback>`_


In a nutshell
--------------

There exists many Python projects intended to supplement the information
given by Python traceback to make them more useful for **advanced** programmers.
Friendly-traceback is **not** one of these projects.

Friendly-traceback is aimed primarily at **beginners** and/or at users
who would like to get information about traceback in their own language.
Please, see the Design section for a complete description of the goals
of this project.

While Friendly-traceback can be used on its own with a specially
designed REPL, a better option would be to use it together with
GUI-based editors/IDE
that are especially designed with beginners in mind.
Currently, only one such program, `Thonny <https://thonny.org/>`_,
incorporate some of the features of Friendly-traceback.
We explain how to use Friendly-traceback with Thonny in this
document.

For the other programs designed with beginners in mind,
such as `Mu <https://codewith.mu/>`_ or, to a certain extent,
Python's own IDLE,
we show what we hope is a relatively easy way to use Friendly-traceback.


A quick look
------------

Let's have a quick look at a standard
Python traceback when using the REPL.

.. image:: images/python_indexerror.png
   :scale: 50 %
   :alt: Python IndexError

Not exactly the most helpful information for beginners ...

Here's the corresponding version from Friendly-traceback's REPL using
the default configuration.

.. image:: images/friendly_indexerror_en.png
   :scale: 50 %
   :alt: Friendly IndexError in English


The only thing that is shown in exactly the same way is the line showing
the exception name and a message.  Everything else can be made available
in other languages.


.. image:: images/friendly_indexerror_fr.png
   :scale: 50 %
   :alt: Friendly IndexError in French

.. hint::

    |france| Voir la section en français vers la fin.

Organization of this documentation
----------------------------------

This documentation has been written with many different types of
readers in mind.

The first part has been written with beginners and teachers in mind.
We have attempted to only show the most pertinent information while
giving a glimpse of more advanced features.

The third part is written with more advanced readers in mind,
and the explanations given are not as detailed.
However, **it is assumed that advanced users will have already read
and are familiar with the content of the first part** and possibly
the second part, dealing with the design of Friendly-traceback.

Detailed examples of **all** possible cases covered, using different
Python versions and/or different languages (currently only
English and French) are found in an appendix. Feel free to make
suggestions for improvements and/or suggesting additional cases
to be included.

About the version
-----------------

Typically, the version shown at the top will have the letter "a" at the end.
This means that the latest update to the documentation was made after
a release with a version number without the "a" was uploaded to Pypi,
and that we are working towards the next release.
As a result, some features shown here may be slightly different
from the version available from Pypi.


.. toctree::
   :maxdepth: 1
   :hidden:
   :caption: For beginners and teachers

   usage
   Console basics <repl>
   friendly_tb
   python_tb
   debug_tb
   thonny
   mu

.. toctree::
   :maxdepth: 1
   :hidden:
   :caption: Thoughts on design

   design


.. toctree::
   :maxdepth: 1
   :hidden:
   :caption: More advanced users

   usage_adv

.. toctree::
   :maxdepth: 1
   :hidden:
   :caption: Use in your project

   lies
   api


.. toctree::
   :maxdepth: 1
   :hidden:
   :caption: Contribute

   suggest
   adding_exception
   syntax_error
   translation_notes

.. toctree::
   :maxdepth: 1
   :hidden:
   :caption: All the tracebacks!

   known
   Friendly tracebacks - Python 3.6 in English <tracebacks_en_3.6>
   SyntaxError - Python 3.6 in English <syntax_tracebacks_en_3.6>
   Friendly tracebacks - Python 3.7 in English <tracebacks_en_3.7>
   SyntaxError - Python 3.7 in English <syntax_tracebacks_en_3.7>
   Friendly tracebacks - Python 3.8 in English <tracebacks_en_3.8>
   SyntaxError - Python 3.8 in English <syntax_tracebacks_en_3.8>
   Friendly tracebacks - Python 3.9 in English <tracebacks_en_3.9>
   SyntaxError - Python 3.9 in English <syntax_tracebacks_en_3.9>
   Friendly tracebacks - Python 3.10 in English <tracebacks_en_3.10>
   SyntaxError - Python 3.10 in English <syntax_tracebacks_en_3.10>
   compare_exceptions
   compare


.. toctree::
   :maxdepth: 1
   :hidden:
   :caption: Markdown examples

   tracebacks_markdown
   tracebacks_syntax_markdown


.. toctree::
   :maxdepth: 1
   :hidden:
   :caption: En français

   tracebacks_fr
   syntax_tracebacks_fr

.. toctree::
   :maxdepth: 1
   :hidden:
   :caption: varia

   changelog


.. todolist::
