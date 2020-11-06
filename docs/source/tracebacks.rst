Multiple tracebacks
====================

Friendly traceback with hint
-----------------------------

``friendly_tb()``, that includes ``hint()``


Python traceback
----------------

``python_tb()``


True Python traceback
---------------------

Talk about ``debug_tb()``


Recursion example
------------------

Consider the following::

    def a():
        b()

    def b():
        a()

    a()

Try running this using Python. Not only will you get a
``RecursionError`` but you'll get something like 2000 lines included.
This is not exactly user friendly.  It is also what
would be shown if we used ``debug_tb()``. Let's skip this, and
only look at the output from the other two tracebacks, starting
with ``friendly_tb()`` which is shown by default.
