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


All of the above assume that you are using a terminal with a dark background.
If you are using a terminal with a light background, you might want to
add ``--style light`` as a command line option.


Suggestions
~~~~~~~~~~~

If you are a Windows user I **very strongly suggest** that you use the new
`Windows Terminal <https://github.com/microsoft/terminal>`_
that you can get from the Windows Store; this is
what I have used for various screen captures.
See :ref:`themes` for screenshot taken with with other terminals
on Windows.

If you are a Mac or Linux user,
and use friendly with Rich installed,
I would gladly accept any screenshot that you could provide so that they
could be included in this documentation.

If possible, friendly makes use of
`Rich <https://github.com/willmcgugan/rich>`_ to add colour to its output.
Note however that some programming environments,
such as IDLE and other IDEs do not support Rich; this does not
prevent you from using friendly, but the display
will definitely not look as nice.
The only editor/IDE capable of **fully** making use of Rich that I know
of is `Microsoft Visual Studio Code <https://code.visualstudio.com/>`_.
Jupyter notebooks and JupyterLab can also use Rich.
Pycharm's embedded console, at least on Windows, does not fully
support Rich.


Other ways
----------

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
