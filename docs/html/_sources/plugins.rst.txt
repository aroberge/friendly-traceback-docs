Editor plugins
===============

As mentioned in :ref:`using_editor`, one can launch a program
by writing an auxiliary file that uses ``friendly.run()``.
Perhaps your favourite editor support plugins that can replace
such auxiliary scripts by a menu item or an additional button.
If that is the case, we encourage you to do so, and let us know
so that we can make other users aware.

``friendly.run()`` makes use of another function
called ``exec_code()`` found in ``editors_helpers.py``.
This file contains additional functions that might be useful
to turn into plugins, for example enabling to check the
syntax without actually running a program.

Again, if you do so, let us know, and we will add any function
you use to the public API. In the meantime,
here's some information about these functions.


.. automodule:: friendly.editors_helpers
   :members:
