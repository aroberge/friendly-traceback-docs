Developer: Add a new SyntaxError case
========================================

``SyntaxError``, and its subclasses, ``IndentationError`` and ``TabError``,
are particular cases in that arise when a file cannot be parsed properly
by Python. Such files cannot be imported by pytest.
In order to create test cases, we need a two-step process.

In what follows, I assume that you are already familiar with how to
add test cases for other exceptions, and **I will only focus on differences**
from the other situation.

.. note::

    **Checklist**

    The following are the required steps before a pull request.
    Each item is explained in a different section below. If you find
    the instructions unclear, please do not hesitate to reach out.

        - File an issue indicating that you are planning to work on a
          given exception.
        - Add test case

            - Add /tests/syntax/raise_syntax_errorXX.py
            - Modify /tests/syntax/catch_syntax_error.py to include this new case
        
        - Add generic information
        - Add specific information
        - Execute catch_some_exception.py and confirm visually it works as expected
        - Run pytest and confirm that your new test is included
        - Make a pull request


    The following are additional **optional** steps, 
    dealing with the documentation
    rather than the code itself.
    They will need to be done at some point
    but, apart for possible translations in languages other than French,
    I can definitely take care of this.


        - Ensure that you have a copy of the friendly-traceceback-docs 
          repository; it should be located at the same directory level
          as Friendly-traceback on your computer.
        - Add case to tests/tb_syntax_common.py

            - Run tests/tb_english.py and ensure that
              ``../friendly-traceceback-docs/docs/source/tracebacks_en.rst``
              shows the expected result for all Python versions.
        - Run make_tb.bat or do the equivalent on non Windows computer
        - Confirm that all docs/tracebacks_xx.rst include the new exception
        - Add translation


Adding a test case
------------------

After you have filed an issue indicating that you wished to
adding coverage for an exception that is not previously
covered, you need to start by adding a test case.
As an example throughout, I will use the existing one for
``raise_indentation_error1.py``.

Note that tests for these exceptions are found in the tests/syntax/ directory.

Raising an exception
~~~~~~~~~~~~~~~~~~~~~

Your test file name should start with ``raise_``,
such as ``raise_indentation_error1.py``.
Here is the content of that file::

    '''Should raise IndentationError'''

    if True:
    pass


As you can see, it contains invalid code.

For this project, pytest has been configured such that it only
includes files whose names begin with ``test_`` or ``catch_``.
Therefore, it will ignore this file.

You can nonetheless test it directly, by doing:

.. code-block:: none

    python -m friendly_traceback tests/syntax/raise_indentation_error1.py

from the root directory of the repository.

Catching an exception
~~~~~~~~~~~~~~~~~~~~~

Now that we have script that can raise an exception,
we need to create a script that will catch it, and can
also be used by pytest which we use as our test runner.
Here's only part of the content of ``catch_name_error.py``,
with some numbered comments added, to which we refer below::

    import friendly_traceback
    import sys


    def test_indentation_error1():
        try:
            try:
                from . import raise_indentation_error1  # 1 for pytest
            except ImportError:
                import raise_indentation_error1
        except Exception:
            friendly_traceback.explain(*sys.exc_info(), redirect="capture")
        result = friendly_traceback.get_output()
        assert "IndentationError: expected an indented block" in result  # 2
        return result


    if __name__ == "__main__":
        print(test_indentation_error1())


1. Importing a test using pytest is done differently than importing it when
   running this file as standalone
2. There are three possible cases of ``IndentationError``. We try to be
   as specific as possible in terms of which case will be indicated by Python.

At this point, running pytest from the root directory should
work, and you should see your test case included.  You can also
run this test directly, using::

    python tests/syntax/catch_indentation_error.py


Adding generic information
--------------------------

This has already been done for ``SyntaxError`` and its subclasses.
Feel free to suggest improvements to the explanation given.

Add specific information
------------------------

This is the tricky part.

The three possible causes of ``IndentationError`` are already covered;
this is also the case for ``TabError``.

For ``SyntaxError``, we actually need to get access to the offending
code, analyze it and see if we can make an educated guess as to the
cause of the error and give proper feedback. This is done in a 
separate module, ``analyze_syntax.py``.  
Adding support for a new case is often not straightforward.
If you wish to do so, I suggest you actually look at the code 
in that module: any attempt at adding something useful in this
documentation would likely be doomed to be hopelessly out of 
date and possibly misleading.
