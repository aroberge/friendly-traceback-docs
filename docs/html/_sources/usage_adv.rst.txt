Other details for advanced users
=================================

.. note::

    Some additional information might be available from the command line::

       python -m friendly -h


Where the output is written?
----------------------------

By default, friendly tracebacks are written to ``sys.stderr``.
However, it is possible to override this choice, as follows::

    friendly.set_stream(stream)

Thus, the default amounts to::

    friendly.set_stream(sys.stderr)

A special option exists to capture the output as a string::

    friendly.set_stream("capture")

Later, this captured output can be retrieved using::

    output = friendly.get_output()

    # equivalent to
    output = friendly.get_output(flush=True)


The value shown for the ``flush`` parameter is the default; this means that
the output will be cleared once it has been retrieved. If this is not the
desired behaviour, simply use ``flush=False``.



Language used
-------------

.. sidebar::  Supported languages

    Currently, only English and French are available.
    Additional translations are more than welcome.

The language used can be explicitly set as follows::

    friendly.set_lang("fr")  # two-letter code for French

The language currently used can be obtained using::

    lang = friendly.get_lang()

If the language requested does not exist, no error is raised nor any warning
given, but the choice reverts to the default (English).
More information on the choice of language (localization) can be found
in the section about design.

As an exception hook
---------------------

When "installing" friendly, one can use various optional
parameters::

    friendly.install(lang="fr", redirect="capture", include="explain")

This is equivalent to writing::

    friendly.install()
    friendly.set_lang("fr")
    friendly.set_stream("capture")
    friendly.set_include("explain")


Catching exception locally
--------------------------

As mentioned before, another way to use friendly is to catch
exceptions where they are expected to arise, such as::


    try:
        # Some code
    except Exception:
        friendly.explain_traceback()

This uses the default of writing to ``sys.stderr``.
One can also **temporarily** redirect the output to any stream::

    try:
        # Some code
    except Exception:
        friendly.explain_traceback(redirect=stream)

By default, friendly takes its information from ``sys.exc_info()``.
It may happen that this is not what we want to show.
For example, the `showtraceback method in Python's code.py <https://github.com/python/cpython/blob/3.7/Lib/code.py#L131>`_ replaces one of the items prior to
showing the traceback to the user; we currently also do something similar in
friendly's own console.

Finally, if one wishes to *temporarily* change some other option mentioned above,
it can be done as in the following example::

    try:
        # Some code
    except Exception:
        lang = friendly.get_lang()
        friendly.set_lang("fr")
        friendly.explain_traceback()
        friendly.set_lang(lang)


Running another script
----------------------

We have already given an example of running another script::

    $ python -m friendly demos/hello.py

    Hello world!
    Running as main!

What if the separate script has its own command line arguments?
If they are simply positional arguments, you can simply tack them
on at the end of the argument list. An example can be found
in the ``demos/`` directory, which can be run directly or using
friendly.

.. code-block::

    $ python demos/adder.py 1 2 3
    The sum is 6

.. code-block::

    $ python -m friendly demos/adder.py 1 2 3
    The sum is 6.0

Note that this works even if you specify command line arguments
that are specific to friendly::

    $ python -m friendly --lang fr demos/adder.py 1 2 3
    The sum is 6.0

However, what if one wants to run a script that uses optional named arguments
similarly to how friendly can use ``--lang`` and other optional
arguments? In this case, use ``--`` to separate the list of arguments
to be used by the script from those written previously and
intended to be used by friendly::

    $ python -m friendly --lang fr demos/adder.py -- --to_int 1 2 3
    The sum is 6

An alterative is to use either a ``sitecustomize.py``
or a ``usercustomize.py`` file, as described in the
`Python documentation <https://docs.python.org/3/library/site.html>`_.

For example, you can use the following approach.

1. Create a ``usercustomize.py`` file whose content is the following::

    import friendly
    friendly.install()
    # specify other desired options here

2. Set the ``PYTHONPATH`` environment variable to that directory.
   On Windows, this can be done by navigating to that directory
   and writing::

       set PYTHONPATH=%CD%

You can now run your script normally: friendly exception
handling will be used by default on it.
