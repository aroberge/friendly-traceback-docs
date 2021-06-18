Notes on translations - using gettext
=====================================

.. important::

    There are many sites that explain how to use gettext. However, I found
    that, no matter what individual explanation I read, it was either
    incomplete, too specific, or otherwise glossing over some minor point
    that was important for my project.

    I wrote these notes mostly for myself, but they may be useful for
    you as well, perhaps even more so if you read a "standard" tutorial
    on using gettext first.


What is gettext?
----------------

gettext is basically a standardized way of internationalization (i18n)
and localization (l10n) of computer programs.

What this means for this project, is the translation of strings shown
to the user in their preferred language.


Structure of this project
-------------------------

Below, I make references to various files. Here's a simplified view of the
directory structure of this project, showing only a few relevant files:

.. code-block:: none

    friendly/
        demos/
        friendly/
            locales/
                fr/
                    LC_MESSAGES/
                        friendly.mo
                        friendly.po
                friendly.pot
            __init__.py
            ...
            make_pot.bat  <-- not in repository
            my_gettext.py
            ...
        tests/
        setup.py

If you look at the repository on Github (or cloned locally), you will not
see the file ``make_pot.bat``.
I'll explain its role below.


How to use gettext
--------------------

Suppose we want to greet a user in their own language. For example,
in English we might have the following::

    print("Hello {name}".format(name=username))

while in French, we might have::

    print("Bonjour {name}".format(name=username))

The first thing to do would normally be to choose one of these forms as
our standard to be used as the reference for translation.
This is what I eventually chose to do for this project.
However, in the past, I have often
used a variation where words are written in the source file in uppercase
letter to make it more obvious to see if a translation is missing.

To indicate that a string needs to be translated, the common way is to
surround it by a function call, using ``_`` as the function name::

    print(  _( "Hello {name}" )  .format(name=username)  )

    # extra spaces above added for clarity

Next, we need to create a "template" file for translations.
I use ``pygettext.py`` included as a **tool** with Python.
It is very likely not on the normal path where it can be found by Python.
If you don't know where your python files are located, you can use
Python's REPL and do the following::

    >>> import sys
    >>> print(sys.prefix)
    path\to\python

You can then navigate to the directory containing the Python version
you are using and will almost certainly
find ``pygettext.py`` under the ``tools\i18n`` subdirectory.

``pygettext`` will extract all the strings surronded by ``_( )`` in the
input file you specify and create a "template" file (identified by a ``.pot``
extension). To make my life easier, I simply type ``make_pot`` at the prompt
which executes the content of ``make_pot.bat`` (I'm using Windows)::

    py -3.7 path\to\python\tools\i18n\pygettext.py -p locales -d friendly *.py


- ``make_pot.bat`` is located in the same directory where the Python source files
  containing strings to be translated is located.
- I use ``python filename.py`` instead of simply ``filename.py`` as I set my
  computer default to open ``.py`` files with my preferred editor instead of
  executing them. If you are not using Windows, you might need to use
  ``python3`` instead of ``python``.
- The ``-p locales`` option specifies that the template file is going to be
  created (or updated) in the ``locales/`` directory
  (see above for the directory structure).
- Using the -d flag, I specified ``friendly`` as the name for the template file,
  ``friendly.pot``, instead of the default ``messages.pot``.
- The source files scanned by pygettext (``*.py``) will be all the
  Python files in that directory.

There's more to be done; let's break this up into a few additional
sections.

Using Poedit
-------------

In principle, template files can be edited with any standard text editor
to create "portable object" (``.po``) files from a template file.
However, this is more easily done using
`Poedit <https://poedit.net/>`_ which is a free program especially designed
for this task. There is a paid "pro" version but it is really not required for
most tasks.  However, after a while, I have purchased it and found its
suggested translations usually very useful, at least as a starting point.

With Poedit, you have the choice of **creating** a new translation
either from a ``.pot`` file, or from a ``.po`` file. Open the relevant file,
choose a language, and start translating the various strings.

If you are **updating** an existing translation, open the ``.po`` file
and use Poedit's "Catalog" menu (fourth at the top of the menu
bar) to first update from the source (``messages.pot``) from which the
``.po`` file is derived.

Poedit gives the choice to translate for specific regions (e.g. fr_CA for
French used in Canada). For this project, I prefer to choose a generic
two-letter code (fr) as it is assumed to be the case in various places.

.. warning::

    If, for a given language, you **absolutely** need different language
    translations, specific to a region, please file an issue
    first so that this can be discussed and the impact on the rest of
    the code can be properly evaluated.

    One of the goals of this project is to provide easier to understand
    tracebacks than those provided by Python. These do not need to be
    absolutely perfect. For example, we follow
    `Blockly's practice <https://translatewiki.net/wiki/Translating:Blockly>`_
    in not supporting `plural formatting <https://translatewiki.net/wiki/Plural>`_

When it comes time to save the ``.po`` file, use a similar structure
as that shown above and save
it in the ``LC_MESSAGES`` directory of the appropriate language.
Note that Poedit will automatically save another file with
a ``.mo`` extension; this is a "machine object" (binary) file that will actually
be used by your program.

In addition to strings to be translated, ``.po`` files contain some
information about who translated the file and some copyright information.
In general, you might want to fill in the appropriate information.
Note that Poedit allows you to set your personal information (name
and email address) which will be automatically used, so that you don't
have to edit the created file by hand.

.. warning::

    Please, do not contribute translations to friendly
    where you attribute the copyright to yourself.
    Either do not include any copyright information
    or attribute it to the friendly project.

Telling Python to use the translations
--------------------------------------

In this project, the language selection is done in the file ``session.py``.
(See directory structure above.)
At the top of ``session.py``, ``my_gettext`` is imported.
As I am writing this documentation, this is the content of ``my_gettext.py``::

    import gettext
    import os

    class LangState:
        def __init__(self):
            self.translate = None
            self.lang = "en"

        def install(self, lang=None):
            """Sets the language to be used for translations"""
            if lang is None:
                lang = "en"
            try:
                # We first look for the exact language requested.
                _lang = gettext.translation(
                    "friendly",
                    localedir=os.path.normpath(  # 1
                        os.path.join(os.path.dirname(__file__), "locales")
                    ),
                    languages=[lang],
                    fallback=False,  # 2
                )
            except FileNotFoundError:
                # If it is not available, we make it possible to replace a
                # language specific to a region, as in fr_CA, by a more
                # generic version, such as fr, defined by a two-letter code.
                lang = lang[:2]  # 3
                _lang = gettext.translation(
                    "friendly",
                    localedir=os.path.normpath(
                        os.path.join(os.path.dirname(__file__), "locales")
                    ),
                    languages=[lang],
                    fallback=True,  # 4 This means that the hard-coded strings in
                    # the source file will be used if the requested language
                    # is not available.
                )
            self.lang = lang
            self.translate = _lang.gettext


    current_lang = LangState()  # 3


Here is an explanation for the numbered comments above:

    1. "Foolproof" way of locating the translation directory

    2. By default, fallback is ``False``; for clarity, we explicitly set it.
       If a request is made to use a non-existing translation, an exception is raised.

    3. This is the instance we use elsewhere; see below.


When we want to make use of translations inside a given function,
we do the following::

    from . import my_gettext

    def international_greeting(name):
        _ = current_lang.translate
        return _("Hello {name}").format(name=name)

.. warning::

    Every language has its own way to deal (or not) with plural forms of words.
    As mentioned, in principle, ``gettext`` offers a way to handle
    with the language specific complexities.
    In practice for this project, we assume a single form to be used.


Why are .mo files in the repository
-----------------------------------

When configuring the project, the automatically generated ``.gitignore`` file
include exclusion for ``.pot`` and ``.mo`` files.
The rationale is that these files are automatically generated (by some standard
programs) and it is generally suggested that such files not be included.

However, in this case, we want these files to be available to end users.
If someone clones the project, and needs to upload a version somewhere (e.g. pypi.org),
these generated files (at least the ``.mo`` files) need to be included.


Packaging
---------

This is more of a "note to self" than something needed for this project.
Since ``.po`` and ``.mo`` are data files are not python files,
they are not automatically added when creating a package with setuptools.
One way to include them is to write the following in a file named
``manifest.in`` written where ``setup.py`` is found:

.. code-block:: none

    recursive-include friendly/locales *.*

Also (instead?), if using a ``setup.cfg`` file, include the following:

.. code-block:: none

    [options.package_data]
    * =
        friendly/locales/*
