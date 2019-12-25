Usage
=====

There are various ways of using friendly-traceback.

.. note::

    In some of the examples below, we use the program ``hello.py`` found
    in the ``demos`` directory, containing the following::

        print("\nHello world!")

        if __name__ == '__main__':
            print("Running as main!")


1. As an exception hook::

    import friendly_traceback
    friendly_traceback.install()  # sys.excepthook = friendly_traceback.explain


2. Catching exceptions locally::

    import friendly_traceback

    ...

    try:
        # Some code
    except Exception:
        friendly_traceback.explain()


.. sidebar:: Important

   Note the ``.py`` extension required here, but not for other cases.


3. When launching a Python script::

    $ python -m friendly_traceback demos/hello.py

    Hello world!
    Running as main!

4. Launching the friendly console after running a script::

    $ python -im friendly_traceback demos.hello

    Hello world!
    Running as main!
    Friendly Console version 0.0.10a. [Python version: 3.7.3]

    >>>

5. Only importing a Python script::

    $ python -m friendly_traceback --import_only demos.hello

    Hello world!

6. Importing a script and starting the console::

    $ python -im friendly_traceback --import_only demos.hello

    Hello world!
    Friendly Console version 0.0.10a. [Python version: 3.7.3]

    >>>

7. Only starting the console::

    $ python -m friendly_traceback

8. Starting the console from an interpreter::

    >>> import friendly_traceback
    >>> friendly_traceback.start_console()

9. To see if there are syntax errors, with attempts to provide an
   explanation as to what they mean, in a file specified by
   its path (assumed to be relative to the current working directory)::

       import friendly_traceback
       friendly_traceback.check_syntax(path="demos/hello.py")

10. To see if there are syntax errors in some code submitted as
    a string, with an optional file name supplied::

       import friendly_traceback
       friendly_traceback.check_syntax(source=some_code, filename="hello.py")


11. Instead of simply checking the syntax, one can run the code to see
    if there are also runtime errors; this is done by calling ``run_code``
    which first calls ``check_syntax`` and will execute the code if
    no exception are raised; for example::

        import friendly_traceback
        friendly_traceback.run_code(source=some_code, filename="hello.py")


You can also specify the verbosity level as well as the language
to be used, either as command line arguments::

    $ python -m friendly_traceback --lang fr --level 5

or as optional arguments when using ``check_syntax`` or ``run_code``::

    friendly_traceback.check_syntax(..., lang='fr', level=5)

Where the output is written?
----------------------------

By default, friendly tracebacks are written to ``sys.stderr``.
However, it is possible to override this choice, as follows::

    friendly_traceback.set_stream(stream)

Thus, the default amounts to::

    friendly_traceback.set_stream(sys.stderr)

A special option exists to capture the output as a string::

    friendly_traceback.set_stream("capture")

Later, this captured output can be retrieved using::

    output = friendly_traceback.get_output()

    # equivalent to
    output = friendly_traceback.get_output(flush=True)


The value shown for the ``flush`` parameter is the default; this means that
the output will be cleared once it has been retrieved. If this is not the
desired behaviour, simply use ``flush=False``.


How much information is printed?
--------------------------------

The amount of information shown to the user can be changed using::

    friendly_traceback.set_level(level)

What each level correspond to is shown later in this documentation.
The level currently used can be obtained as follows:

    level = friendly_traceback.get_level()


Language used
-------------

The language used can be explicitly set as follows::

    friendly_traceback.set_lang("fr")  # two-letter code for French

The language currently used can be obtained using::

    lang = friendly_traceback.get_lang()

If the language requested does not exist, no error is raised nor any warning
given, but the choice reverts to the default (English).
More information on the choice of language (localization) can be found
in the section about design.

As an exception hook
---------------------

When "installing" friendly-traceback, one can use various optional
parameters::

    friendly_traceback.install(lang="fr", redirect="capture", level=1)

This is equivalent to writing::

    friendly_traceback.install()
    friendly_traceback.set_lang("fr")
    friendly_traceback.set_stream("capture")
    friendly_traceback.set_level(1)


Catching exception locally
--------------------------

As mentioned before, another way to use Friendly-traceback is to catch
exceptions where they are expected to arise, such as::


    try:
        # Some code
    except Exception:
        friendly_traceback.explain()

This uses the default of writing to ``sys.stderr``.
One can also **temporarily** redirect the output to any stream::

    try:
        # Some code
    except Exception:
        friendly_traceback.explain(redirect=stream)

By default, friendly-traceback takes its information from ``sys.exc_info()``.
It may happen that this is not what we want to show.
For example, the `showtraceback method in Python's code.py <https://github.com/python/cpython/blob/3.7/Lib/code.py#L131>`_ replaces one of the items prior to
showing the traceback to the user; we currently also do the same in
friendly-traceback's own console.  If this is something desired,
instead of ``explain()``, one can use the "private" function
``_explain()`` instead.  Ignoring optional parameters,
what we currently have is essentially the following::

    def explain():
        etype, value, tb = sys.exc_info()
        _explain(etype, value, tb)


If one wishes to temporarily change some other option mentioned above,
it can be done as in the following example::

    try:
        # Some code
    except Exception:
        lang = friendly_traceback.get_lang()
        friendly_traceback.set_lang("fr")
        friendly_traceback.explain()
        friendly_traceback.set_lang(lang)


From the command line
----------------------

The following is subject to change; this was copied from version 0.0.8a

.. code-block:: none

    $ python -m friendly_traceback -h
    usage: __main__.py [-h] [--lang LANG] [--level LEVEL] [--import_only]
                       [--version]
                       [source]

    Friendly-traceback makes Python tracebacks easier to understand.

            Note: the values of the verbosity level described below are:
                0: Normal Python tracebacks
                1: Default - does not need to be specified
                2: Python tracebacks appear before the friendly display
                3: Python tracebacks appended at the end of the friendly display.
                4: Python traceback followed by basic explanation
                5: Only basic explanation
                6: No generic explanation
                7: Python tracebacks appear before the friendly display but
                   no generic explanation is included.
                9: Python traceback

            The Python traceback for level >= 1 are the simulated version.
            You can use negative values to show the true Python traceback which
            will likely include function calls from friendly-traceback itself.
            Thus level -9 is equivalent to level 0.

            Other values may be available, as we try to find the most useful
            settings for beginners.

    positional arguments:
      source         Name of the script to be run as though it was the main module
                     run by Python, so that __name__ does equal '__main__'.

    optional arguments:
      -h, --help     show this help message and exit
      --lang LANG    This sets the language used by Friendly-tracebacks. Usually
                     this is a two-letter code such as 'fr' for French.
      --level LEVEL  This sets the "verbosity" level, that is the amount of
                     information provided.
      --import_only  Imports the module instead of running it as a script.
      --version      Displays the current version.
