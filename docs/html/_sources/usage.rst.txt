Basic usage
============

There are various ways of using Friendly-traceback.
We only list here the basic scenarios available from a
terminal or from within a Python interpreter.
More options are possible, including running from an editor/IDE
as described later in this documentation.

To get started, we recommend using **one of the first three** following options.


1. Execute a Python program, as we have already shown at the beginning::

    $ python -m friendly_traceback example.py


2. You can also start a Friendly console::

    $ python -m friendly_traceback


3. Combining the two options above by using Python's ``-i`` flag
   to start Friendly-traceback's console after executing
   a program::

    $ python -im friendly_traceback example.py


If this is the first time that you are using Friendly-traceback,
we suggest that you go to the next page, ignoring the content below.


Other ways
----------



4. You can use Friendly-traceback as an exception hook::

    import friendly_traceback
    friendly_traceback.install()  # replaces the default sys.excepthook


5. Starting the console from any Python interpreter::

    >>> import friendly_traceback
    >>> friendly_traceback.start_console()


6. You can also use it to catch exceptions locally::

    import friendly_traceback

    ...

    try:
        # Some code
    except Exception:
        friendly_traceback.explain_traceback()


All of the above support additional options allowing one
to select a different language (only French for now) or
changing the information that is shown by default.

More information about various additional options is
provided later in this documentation.
As a shortcut, you can
also type ``python -m friendly_traceback -h`` in a terminal.


Suggestions
~~~~~~~~~~~

If you use Rich on Windows from a terminal,
we also **very strongly suggest** that you use the new
`Windows Terminal <https://github.com/microsoft/terminal>`_; this is
what we have used for various screen captures.
See :ref:`themes` for screenshot taken with with other terminals
on Windows.

If you are a Mac or Linux user,
and use Friendly-traceback with Rich installed,
we'd gladly accept any screenshot that you could provide so that they
could be included in this documentation.

If possible, Friendly-traceback makes use of
`Rich <https://github.com/willmcgugan/rich>`_ to add colour to its output.

Note however that some programming environments,
such as IDLE and other IDEs do not support Rich; this does not
prevent you from using Friendly-traceback, but the display
will definitely not look as nice.
The only editor/IDE capable of **fully** making use of Rich that we know
of is `Microsoft Visual Studio Code <https://code.visualstudio.com/>`_.
Pycharm's embedded console, at least on Windows, does not fully
support Rich. Jupyter notebooks and JupyterLab can also use Rich adequately
when a dark theme is used.
