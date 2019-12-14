
Known exceptions
=================

.. note::

    I am currently focusing on adding more cases of ``SyntaxError``,
    and possibly ``TypeError``, rather than other other specific 
    types of exceptions, as I believe that these are the most
    likely ones to be encountered by beginners and include so 
    many different possible cases.


.. warning::

    This documentation is not updated as often as the actual 
    content of the program. 
    The content of the following two pages **is** updated 
    a lot more frequently than the rest of the documentation
    and might be a more useful reference than what is 
    written below.


In the following, those that are followed by an * had been implemented
when this page was last updated.

Those followed by ``!!``, namely ``SystemExit`` and ``KeyboardInterrupt``,
have been excluded as it seemed rather counter-productive to intercept them.

Those followed by ``#``, namely ``GeneratorExit``, ``StopIteration``,
``FloatingPointError``, and
``StopAsyncIteration``, are excluded as they should not normally be
seen by an end user - at least, not by beginners who would need
additional explanation about the meaning of such exceptions.
Furthermore, in the case of ``StopIteration``, see
`PEP 479 <https://www.python.org/dev/peps/pep-0479/>`_.

``FloatingPointError`` is actually
`not used by Python <https://docs.python.org/3.7/library/exceptions.html#FloatingPointError>`_.

``BaseException``, ``Exception``, and ``ArithmeticError`` are base classes which
are not normally seen: some derived classes are normally used instead.
They are denoted by ``**``.

.. code-block:: none
    :emphasize-lines: 8, 10, 11, 16-20, 22, 23, 33, 44-46, 48
    :linenos:

    BaseException **
     +-- SystemExit !!
     +-- KeyboardInterrupt !!
     +-- GeneratorExit #
     +-- Exception **
          +-- StopIteration #
          +-- StopAsyncIteration #
          +-- ArithmeticError **
          |    +-- FloatingPointError #
          |    +-- OverflowError *
          |    +-- ZeroDivisionError *
          +-- AssertionError
          +-- AttributeError
          +-- BufferError
          +-- EOFError
          +-- ImportError *
          |    +-- ModuleNotFoundError *
          +-- LookupError *
          |    +-- IndexError *
          |    +-- KeyError *
          +-- MemoryError
          +-- NameError  *
          |    +-- UnboundLocalError *
          +-- OSError
          |    +-- BlockingIOError
          |    +-- ChildProcessError
          |    +-- ConnectionError
          |    |    +-- BrokenPipeError
          |    |    +-- ConnectionAbortedError
          |    |    +-- ConnectionRefusedError
          |    |    +-- ConnectionResetError
          |    +-- FileExistsError
          |    +-- FileNotFoundError *
          |    +-- InterruptedError
          |    +-- IsADirectoryError
          |    +-- NotADirectoryError
          |    +-- PermissionError
          |    +-- ProcessLookupError
          |    +-- TimeoutError
          +-- ReferenceError
          +-- RuntimeError
          |    +-- NotImplementedError
          |    +-- RecursionError
          +-- SyntaxError * (partial: many more cases to include)
          |    +-- IndentationError *
          |         +-- TabError *
          +-- SystemError
          +-- TypeError * (partial: many more cases to include)
          +-- ValueError
          |    +-- UnicodeError
          |         +-- UnicodeDecodeError
          |         +-- UnicodeEncodeError
          |         +-- UnicodeTranslateError
          +-- Warning
               +-- DeprecationWarning
               +-- PendingDeprecationWarning
               +-- RuntimeWarning
               +-- SyntaxWarning
               +-- UserWarning
               +-- FutureWarning
               +-- ImportWarning
               +-- UnicodeWarning
               +-- BytesWarning
               +-- ResourceWarning
