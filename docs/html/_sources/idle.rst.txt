Introduction to IDLE
=====================

Since IDLE is part of the standard library, it is often the first
editor that is used by beginners learning Python.
It includes its own REPL (known as its "shell") and enable
users to write code in editors and run them, with the output
redirected to the shell.

Before Python version 3.10.0a5, IDLE did not allow a user to
define their own "exception hook" to modify the information shown to
a user. Since then, it is possible to have IDLE use a custom
exception hook **except** when dealing with syntax errors.
To get the most out of friendly, **I recommend to use
friendly's own console instead of IDLE's shell.**


Idle provides a few pre-defined element types to which colouring
can be applied

.. image:: images/idle_defaults.png
   :scale: 50 %
   :alt: Idle color scheme

In the default scheme:

1. The default colour is black
2. Anything "printed" normally (``print() --> sys.stdout``) is in blue
3. Anything printed following an exception (sent to ``sys.stderr``) is in red
4. IDLE uses a red background to highlight a specific position of a syntax error
   as identified by Python.

The specific colour used for each of these cases can be changed by
a user. Friendly makes use of the colours chosen for these four basic
elements when it formats the information presented to the user.
