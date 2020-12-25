Installation and basic usage
=============================

.. hint::

    |mu_logo| If you use Mu, you should skip this and go to :ref:`mu_instructions`.

.. |mu_logo| image:: images/mu_logo.png


.. hint::

    |thonny_logo| If you use Thonny, you should skip this and go to :ref:`using_thonny`.

.. |thonny_logo| image:: images/thonny_logo.png


Installation
-------------

You can install Friendly-traceback from Pypi in the usual way::


    python -m pip install friendly-traceback


Suggestions
~~~~~~~~~~~

If possible, Friendly-traceback makes use of 
`Rich <https://github.com/willmcgugan/rich>`_.

Note however that some programming environments,
such as IDLE and other IDEs do not support Rich; this does not
prevent you from using Friendly-traceback, but the display
will definitely not look as nice.
The only editor/IDE capable of **fully** making use of Rich that we know
of is `Microsoft Visual Studio Code <https://code.visualstudio.com/>`_.
Pycharm's embedded console, at least on Windows, does not fully
support Rich. At present, Jupyter notebooks can potentially use
Rich partially.

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


Usage
-----

There are various ways of using Friendly-traceback.
We only list here the basic scenarios available from a
terminal or from within a Python interpreter.
More options are possible, including running from an editor/IDE
as described later in this documentation.


1. Execute a Python program::

    $ python -m friendly_traceback hello.py


2. Start the friendly console::

    $ python -m friendly_traceback


3. Combining the two options above by using Python's ``-i`` flag
   to start Friendly-traceback's console after executing
   a program::

    $ python -im friendly_traceback hello.py


4. As an exception hook::

    import friendly_traceback
    friendly_traceback.install()  # replaces the default sys.excepthook


5. Starting the console from an interpreter::

    >>> import friendly_traceback
    >>> friendly_traceback.start_console()


6. Catching exceptions locally::

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

