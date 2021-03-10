Public API
==========


Before getting Sphinx to document the public API automatically,
I need to let you in on a little secret:
occasionally, friendly will lie to you.
Furthermore, I encourage you to do the same.

Actually, if you have read the section
:ref:`multiple_tracebacks`, you already have seen that the
traceback shown usually does not include modules from friendly
itself.  You can do the same for your own modules
using something like the following::

    import my_module
    friendly.add_excluded_path(my_module.__file__)


Without further ado, here's the API automatically obtained
by Sphinx from the source code.


.. automodule:: friendly
   :members:

