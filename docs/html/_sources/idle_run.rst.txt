IDLE: using the editor
========================


Since IDLE is part of the standard library, it is often the first
editor that is used by beginners learning Python.
Let's have a look at what happens if we run
a program with IDLE using the
"Run -> Run Module" menu item.

.. image:: images/python_idle.png
   :scale: 60 %
   :alt: Screen capture of IDLE


Below, I did something similar, but using friendly
as a program launcher, and using French as the default
language. After the program's execution had been
completed, I entered more code, making a syntax error.


.. image:: images/friendly_idle.png
   :scale: 50 %
   :alt: Screen capture of IDLE using friendly to launch a program


.. admonition:: Summary

    To run a program named ``hello.py``, create a second Python
    program saved in the same directory
    and containing the following::

        from friendly.idle import run
        run("hello.py")


.. danger::

    Do not name your own program ``friendly.py``.


If you are using Python 3.10 and do not worry about syntax errors,
you can add the following at the beginning of your
module and run it as is::

    from friendly.idle import *
    install()

    # rest of your code
