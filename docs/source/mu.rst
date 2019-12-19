Using with Mu
=============

.. sidebar:: What about Thonny or IDLE?

    Unfortunately, because IDLE and Thonny use their own 
    quirky ways to run execute programs, the approach described
    here to use Friendly-traceback is not possible with them.

`Mu <https://codewith.mu/>`_ is a fantastic editor for beginners.
In the future, when Friendly-traceback is a bit more mature,
it appears very likely that Mu will incorporate
Friendly-traceback natively. 
For now, it is nonetheless possible to use
Friendly-traceback productively with Mu by of adding 
a single line at the top of the program to be execute. 
This is described below. But first, one has to 
install Friendly-traceback in Mu's environment.

Installation
------------

I assume that you have installed Mu on your computer.
Mu picks up the language to use from the computer default settings,
which explains why French appears on the screen capture below. 

After you start it, you should see a gear icon at the bottom right
corner.

.. image:: images/mu.png
   :scale: 50 %
   :alt: Mu

If you click on it, it will bring the following dialog.

.. image:: images/mu_dialog1.png
   :alt: Mu dialog

Click on the triangular "arrow" until the Third Party Packages tab is shown.

.. image:: images/mu_dialog2.png
   :alt: Mu dialog

Enter "friendly-traceback" and click "ok".  Friendly-traceback should
be installed. Version 0.0.26 or newer is required.
Note that until version 0.1 is released, Friendly-traceback is considered
pre-alpha, and anything you see in this documentation could be 
rapidly obsolete.

.. image:: images/mu_dialog3.png
   :alt: Mu dialog

Before using Friendly-traceback with Mu 
----------------------------------------

I have created a test module, called test_problem.py, that raises
and exception.
First, I show what happens when I run test_problem.py with Mu.

.. image:: images/test_problem.png
   :scale: 50 %
   :alt: Mu running test_problem

Using Friendly-traceback with Mu
--------------------------------

To use Friendly-traceback with Mu, I need to add one line 
of code at the top, and run it as usual.


.. image:: images/test_problem_friendly.png
   :scale: 50 %
   :alt: Mu with friendly running test_problem

As should be expected, a friendlier traceback is shown.


.. note::

    You can copy the required line from this::

        from friendly_traceback import explanations
        
    This is equivalent to the following::

        import friendly_traceback
        friendly_traceback.install()



You likely will not be surprised to know that 
I can ask Friendly-traceback to provide explanations in French instead:

.. image:: images/test_problem_fr.png
   :scale: 50 %
   :alt: Mu with friendly running test_problem

The single line of code at the top is equivalent to the following::

    import friendly_traceback
    friendly_traceback.install(lang="fr")


Ideally, more languages would be supported. 
