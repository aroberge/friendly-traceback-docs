About Mu and Thonny
===================

.. sidebar:: What about IDLE?

    Since IDLE is included with most Python distribution,
    it is often used as the default editor/IDE by beginners.
    However, because IDLE use its own 
    quirky ways to run execute programs, it is not possible to 
    set up Friendly-traceback to capture **by default**
    the exceptions that are raised.
    While there are ways to use some functions included with 
    Friendly-traceback that can be used to find and analyze errors
    in a given program, they are not beginner friendly.
    Advanced users can consult the usage page, or the
    public API for Friendly-traceback 
    to determine which method is the most appropriate for their purpose.

As mentioned in the introduction,
while Friendly-traceback can be used on its own with a specially 
designed REPL, a better option is to use it together with GUI editors/IDE 
that are especially designed with beginners in mind. We know of 
two excellent such programs: `Mu <https://codewith.mu/>`_ and
`Thonny <https://thonny.org/>`_. This documentation includes a specific 
page for each of these two editors
which explain how to use Friendly-traceback.
Here, we offer our own opiniated comparison between the two.

About Mu 
--------

`Mu <https://codewith.mu/>`_ is a fantastic editor for absolute beginners.
Its design philosophy is to enable beginners to download a single 
program that comes with everything they need to begin their programming
journey. However, its creators 
`do acknowledge <https://codewith.mu/en/tutorials/1.0/moving-on>`_ 
that users of Mu will likely outgrow it and have to move on to use more 
advanced tools at some point in their programming journey.
This is not a weakness, but rather a strength of Mu.

While Mu can be set up to work in particular context by choosing
a `mode <https://codewith.mu/en/tutorials/1.0/modes>`_, once a mode 
is chosen, very little choice is available to a user: all available
actions are possible by clicking a fixed number of buttons, with 
everything in a single window.
This leads to a good user experience for beginners as they don't have 
to figure out whether or not option X might be a good additional choice 
for them.

This can lead to some familiar UI elements (such as "save as" to save
a file under a different name) being missed by some.

Mu supports many different human languages (English, French, etc.). 
However it does so by getting its information from the underlying
configuration of the operating system, leaving no choice for the 
user to select a different language. This is something which is 
my personal pet peeve and which I hope will be changed in future versions.

About Thonny 
------------

`Thonny <https://thonny.org/>`_ is a fantastic IDE for beginners. 
In our opinion, it is 
designed to accompany users further in their learning journey than Mu.
In a formal classroom setting, where students learn about computer 
programming, our recommendation would be to use Thonny rather than Mu as 
it includes many features specifically designed to support teaching
specific programming concepts. For example, 
users can step through a program and see a new windows opening
for each function call: this can really help beginners to understand
how recursion works.

Thonny's UI can be changed, with more elements added, by choosing
from a menu.  Some advanced configuration options are available 
via a specific dialog, including the possibility to change the
language used for the UI. 

There are simply too many features of Thonny to describe here.
To find out more, please consult `Thonny's site <https://thonny.org/>`_

Which one to use?
------------------

We really encourage you to consult the documentation available 
online for both editors, and make your own choice.
Both are fantastic tools which deserve to be better known.

Our thoughts on which one to use would be the following:

- For short term learning sessions ("workshops") with absolute beginners,
  Mu might be preferable due to its simplicity.
- For those that are teaching formal courses in computer science to 
  beginners, Thonny would likely be a better choice.
