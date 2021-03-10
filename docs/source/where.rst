
where()
=======

Python traceback give information about where an exception was raised and
more. But it does so in a way that's not entirely friendly to users.
Let's look at a different example, and see how friendly
can give a bit more information about the location of the problem.


.. code-block:: python

    >>> test_4(42)

    Traceback (most recent call last):
      File "<friendly-console:10>", line 1, in <module>
        test_4(42)

           ... More lines not shown. ...

        test_2(x)
      File "<friendly-console:7>", line 2, in test_2
        test_1(x)
      File "<friendly-console:8>", line 3, in test_1
        print(arg + something + others)
    NameError: name 'others' is not defined

    Did you mean other?


By default, friendly limits the length of the traceback
shown to the user.
[If you want to see a full traceback instead, use ``python_tb()`` or
see :ref:`multiple_tracebacks` for more details.]
Still, Python tracebacks can be rather too terse looking for
beginners, making it difficult for them to grasp where the error occurred.


Let's see how ``where()`` can get a bit more information about this::

    >>> where()

    Execution stopped on line 1 of file '<friendly-console:10>'.

        -->1: test_4(42)

        test_4: <function test_4>

    Exception raised on line 3 of file '<friendly-console:8>'.

           1: def test_1(arg):
           2:     other = 3
        -->3:     print(arg + something + others)
                                          ^^^^^^

        arg: 42
        global something: 4
        print: <builtin function print>
    >>>

friendly gives detailed information about two locations
at most: where the program stopped and where the exception was
raised. It shows a few lines of code near the source of the problem,
and gives some information about what it thinks might be
relevant identifiers.
