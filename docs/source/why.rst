

why()
======

You are a beginner reading some code found in a tutorial on the web
and decide to try it out by copy-pasting it.

.. image:: images/why_1.png
   :scale: 60 %
   :alt: Screen capture of syntax error

So, this didn't work, but you'd like to find out a bit more information than
that provided by the terse hint shown after the traceback.


    >>> why()
    Python indicates that you used some unicode characters not allowed as part
    of a variable name; this includes many emojis. However, I suspect that you
    used a fancy unicode quotation mark instead of a normal single or double
    quote for a string. This can happen if you copy-pasted code.

More generally, ``why()`` attempts to find the exact cause of an
exception and suggest some ways to fix the code.


Using www()
-----------

Occasionally, friendly will be unable to give you an explanation,
or you will find that the explanation it gave is not sufficient.
If that is the case, you can use ``www()`` with no arguments
to automatically open your browser and
do a search using the error message given by Python.

.. image:: images/www_ddg.png
   :scale: 60 %
   :alt: Screen capture of search using DuckDuckGo

Not always a search
-------------------

In some cases, as discussed later, instead of a search for the error message,
a specific page will be open when calling ``www()``.
