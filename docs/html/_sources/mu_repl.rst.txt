.. admonition:: Summary

    To use friendly with Mu's REPL, you only need to write the following,
    preferably as the first statement in the REPL::

        from friendly.mu import *

Mu's REPL
==========

Before using friendly, I will show what happens if a
syntax error is made when entering code in Mu's REPL.

.. image:: images/mu_repl3.png
   :scale: 60 %
   :alt: Screen capture a normal traceback in Mu's REPL.


I will now show you what would happens if I first import
friendly before doing anything else.

.. image:: images/mu_repl1.png
   :scale: 60 %
   :alt: Screen capture a friendly traceback in Mu's REPL

In this case, friendly gives a quick hint as to the cause
of the error. You can find out more details by using ``why()``.


.. image:: images/mu_repl2.png
   :scale: 50 %
   :alt: Screen capture with the result of why() in Mu's REPL.

