.. _adding_exception:

Developer: Add a new Exception case
======================================

This primarily describes the situation where you wish to add friendly
tracebacks for an Exception that is not already included.
**It does not apply to** ``SyntaxError`` **and its subclasses,**
``IndentationError`` and ``TabError``, **which need to be dealt separately.**

.. note::

    Any contribution, **no matter how small**, is welcome.
    The following checklist
    is provided for those that are ambitious and want to do all the required
    steps by themselves to include a new case.
    You definitely do not have to do all of this.

    **Checklist**

    The following are the include all the steps that have to be done
    to consider that a new case has been completely covered.
    Most individual steps are explained in a different section below.
    If you find the instructions unclear, please do not hesitate to reach out.

        - File an issue indicating that you are planning to work on a
          given exception. This should be done if you are planning to
          submit something within a week or so.
        - Add /tests/except/test_new_error.py
        - Run pytest with one of Python's supported versions (3.6 to 3.9)
          and confirm that your new test is included
        - Add generic information about this Exception
        - Add specific information about this Exception
        - Add another assertion in test case, to be run if the language
          is English, that confirms that (part of) the specific information
          is included in the traceback
        - Execute test_new_error.py and confirm visually it works as expected
        - Run pytest and confirm that your new test is included
        - For completeness, you could check to see that all this works
          properly with all supported Python versions: sometimes the text
          of the message changes from one Python version to another.


    After completing any of the steps above (other than the first one),
    feel free to make a pull request so that your code can be included.
    If you want to contribute and do not know how to do a pull request,
    or find it too complicated, please contact me: we'll find a way to help you
    contribute.


    The following are additional steps, dealing with the documentation
    rather than the code itself.
    They will need to be done at some point
    but, apart for possible translations in languages other than French,
    it is usually something that I do myself. As I do not expect
    contributions for this, I did not include detailed explanations of
    each steps. Let me know if you'd like to work on this and need
    more details.


        - Ensure that you have a copy of the friendly-traceceback-docs
          repository; it should be located at the same directory level
          as friendly-traceback on your computer.
        - Add case to tests/tb_common.py

            - Run tests/tb_english.py and ensure that
              ``../friendly-traceceback-docs/docs/source/tracebacks_en.rst``
              shows the expected result for all Python versions.
        - Run make_tb.bat or do the equivalent on non Windows computer
        - Confirm that all docs/tracebacks_xx.rst include the new exception
        - Add translation; currenly only French is supported.

Adding a test case
------------------

After you have filed an issue indicating that you wished to
adding coverage for an exception that is not previously
covered, you need to start by adding a test case.
As an example throughout, I will use the existing one for
``UnboundLocalError``. I am documenting the process as I go through.

In this project, we use `pytest <https://docs.pytest.org/en/latest/>`_ and
simple assertion-based tests.

For named exceptions, test files are located in the ``tests/except`` directory.
Your test file name should start with ``test_``,
such as ``test_unbound_local_error.py``.
Here is what was the **initial** content of that file,
with some numbered comments added::

    import friendly_traceback
    import sys


    def test_unbound_local_error():    # 1
        """Should raise UnboundLocalError"""
        a = 1

        def inner():
            a += 1

        try:
            inner()   # 2
        except Exception:
            friendly_traceback.explain(*sys.exc_info(), redirect="capture")  # 3
        result = friendly_traceback.get_output()  # 4
        assert "UnboundLocalError" in result  # 5
        return result  # 6


    if __name__ == "__main__":
        print(test_unbound_local_error())  # 7


1. Test functions should start with `test_`, so as to be recognized by pytest.
   I like to use a name written that reflects the name of the exception,
   replacing any uppercase letter in the exception name by an underscore
   followed by a lowercase version of the letter.
2. The code raising an error is inserted in a try/except clause.
   Friendly-traceback can be installed globally as an exception hook but
   this would not work when using pytest. **Important:** unless there is no
   other way, you should not trigger an exception by an explicit call
   using the ``raise`` keyword, so that the message included is produce
   by Python and not artificially written. Whenever possible, friendly-traceback
   provides some specific information about an exception based on the content
   of the message included by Python.
3. By default, friendly_traceback outputs its result to sys.stderr.
   However, this can be redirected to any other user provided
   function. In addition, there is a "capture" mode, as indicated,
   which simply stores the result.
4. To retrieve the previously stored result, we use the
   ``get_output()`` method. By default, this method also empties
   the cache used to capture the output. There is an optional
   argument to change this behaviour but it would be counter
   productive in this situation as we wish our tests to be done
   independently.
5. Pytest checks for assertion errors. So, we include parts of
   what we expect to see in the output. This is usually the
   beginning of the line just below ``Python exception:`` that
   was shown when running something like ``raise_myexception.py``
   previously. For reliability, we should include more than
   just the name of the Exception. Just leave any information
   about the line and file number out, to avoid making the tests
   brittle if we were to change either.
6. We must return the previously captured result for independent
   testing.
7. This enables us to run this test by itself, without Pytest.

So, let's see what happens if we do run this test by itself.

.. code-block:: none

    $ python tests/except/test_unbound_local_error.py

        Python exception:
           UnboundLocalError: local variable 'a' referenced before assignment

        No information is known about this exception.


        Execution stopped on line 15 of file 'test_unbound_local_error.py'.

           13:
           14:     try:
        -->15:         inner()
           16:     except Exception:


        Exception raised on line 12 of file 'test_unbound_local_error.py'.

           10:
           11:     def inner():
        -->12:         a += 1
           13:

Note the line:

.. code-block:: none

    No information is known about this exception.

We will soon want to correct this. However, before we do so,
in order to make our test more accurate, we replace the line::

    assert "UnboundLocalError" in result

by::

    assert "UnboundLocalError: local variable 'a' referenced before assignment" in result


Running with pytest
-------------------

This assumes that pytest is installed on your computer.
From Friendly-traceback's root directory, simply run::

    python -m pytest

You should see your test file listed, and no test failures reported by pytest.

Adding generic information
--------------------------

The main goal of friendly_tracebacks is to help beginners and/or
programmers whose knowledge of English is limited,
to understand what a given exception means.
So, your first goal is to imagine that you are helping a beginner
understand what ``SomeException`` means, writing in English with
as little Python-specific jargon as possible.  Try to do
so in a short paragraph. Do not strive for perfection.
It is expected that we will hear from actual users
(teachers and students) using friendly_tracebacks and that we
will be able to improve the descriptions based on their feedback,
and not based on our own pre-conceptions.

Generic information about given exceptions is found in file
``friendly_traceback/info_generic.py``.
Here are the relevant parts of that file for the UnboundLocalError
exception, followed by some explications::

    @register("UnboundLocalError")
    def unbound_local_error(*args):
        _ = current_lang.lang
        return _(
            "In Python, variables that are used inside a function are known as \n"
            "local variables. Before they are used, they must be assigned a value.\n"
            "A variable that is used before it is assigned a value is assumed to\n"
            "be defined outside that function; it is known as a 'global'\n"
            "(or sometimes 'nonlocal') variable. You cannot assign a value to such\n"
            "a global variable inside a function without first indicating to\n"
            "Python that this is a global variable, otherwise you will see\n"
            "an UnboundLocalError.\n"
        )

This generic explanation is rather long.
As mentioned before, if possible, you should make it
as short as possible while giving enough information so that a beginner
would understand what such an exception means.

We use gettext for providing translations. You do not need to be
familiar with gettext for this doing this work.
For those that are familiar with gettext, the most common way
to use it is to **install** it globally, so that the function ``_``
is added to Python's builtins and can be used everywhere.
However, this conflicts with using ``_`` in the console (REPL) as
the value of the last command; for this reason, we use ``_``
as a local variable inside any function which contains some strings
to be translated.

We first define a function whose name reflects the exception
we wish to explain.
This is not strictly required but it makes it easier to find the
information when looking at the code. Thus, for ``UnboundLocalError``,
we defined ``unbound_local_error()``.
We use ``register`` as a decorator to add it to the known
cases automatically.
This function will receive some positional arguments that
may be useful for some exceptions.  For the first run through, you can
assume that you can ignore these arguments.

Ideally, this function should be inserted sorted alphabetically
in the file.

The first line of the function is::

    _ = current_lang.lang

This ensures that translations done by gettext are handled correctly.

Next, we return a string enclosed by ``_( )``; this is a call to
gettext to retrieve the correct translation.

For clarity, instead of using triple-quoted strings, we use Python's
automatic concatenation of adjacent strings to format the text.
Experience has shown us that this makes it much easier to
write the corresponding translations using Poedit, as described elsewhere.
Each string should represent a single line of text, and end with
a single ``\n``.


Add specific information
------------------------

.. note::

    In some cases, it could happen that no specific information, as
    described below, is needed. In this case, you should still define
    a function for the specific information, so that we know it has
    not been overlooked, but have that function simply return ``None``.

Let's look again at the output for UnboundLocalError.
At the top of the feedback given by friendly_traceback, we
see the following:

.. code-block:: none

    Python exception:
        UnboundLocalError: local variable 'a' referenced before assignment

The second line is the information given by Python.
Your goal should be to rephrase this information in a way that
is possibly easier to understand by beginners **and** which can
be translated into languages other than English.
It should also follow naturally from your generic information.

In some cases, such as ``SyntaxError``, we might need the actual
source code in order to provide some very specific information.
For now, we assume here that this is not the case.

Examining the line ``UnboundLocalError: local variable 'a' referenced before assignment``, we
see that it refers to a variable name, ``a``, which will almost
certainly be different when another user encounters a similar error.
Thus, our specific information should probably include this as a variable.

Specific information about given exceptions is found in file
``friendly_traceback/info_specific.py``.
Here are the relevant parts of that file for the UnboundLocalError
exception::

    @register("UnboundLocalError")
    def unbound_local_error(etype, value):
        _ = current_lang.lang
        # value is expected to be something like
        #
        # UnboundLocalError: local variable 'a' referenced before assignment
        #
        # By splitting value using ', we can extract the variable name.
        return _("The variable that appears to cause the problem is '{var_name}'.\n"
                 "Try inserting the statement\n"
                 "    global {var_name}\n"
                 "as the first line inside your function.").format(
            var_name=str(value).split("'")[1]
        )

I assume that this is similar enough to the situation for the
generic information case that it does not warrant additional
explanation.

If you find that some additional explanation is needed,
please contact me or file an issue.

Add another assertion
---------------------

To ensure that Friendly-traceback does not misidentify a given case,
include another assertion in the test,
this one based on the specific information given in your test case.
This test should not pass simply based on the
information given by Python: it should rely on the specificity of the
explanation you provide.  In the example I give above, the additional
assertion is::

    assert "The variable that appears to cause the problem is 'a'." in result

To ensure that this will not cause problems when creating sample tracebacks
for languages other than English, we make sure to check this assertion
only if the language set is English.

And here, after quite a few revisions,
is the **final** content of that file, where the initial
single very basic assertion has been replaced by two longer ones.
While this was not necessary, I also moved the offending Python code out
of the test function, and made is slightly more complicated as it
gave a more interesting traceback, showing the values of
local and global variables, which was not something
that could be done when I first created this example::

    # More complex example than needed - used for documentation
    import friendly_traceback

    b = 2

    def outer():
        a = 1

        def inner():
            c = 3
            a = a + b + c
        inner()


    def test_unbound_local_error():
        """Should raise UnboundLocalError"""

        try:
            outer()
        except Exception:
            friendly_traceback.explain(redirect="capture")
        result = friendly_traceback.get_output()
        assert "UnboundLocalError: local variable 'a' referenced" in result
        if friendly_traceback.get_lang() == 'en':
            assert "The variable that appears to cause the problem is 'a'." in result
        return result

    if __name__ == "__main__":
        print(test_unbound_local_error())


The following is the output for this revised example::

    Python exception:
        UnboundLocalError: local variable 'a' referenced before assignment

    In Python, variables that are used inside a function are known as
    local variables. Before they are used, they must be assigned a value.
    A variable that is used before it is assigned a value is assumed to
    be defined outside that function; it is known as a 'global'
    (or sometimes 'nonlocal') variable. You cannot assign a value to such
    a global variable inside a function without first indicating to
    Python that this is a global variable, otherwise you will see
    an UnboundLocalError.

    Likely cause based on the information given by Python:
        The variable that appears to cause the problem is 'a'.
        Perhaps the statement
            global a
        should have been included as the first line inside your function.

    Execution stopped on line 20 of file 'tests\except\test_unbound_local_error.py'.

       18:
       19:     try:
    -->20:         outer()
       21:     except Exception:

    global outer: <function outer>

    Exception raised on line 12 of file 'tests\except\test_unbound_local_error.py'.

       10:     def inner():
       11:         c = 3
    -->12:         a = a + b + c
       13:     inner()

    global b: 2
    c: 3



.. important::

    Each test case should contain at least two distinct assertions:

    1. One based on the information given by Python about the exception.
    2. One or more based on the specific information information provided by
       Friendly-traceback. These should be only checked if the language
       is set to English (``'en'``)


Test your work
--------------

Now that you have added the generic and specific information,
you might want to test again by running something like::

    python tests/except/test_my_exception.py

and confirm that the result is acceptable.

Once this is done, run pytest once again from the root directory to make
sure that your new case is included correctly in the test suite.

Make a pull request
--------------------

Before submitting your code, with the possible exception of test cases,
you should make sure that your code
is formatted correctly according to `black <https://github.com/ambv/black>`_

However, we ask that you ensures that your added text
uses the one-line-per-string format described above.
If black reformats your code such that this is not the case, you
can temporarily turn it off and back on around the relevant
code.  Here's an example that we currently have in our code::

    # fmt: off
    return _(
        "\n"
        "Python exception: \n"
        "    {name}: {value}\n"
        "\n"
        "{explanation}"
    ).format(name=name, value=value, explanation=explanation)
    # fmt: on

Next, you should make sure that your local repository is up to date
and fix any conflict that might be arising.

Finally, you can proceed with a `pull request <https://help.github.com/en/articles/creating-a-pull-request>`_.
If the information provided in that link is not clear, please do
not hesitate to ask for clarification.
