Visual Studio Code
===================


The terminal included with Microsoft Visual Studio Code is capable
of making use of the syntax colouring provided by Rich. Since using
Rich greatly improves the look of the output, we recommend using
it by adding an optional argument to ``run`` as follows::


    from friendly_traceback import run

    run("error.py", use_rich=True)

.. image:: images/vs-code.png
   :scale: 50 %
   :alt: Screen capture VS Code

The above screen capture has been edited to remove some output
when the terminal starts it execution, but prior to running
our program.


Using the notebook in VS Code
-----------------------------

.. todo:: add info about using notebook in VS Code

