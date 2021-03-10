Custom formatter
================

friendly comes with various formatters which style
the information differently based on the environment.
If the builtin formatters do not meet your need, you can design
your own and set it as a default using either::

    import friendly
    from my_module import my_formatter

    friendly.set_formatter(formatter=my_formatter)

or, from the command line:

.. code-block:: none

    python -m friendly --format path.to.my_module.my_formatter
    

Currently, a formatter must accept two arguments:

1. A dict (``info``) which contains the friendly traceback information.
   The current dict items are the following::

       items = [
            "debug_warning",
            "header",
            "message",  # The last line of a Python traceback
            "original_python_traceback",
            "simulated_python_traceback",
            "shortened_traceback",
            "suggest",
            "generic",
            "parsing_error",
            "parsing_error_source",
            "cause_header",
            "cause",
            "last_call_header",
            "last_call_source",
            "last_call_variables",
            "exception_raised_header",
            "exception_raised_source",
            "exception_raised_variables",
        ]

   New items are likely going to be added in the near future:
   is it suggested that you look at the actual code if you plan to
   create your own formatter.

.. tip::

    Use ``show_info()`` in a friendly console to see all possible items.


2. A string (``include``) which specifies which parts of the friendly
   traceback should be shown, and whose value is currently set
   using ``friendly.set_include(...)``.

The second argument _might_ change in the future. If you only plan
on making use of the traceback information compiled by friendly
and determine what to show (and in which order) on your own, to ensure
that future version of friendly will be compatible with
your formatter, we suggest the following definition::

    def my_formatter(info, **ignore):
        ....

.. automodule:: friendly.formatters
   :members:
