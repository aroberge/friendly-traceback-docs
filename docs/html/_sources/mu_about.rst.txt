About Mu
==========

`Mu <https://codewith.mu/>`_ is a fantastic editor for absolute beginners.
Its design philosophy is to enable beginners to download a single
program that comes with everything they need to begin their programming
journey.

You can use Mu to program in different environments known as "modes".
Note that Mu uses the default language for the computer, which explains
why all the screenshots I include are in French. It is currently
not possible to (easily) change the language used for Mu's menu items.

.. image:: images/mu_modes.png
   :scale: 60 %
   :alt: Mu modes

**friendly** has only been tested with the Python 3 mode.
It should work when using the Pygame zero or the Web mode.


.. warning::

    Unfortunately, I am not able at present to provide any support
    for the other modes (BBC micro:bit, CircuitPython, ESP MicroPython).


Two ways to use Python
-----------------------

Using the Python 3 mode, there are two ways to execute Python code:

1. Using a "run" button to execute code saved in a file.
2. Using a REPL to execute code interactively.

.. image:: images/mu_ui1.png
   :scale: 50 %
   :alt: Mu basic user interface

Running a program in the editor
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

First, I show what happens using the "run" method.

.. image:: images/mu_ui2.png
   :scale: 50 %
   :alt: Mu basic user interface - running a program


After clicking on the "run" button, the icon (1) changes to an "X".
The code in the editor (2) is executed and the result is
shown in the output pane (3) where we can continue entering commands.

Using the REPL
~~~~~~~~~~~~~~~


.. image:: images/mu_ui3.png
   :scale: 50 %
   :alt: Mu basic user interface - using the REPL

After clicking on the REPL button (1), a panel (2) opens where you can
enter Python code (3). If you have a file saved (4) in the editor,
you can use the ``import`` statement (5) and have its code executed
in the REPL.


.. warning::

    The REPL used by Mu is a well-known Python interpreter which
    has been created by a different group of developers.
    It has at least one bug which I have reported: if you write code
    with an extra closing ``)``, it is not interpreted as a ``SyntaxError``
    but behaves as though more code is expected to have a complete
    statement.

    .. image:: images/ipython_bug.png
       :scale: 60 %
       :alt: IPython bug
