Basic usage
============

There are various ways of using friendly.
I only list here the basic scenarios available from a
terminal or from within a Python interpreter.
More options are possible, including running from an editor/IDE
as described later in this documentation.

For those that know how to run programs **from a terminal**,
I recommend using **one of the first three** following options.


1. Execute a Python program, as I have already shown at the beginning::

    $ python -m friendly example.py


2. You can also start a friendly console::

    $ python -m friendly


3. Combining the two options above by using Python's ``-i`` flag
   to start friendly's console after executing
   a program::

    $ python -im friendly example.py


.. sidebar:: Suggestion

    If you are a Windows user I **very strongly suggest** that you use the new
    `Windows Terminal <https://github.com/microsoft/terminal>`_
    that you can get from the Windows Store; this is
    what I have used for various screen captures.


All of the above assume that you are using a terminal with a dark background.
If you are using a terminal with a light background, you might want to
add ``--style light`` as a command line option.


More ways to use
-----------------

The following ways of using friendly are described
in more details later. I simply list them here as useful
summary for experienced Python programmers.


4. You can use friendly as an exception hook::

    import friendly
    friendly.install()  # replaces the default sys.excepthook


5. Starting the console from any Python interpreter::

    >>> import friendly
    >>> friendly.start_console()


6. You can also use it to catch exceptions locally::

    import friendly

    ...

    try:
        # Some code
    except Exception:
        friendly.explain_traceback()


All of the above support additional options allowing one
to select a different language (only French for now) or
changing the information that is shown by default.

More information about various additional options is
provided later in this documentation.
As a shortcut, you can
also type ``python -m friendly -h`` in a terminal.


Logging
--------

You can use friendly with the logging module.
Here's an example, together with the corresponding
output::

    import friendly
    import logging

    # Configure as desired before running the code
    logging.basicConfig(filename="ignore.log")
    friendly.set_lang('fr')  # Just as an example :-)

    try:
        import ignore2
    except Exception:
        friendly.explain_traceback(redirect="capture")
        # Note: friendly often remove some details from tracebacks
        # to make them more readable. This can be helpful
        # but sometimes we might also need to see the full
        # traceback in log files.
        # For example, compare the path of ignore2.py shown
        # in both tracebacks.
        log = (" Friendly traceback\n" +
                  friendly.get_output() +
                  "\n----Original traceback-----\n")
        # exc_info=True below will append the original traceback
        logging.error(log, exc_info=True)


And here's the output:

.. code-block:: none

    ERROR:root: Friendly traceback

    Traceback (most recent call last):
      File "ignore.py", line 9, in <module>
        import ignore2
      File "CWD:\ignore2.py", line 3, in <module>
        c = a / b
    ZeroDivisionError: division by zero

        Une exception de type `ZeroDivisionError` se produit lorsque vous essayez de diviser une valeur
        par zéro soit directement ou en utilisant une autre opération mathématique.

        Vous divisez par le terme suivant

             b

        qui est égal à zéro.

        L'exécution s'est arrêtée à la ligne 9 du fichier ignore.py

            7:
            8: try:
        --> 9:     import ignore2
           10: except Exception:

        Exception levée à la ligne 3 du fichier CWD:\ignore2.py.

           1: a = 1
           2: b = 0
        -->3: c = a / b
                  ^^^^^

                a:  1
                b:  0


    ----Original traceback-----
    Traceback (most recent call last):
      File "ignore.py", line 9, in <module>
        import ignore2
      File "C:\Users\andre\github\friendly\ignore2.py", line 3, in <module>
        c = a / b
    ZeroDivisionError: division by zero
