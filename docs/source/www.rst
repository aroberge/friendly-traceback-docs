www()
============

Occasionally, friendly will not recognize an exception,
or a given message associated with that exception::

    SomeError: never seen before

In this case, you can use the function ``www()`` which will open
your default web browser and do an internet search for ``"SomeError: never seen before"``
using DuckDuckGo.

In some cases, friendly will not only recognize
the exception and the specific message, but have included a link thought
to be particularly useful. In such cases, ``www()`` will open your web browser
at the page, and possibly the exact location on that page, corresponding
to the link.

``www()`` can also take some arguments, which can change its behaviour.
You can use ``help(www)`` in a friendly console
to find out more about this function or look at the console API :ref:`console_api`
in this documentation.

Note that ``www()`` is a recent addition to friendly and that
its behaviour is subject to change based on received feedback.
