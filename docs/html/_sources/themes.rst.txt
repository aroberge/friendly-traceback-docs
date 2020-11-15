.. _themes:

Themes and colours
===================

As mentioned before, Friendly-traceback can make use of
`Rich <https://github.com/willmcgugan/rich>`_ if it is installed.
Syntax colouring is done by Rich using Pygments.
While Pygments comes with many different styles (colour schemes),
most of them do not define colours for all possible parts of
a Python traceback: depending on the style, we sometimes end up with
some text with the same colour as the background.

To ensure that all of Friendly-traceback's output would be styled
properly, Friendly-traceback includes its own "theme".
One problem I had was to figure out
all the possible styling elements. It turned out that I had "solved"
this problem in 2008 when I created the Pygments Tango style for
a project I worked (Crunchy) where I did my best to include all
possible styling elements, while minimizing the numbers of colours
used. While Tango had been designed for a light coloured background,
the new style has been designed for a dark coloured background.

Designing a pygments colour style is one thing; having it faithfully
displayed in a terminal is something else altogether.
Below you will see various screenshots: the first one is
taken using the new `Windows Terminal <https://github.com/microsoft/terminal>`_.
Other screenshots have been taken using `ConEmu <https://conemu.github.io/>`_,
using different colour schemes available from ConEmu's settings.
Much to my surprise, even though the colours I have chosen are not standard
colours, they are much altered by ConEmu depending on the chosen
colour scheme.

Default theme using Windows Terminal
-------------------------------------

.. image:: images/theme_terminal.png
   :scale: 40 %
   :alt: Default theme using Windows Terminal


ConEmu: base16 theme
--------------------

.. image:: images/conemu_base16.png
   :scale: 40 %
   :alt: ConEmu: base16 theme


ConEmu: default windows theme
-----------------------------

.. image:: images/conemu_default_windows.png
   :scale: 40 %
   :alt: ConEmu: default windows theme

ConEmu: powershell theme
-----------------------------

.. image:: images/conemu_powershell.png
   :scale: 40 %
   :alt: ConEmu: default powershell theme


Other OS
--------

Screenshots taken by MacOS or Linux users would be welcome.

Conclusion
-----------

It appears that efforts to carefully design a theme are somewhat
pointless as the end result can depend on the environment used.
