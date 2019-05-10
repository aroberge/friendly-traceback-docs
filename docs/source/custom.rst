Custom exceptions and formatting
================================

In the ``demo`` directory, there are two different examples which show

- How to create your custom exceptions so that a "friendly" traceback
  can be shown.
- How to create a custom formatter; the example given creates an html file.


Example output from the custom html formatter demo
--------------------------------------------------

.. raw:: html

    <style>
    .main {color:red}
    .sub {color:blue}
    .pre2 {color:yellow; background: #321; width:600px}
    </style>
    <h2 class="main">Python exception:</h2>
    <h4>NameError: name 'a' is not defined</h4>
    <h3 class="sub">Likely cause:</h3>
    <p>In your program, the unknown name is 'a'.
    </p>
    <h4>Execution stopped on line 72 of file 'custom_formatter.py'.
    <h4>
    <pre class="pre2">       70:
           71: try:
        -->72:     b = a + c  # noqa
           73: except Exception:
    </pre>


Acknowledgement
----------------

Note that the information obtained by Friendly-traceback is collected
in a "structured" form, as suggested by Aivar Annamaa
in Issue8_ and noted in Issue10_,
so that it could be formatted differently by any program using Friendly-traceback.

.. _Issue8: https://github.com/aroberge/friendly-traceback/issues/8
.. _Issue10: https://github.com/aroberge/friendly-traceback/issues/10
