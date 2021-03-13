Visual Studio Code
===================


The terminal included with Microsoft Visual Studio Code is capable
of making use of the syntax colouring provided by Rich. Since using
colour improves the look of the output, we recommend using
it by adding an optional argument to ``run`` as follows::


    from friendly import run

    run("error.py", formatter="dark")

.. image:: images/vs-code.png
   :scale: 45 %
   :alt: Screen capture VS Code

The above screen capture has been edited to remove some output
when the terminal starts it execution, but prior to running
our program.


Using the notebook in VS Code
-----------------------------

Visual Studio Code also supports Jupyter notebooks in exactly the
same way as described previously::

    from friendly.jupyter import *
