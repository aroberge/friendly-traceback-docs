
Using with Thonny
=================

`Thonny <https://github.com/thonny/thonny/>`_ is a fantastic
programming environment for learning Python.
While it does not support traceback theming with Rich, we nonetheless
highly recommend it to beginners and instructors.

Starting with version 3.2.5, Thonny included built-in support for
an early version of Friendly-traceback. As Friendly-traceback evolved,
we suggested that the built-in support be temporarily removed so as to avoid
any incompatibility; this will likely happen with the release of
Thonny's version 3.3.

Friendly-traceback can still be used within Thonny
using the same approach described for other editors in
:ref:`using_editor`. The only difference is for actually installing
Friendly-traceback.

Thonny is highly configurable. Among the tools
it provides is the ability to install packages either from pypi or
others found locally.

.. image:: images/thonny_manage_packages1.png
   :scale: 50 %
   :alt: thonny manage packages

The first step is to ensure that Thonny can see that Friendly-traceback
is installed. If not, one can install it with pip or with Thonny itself.
As you can see, Friendly-traceback is indeed installed on my
computer, along with many other packages.

.. image:: images/thonny_manage_packages2.png
   :scale: 50 %
   :alt: thonny manage packages

From that point on, everything is the same as for other editors.
To find out what you can do in addition to what is shown here,
go back and have a look at :ref:`using_repl`.
Then, go on to the following section, :ref:`using_editor`, to
see everything that there is to know about using with any editor.
