.. _using_repl:

Console basics
===============

.. sidebar:: Using screenshots

    Below, we occasionnally use some screenshots, done in a Rich-friendly
    console, but we also write some examples as text so that they
    can provide the required information to people relying on screen readers.
    If you are such a user and need help because the use of screenshots
    prevents you from understanding the explanations, please do not hesitate to
    reach out to me: andre.roberge@gmail.com

As a rule, I do not recommend that beginners write their programs
in a console (repl) but that they use an editor instead or a
notebook environment as it is easier to edit and correct mistakes.
However, using a console is useful to demonstrate various
features of Friendly-traceback which can be made available
in many editor/IDE environments.
Furthermore, the combination of using an editor and a console
can be quite useful.

The example I will be using is the same as the one shown on the
first page of this documentation: I have a file with the
following content::

    # example.py
    def get_last(seq):
        last_index = len(seq)
        return seq[last_index]

    print(get_last([1, 2, 3]))

However, instead of using::

    python -m friendly_traceback example.py

to run this file, I will add an additional ``i`` flag so that ``-m`` become ``-im``;
as a result, a Friendly console will be available after the program ends
so that we can execute more Python commands.

.. image:: images/friendly_interactive_indexerror_en.png
   :scale: 50 %
   :alt: Friendly IndexError interactive example in English

In the image above, the red arrow points to the the interactive prompt
where we can type more command.

Let's do this again but choosing French as the default language: this will
help to better identify various parts and compare what information
is obtained from Python (as it won't be translated) and what additional
information is provided by Friendly traceback.


.. image:: images/friendly_interactive_indexerror_fr.png
   :scale: 50 %
   :alt: Friendly IndexError interactive example in French

In the image above, the part identified by (1) is essentially the normal
Python traceback. Depending on how long it gets, it can get shortened
by Friendly-traceback as is explained later [:ref:`multiple_tracebacks`].

Part (2) is a "hint" **occasionally** provided by Friendly-traceback
that can be useful in identifying the cause of the problem. We will see
shortly how to get Friendly-traceback to give us additional information
as to the possible cause of this error.
