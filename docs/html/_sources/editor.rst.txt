.. _using_editor:


Using with an editor or IDE
============================

Suppose that you are using an editor or IDE to work on a file called
``my_program.py`` and your editor has an option (perhaps from a menu or by
clicking a button)
to run ``my_program.py`` using Python. However, you'd like to
run this program with friendly's help as though it was
invoked the usual way::


    python -m friendly my_program.py
    # or
    python -im friendly my_program.py


The simplest way to do this is to create a second file
(let's call it ``friendly_run.py``) located in the same folder as
your program:

.. code-block:: none

    some_folder/
            |-------- friendly_run.py
            |-------- my_program.py


In **its simplest version**, ``friendly_run.py`` will contain the
following two lines of code::

    from friendly import run
    run("my_program.py")


Instead of executing ``my_program.py``, have your editor or IDE run
``friendly_run.py`` instead.

Depending on the editor or IDE that you use, some minor differences
may have to be included on the above, as described in the following
pages.


The above default is equivalent to executing the following:

.. code-block:: none

    python -im friendly my_program.py

which starts a friendly console at the end of the program's execution.
If you want instead the equivalent to:

.. code-block:: none

    python -m friendly my_program.py


use the following::

    from friendly import run
    run("my_program.py", console=False)


Using command line arguments
-----------------------------

Suppose you wish to run a program that expect command line arguments.
For example, you might have written a program that adds some
numbers passed as arguments on the command line:

.. code-block:: none

    $ python adder.py 1 2.5 3
    The sum is 6.5.


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

    import friendly

    friendly.run(
        "tests/adder.py",
        console=False,
        args=("1", "2.5", "3")
    )
