

why()
======

You read some interesting code found in a tutorial on the web
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

When you call ``why()``, **friendly** attempts to analyze the code you
entered and figure out what exactly went wrong, and quite often makes
suggestions as to how to fix it.

