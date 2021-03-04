Mu's REPL
==========

Mu includes a REPL that can be started by clicking on a button
with the image of a keyboard.

.. image:: images/mu_repl1.png
   :scale: 50 %
   :alt: Screen capture showing Mu's interface with the REPL started.


To use Friendly-traceback in Mu's REPL, include the following line of code::

    from friendly_traceback.mu_repl import *

Here's what it looks like.

.. image:: images/mu_repl2.png
   :scale: 50 %
   :alt: Screen capture showing Friendly-traceback's output in Mu's REPL


Future work
-----------

The REPL included in MU is known as a *Jupyter QtConsole*.
Normal tracebacks produced without using Friendly-traceback are nicely
coloured.

.. image:: images/mu_repl3.png
   :scale: 50 %
   :alt: Screen capture a normal traceback in Mu's REPL.

.. todo::

    Find a way to produce coloured output in Mu's REPL.
