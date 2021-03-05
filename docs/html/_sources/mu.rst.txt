
Using with Mu
=============


Before using Friendly-traceback with Mu
----------------------------------------

I have created a test module, called test.py, that raises
and exception.
First, I show what happens when I run test.py with Mu.

.. image:: images/test_problem.png
   :scale: 50 %
   :alt: Mu running test_problem

Using Friendly-traceback with Mu
--------------------------------

To use Friendly-traceback with Mu, I need to use a second,
very short program, and run that program instead::

    from friendly_traceback.mu import run
    run("test.py")

.. image:: images/test_problem_friendly.png
   :scale: 60 %
   :alt: Mu with friendly running test_problem

As should be expected, a traceback is shown, with a hint added.
By typing ``why()`` at the prompt, Friendly-traceback gives me
more information.


You likely will not be surprised to know that
I can ask Friendly-traceback to provide explanations in French instead:

.. image:: images/test_problem_fr.png
   :scale: 60 %
   :alt: Mu with friendly running test_problem


.. todo::

    Find a way to produce coloured output in Mu's REPL after code execution.
    Note that **this REPL** is not a Jupyter QtConsole, unlike what was shown
    about Mu's REPL before.
