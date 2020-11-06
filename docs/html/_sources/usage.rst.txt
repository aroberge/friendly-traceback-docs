Installation and basic usage
=============================

.. hint::

    |mu_logo| If you use Mu, you should skip this and go to :ref:`mu_instructions`.

.. |mu_logo| image:: images/mu_logo.png



Installation
-------------

You can install Friendly-traceback from Pypi in the usual way::


    python -m pip install friendly-traceback


If the environment in which you plan to use Friendly-traceback
supports `Rich <https://github.com/willmcgugan/rich>`_, we
strongly suggest you install Rich so that Friendly-traceback
can make use of it by default. However, some programming environments,
such as IDLE and other IDEs do not support Rich.
The only editor/IDE capable of making use of Rich that we know
of is `Microsoft Visual Studio Code <https://code.visualstudio.com/>`_.

If you use Rich on Windows from a terminal,
we strongly suggest that you use the new
`Windows Terminal <https://github.com/microsoft/terminal>`_; this is
what we have used for various screen captures.


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
        friendly_traceback.explain()


All of the above support additional options allowing one
to select a different language (only French for now) or
changing the information that is shown by default.


More information about various additional options is
provided later in this documentation.
As a shortcut, you can
also type ``python -m friendly_traceback -h`` in a terminal.

