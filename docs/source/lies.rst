Learn to lie
================

Let me let you in on a secret:
occasionally, Friendly-traceback will lie to you.
And I encourage you to do the same.

Actually, if you have read the section
:ref:`multiple_tracebacks`, you already have seen that the
traceback shown usually does not include modules from Friendly-traceback
itself.  You can do the same for your own modules
using something like the following::

    import my_module
    friendly_traceback.add_excluded_path(my_module.__file__)

