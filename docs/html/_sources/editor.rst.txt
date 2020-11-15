.. _using_editor:


Using with an editor or IDE
============================

.. tip::

   To use Friendly-traceback with an editor or IDE,
   create a second file to be used as a "launcher", containing
   the following::

        from friendly_traceback import run

        run("my_program.py")

Using with IDLE
---------------

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
(sent to ``sys.stderr``), but we can still interact
with the program afterwards, with the variables
defined in the original program being available
in IDLE's console.

Let's do something similar, but using Friendly-traceback
as a program launcher.  The above program was saved
in a file named "error.py". Let's create a second
file with the following content::

    from friendly_traceback import run

    run("error.py")

The following is what happens if we run it, and do
further interactions aftewards.

.. image:: images/idle-friendly.png
   :scale: 50 %
   :alt: Screen capture of IDLE

We stil get a traceback that looks similar to Python's
standard traceback, but that has an added hint
as to what might be the cause of the exception: here
it was because we wrote ``Pi`` with an uppercase ``P``.

Like it was the case with Python running inside IDLE,
we have access to the variables that were in the program
that was run.

Notice how the prompt is blue instead of black: this is
because we are running the friendly console which uses
``print()`` or ``input()`` calls.

As shown below, we can ask for more details about
the exception, as was shown in the previous section.

.. image:: images/idle-friendly2.png
   :scale: 50 %
   :alt: Screen capture of IDLE


Using Microsoft VS Code
-----------------------

Let's do the same thing, this time using Microsoft Visual Studio Code,
using an environment in which Rich is installed.
This time, our code launcher is modified as follows::

    from friendly_traceback import run

    run("error.py", use_rich=True)

.. image:: images/vs-code.png
   :scale: 50 %
   :alt: Screen capture VS Code

Some output when the terminal starts it execution, but prior to running
our program, has been removed from the screen capture above.

As you can see, this is much more pleasant to look at then what
we see using IDLE.


Using command line arguments
-----------------------------

Suppose you wish to run a program that expect command line arguments.
Here's an example, taken from our unit tests::

    # Demonstration of a program that uses command line arguments
    import argparse

    parser = argparse.ArgumentParser()
    parser.add_argument("numbers", nargs="*", help="List of numbers to add.")

    total = 0
    args = parser.parse_args()

    for number in args.numbers:
        total += float(number)

    print(f"The sum is {total}.")


Running the program with the following code will result in
``The sum is 6.5.`` being printed::

    import friendly_traceback

    mod_dict = friendly_traceback.run(
        "tests/adder.py",
        console=False,
        args=("1", "2.5", "3")
    )
    assert "total" in mod_dict
    assert mod_dict["total"] == 6.5

