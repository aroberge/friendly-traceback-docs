Change Log
============

.. note::

    Unless otherwise noted, "with translation" means with French translation.


- Added new SyntaxError case
- Added custom formatter demo
- Improved custom exception demo

Version 0.0.7
-------------

- Bug fix

Version 0.0.6
-------------

- Added custom exception demo
- Improved formatting method
- Made it compatible with Python 3.6 and 3.8(alpha), in addition to the 3.7 default
- Added multiple cases for TypeError, with translation

Version 0.0.5
-------------

- Added different levels of verbosity
- Changed method to collect and print traceback, so that the information
  could be presented differently by other formatters.
- Moved docs to separate repository
- Added KeyError, with translation
- Added value of variables found on lines that are specific to the traceback
- Added IndexError, with translation
- Added LookupError, with translation

Version 0.0.4
-------------

- Added ImportError, with translation
- Added ModuleNotFoundError, with translation
- Added ArithmeticError, with translation
- Added a way to set the language from an environment variable
- Added a way to set the language from a .ini file
- Added many ways to find the possible cause of a SyntaxError
- Added ZeroDivisionError, with translation
- Added UnboundLocalError, with translation
- Took care of SystemExit and KeyboardInterrupt
- Reorganized tests structure
- Added TabError, with translation
- Documentation: Dealing with Syntax Errors

Version 0.0.3
-------------

- Documentation: Adding new exception
- Added console (REPL) support
- Added test for unknown exception
- Added IndentationError, with translation
- Fixed install() option with capture

Version 0.0.2
-------------

- Added support for adding full Python traceback if level is set to higher number
- Added support for extracting preferred language from locale
- Added gettext support and French translation for NameError
- Added basic documentation with Sphinx - enabled on github.io
- Added basic test structure - using pytest
- Implemented and tested two ways of processing output: writing to stderr or capturing in buffer.
- Implemented "complete" processing of single exception (NameError)

Version 0.0.1
--------------

Initial commit and upload to Pypi.
