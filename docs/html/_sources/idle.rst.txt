IDLE: using the editor
========================


Since IDLE is part of the standard library, it is often the first
editor that is used by beginners learning Python.
Let's have a look at what happens if we run
the following program with IDLE using the
"Run -> Run Module" menu item.

.. code-block:: python

    from math import *

    y = 1
    x = cos(Pi)

.. image:: images/idle.png
   :scale: 50 %
   :alt: Screen capture of IDLE


The information about the error is written in red
(sent to ``sys.stderr``), but you can still interact
with the program afterwards, with the variables
defined in the original program being available
in IDLE's console.

Let's do something similar, but using Friendly-traceback
as a program launcher.  The above program was saved
in a file named "error.py". Let's create a second
file with the following content::

    from friendly_traceback import run

    run("error.py")

The following is what happens if I run it, and do
further interactions aftewards.

.. image:: images/idle-friendly.png
   :scale: 50 %
   :alt: Screen capture of IDLE

I stil get a traceback that looks similar to Python's
standard traceback, but that has an added hint
as to what might be the cause of the exception: here
it was because I wrote ``Pi`` with an uppercase ``P``.

Like it was the case with Python running inside IDLE,
I have access to the variables that were in the program
that was run.

Notice how the prompt is blue instead of black: this is
because I am running the friendly console which uses
``print()`` or ``input()`` calls.

As shown below, I can ask for more details about
the exception, as was shown in the previous section.

.. image:: images/idle-friendly2.png
   :scale: 50 %
   :alt: Screen capture of IDLE
