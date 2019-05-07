
Friendly tracebacks - en Français
======================================

Le but principal de friendly-traceback est de fournir des rétroactions plus
conviviales que les fameux **tracebacks** de Python lorsqu'une exception survient.
Ci-dessous, on peut voir quelques exemples. Le but éventuel est de documenter
ici tous les exemples possibles tels qu'interprétés par friendly-traceback.

.. note::

     Le contenu de cette page a été généré par l'exécution de
     trb_french.py situé dans le répertoire ``tests/``.
     Ceci a besoin d'être fait de manière explicite lorsqu'on veut
     faire des corrections ou des ajouts, avant de faire la mise
     à jour du reste de la documentation avec Sphinx.
     Sous Windows, si Sphinx est installé sur votre ordinateur, il est
     plutôt suggéré d'exécuter make_trb.bat qui est au premier niveau
     du répertoire de fichier. Si vous faites ceci, la documentation pour
     toutes les langues sera automatiquement mise à jour.

Friendly-traceback version: 0.0.6alpha
Python version: 3.7.3



ArithmeticError
---------------

.. code-block:: none


    Exception Python: 
        ArithmeticError: 

    ArithmeticError est la classe de base pour les exceptions
    qui sont soulevées pour diverses erreurs arithmétiques.
    Il est inhabituel que vous voyiez cette exception;
    normalement, une exception plus spécifique aurait dû être soulevée.

    L'exécution s'est arrêtée à la ligne 10 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_arithmetic_error.py'

        8:         # Usually, a subclass such as ZeroDivisionError, etc., would
        9:         # likely be raised.
    -->10:         raise ArithmeticError
       11:     except Exception:

ImportError
-----------

.. code-block:: none


    Exception Python: 
        ImportError: cannot import name 'Pi' from 'math' (unknown location)

    Cette exception indique qu’un certain objet n’a pas pu
    être importé à partir d’un module ou d’un paquet. Très souvent, c’est
    parce que le nom de l’objet n’est pas écrit correctement.

    Cause probable : 
        L’objet qui n’a pas pu être importé est 'Pi'.
        Le module ou le paquet d'où il devait être importé est 'math'.

    L'exécution s'est arrêtée à la ligne 7 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_import_error.py'

       5: def test_import_error():
       6:     try:
    -->7:         from math import Pi
       8:     except Exception:

IndentationError - 1: expected an indented block
------------------------------------------------

.. code-block:: none


    Exception Python: 
        IndentationError: expected an indented block (raise_indentation_error1.py, line 4)

    Une exception de type IndentationError se produit lorsqu'une ligne de code
    n'est pas indentée (c'est-à-dire alignée verticalement avec les autres lignes)
    de la façon attendue.
    Python peut seulement analyser le fichier 'raise_indentation_error1.py'
    jusqu'à l'endroit indiqué par --> et ^.

       1: '''Should raise IndentationError'''
       2: 
       3: if True:
    -->4: pass
             ^

    Cause probable : 
        Dans ce cas-ci, la ligne indiquée ci-dessus par --> devrait
        normalement commencer un nouveau bloc de code indenté.

IndentationError - 2: unexpected indent
---------------------------------------

.. code-block:: none


    Exception Python: 
        IndentationError: unexpected indent (raise_indentation_error2.py, line 4)

    Une exception de type IndentationError se produit lorsqu'une ligne de code
    n'est pas indentée (c'est-à-dire alignée verticalement avec les autres lignes)
    de la façon attendue.
    Python peut seulement analyser le fichier 'raise_indentation_error2.py'
    jusqu'à l'endroit indiqué par --> et ^.

       1: '''Should raise IndentationError'''
       2: if True:
       3:     pass
    -->4:       pass
               ^

    Cause probable : 
        Dans ce cas-ci, la ligne indiquée ci-dessus par -->
        est plus indentée que ce qui était attendu et ne
        correspond pas à l'indentation de la ligne précédente.

IndentationError - 3: unindent does not match ...
-------------------------------------------------

.. code-block:: none


    Exception Python: 
        IndentationError: unindent does not match any outer indentation level (raise_indentation_error3.py, line 4)

    Une exception de type IndentationError se produit lorsqu'une ligne de code
    n'est pas indentée (c'est-à-dire alignée verticalement avec les autres lignes)
    de la façon attendue.
    Python peut seulement analyser le fichier 'raise_indentation_error3.py'
    jusqu'à l'endroit indiqué par --> et ^.

       1: '''Should raise IndentationError'''
       2: if True:
       3:       pass
    -->4:     pass
                  ^

    Cause probable : 
        Dans ce cas-ci, la ligne indiquée ci-dessus par -->
        est moins indentée que la ligne précédente
        et n’est pas alignée verticalement avec un autre bloc de code.

KeyError
--------

.. code-block:: none


    Exception Python: 
        KeyError: 'c'

    Une erreur KeyError est levée lorsqu’une valeur n’est pas trouvée
    en tant que clé dans un dictionnaire (dict) Python.

    Cause probable : 
        Dans votre programme, le nom de la clé inconnue est 'c'.

    L'exécution s'est arrêtée à la ligne 8 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_key_error.py'

        6:     d = {'a': 1, 'b': 2}
        7:     try:
    --> 8:         d['c']
        9:     except Exception:
    d: {'a': 1, 'b': 2}


LookupError
-----------

.. code-block:: none


    Exception Python: 
        LookupError: 

    LookupError est la classe de base pour les exceptions qui sont levées
    lorsqu’une clé ou un index utilisé sur un tableau de correspondance ou une séquence est invalide.
    Elle peut également être levée directement par codecs.lookup().

    L'exécution s'est arrêtée à la ligne 11 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_lookup_error.py'

        9:         # other than possibly codecs.lookup(), which is why we raise
       10:         # it directly here for our example.
    -->11:         raise LookupError
       12:     except Exception:

IndexError - short tuple
------------------------

.. code-block:: none


    Exception Python: 
        IndexError: tuple index out of range

    Un IndexError se produit lorsque vous essayez d’obtenir un élément
    d'une liste, d'un tuple, ou d'un objet similaire (séquence), à l’aide d’un index qui
    n’existe pas; typiquement, c’est parce que l’index que vous donnez
    est plus grand que la longueur de la séquence.
    Rappel: le premier élément d'une séquence est à l'index 0.


    Cause probable : 
        Dans ce cas, la séquence est un tuple.

    L'exécution s'est arrêtée à la ligne 9 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_index_error.py'

        7:     b = [1, 2, 3]
        8:     try:
    --> 9:         print(a[3], b[2])
       10:     except Exception:
    a: (1, 2, 3)
    b: [1, 2, 3]


IndexError - long list
----------------------

.. code-block:: none


    Exception Python: 
        IndexError: list index out of range

    Un IndexError se produit lorsque vous essayez d’obtenir un élément
    d'une liste, d'un tuple, ou d'un objet similaire (séquence), à l’aide d’un index qui
    n’existe pas; typiquement, c’est parce que l’index que vous donnez
    est plus grand que la longueur de la séquence.
    Rappel: le premier élément d'une séquence est à l'index 0.


    Cause probable : 
        Dans ce cas, la séquence est une liste.

    L'exécution s'est arrêtée à la ligne 21 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_index_error.py'

       19:     b = tuple(range(50))
       20:     try:
    -->21:         print(a[50], b[0])
       22:     except Exception:
    a: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13...]  | len(a): 40
    b: (0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13...)  | len(b): 50


ModuleNotFoundError
-------------------

.. code-block:: none


    Exception Python: 
        ModuleNotFoundError: No module named 'does_not_exist'

    Une exception ModuleNotFoundError indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe
    écrivant le nom du module, ou parce qu’il n’est pas installé sur votre ordinateur.

    Cause probable : 
        Dans votre programme, le nom du module inconnu est 'does_not_exist'.

    L'exécution s'est arrêtée à la ligne 7 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_module_not_found_error.py'

       5: def test_module_not_found_error():
       6:     try:
    -->7:         import does_not_exist
       8:     except Exception:

NameError
---------

.. code-block:: none


    Exception Python: 
        NameError: name 'c' is not defined

    Une exception NameError indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.

    Cause probable : 
        Dans votre programme, le nom inconnu est 'c'.

    L'exécution s'est arrêtée à la ligne 7 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_name_error.py'

       5: def test_name_error():
       6:     try:
    -->7:         b = c
       8:     except Exception:

TabError
--------

.. code-block:: none


    Exception Python: 
        TabError: inconsistent use of tabs and spaces in indentation (raise_tab_error.py, line 7)

    Un exception de type TabError indique que vous avez utilisé des espaces
    ainsi que des caractères de tabulation pour indenter votre code.
    Cela n’est pas autorisé dans Python.
    L’indentation de votre code signifie que le bloc de codes est aligné
    verticalement en insérant des espaces ou des tabulations au début des lignes.
    La recommandation de Python est de toujours utiliser des espaces
    pour indenter votre code.

    Python peut seulement analyser le fichier 'raise_tab_error.py'
    jusqu'à l'endroit indiqué par --> et ^.

        4: 
        5: def test_tab_error():
        6:     if True:
    --> 7: 	pass
                ^

TypeError - 1: concatenate two different types
----------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: can only concatenate str (not "int") to str

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez essayé de concaténer (additionner) deux types d’objets différents:
        une chaîne de caractères ('str') et un entier ('int')

    L'exécution s'est arrêtée à la ligne 9 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

        7:         a = "a"
        8:         one = 1
    --> 9:         result = a + one
       10:     except Exception:
    a: 'a'
    one: 1


TypeError - 1a: concatenate two different types
-----------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: can only concatenate str (not "list") to str

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez essayé de concaténer (additionner) deux types d’objets différents:
        une chaîne de caractères ('str') et une liste ('list')

    L'exécution s'est arrêtée à la ligne 23 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       21:         a = "a"
       22:         a_list = [1, 2, 3]
    -->23:         result = a + a_list
       24:     except Exception:
    a: 'a'
    a_list: [1, 2, 3]


TypeError - 1b: concatenate two different types
-----------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: can only concatenate tuple (not "list") to tuple

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez essayé de concaténer (additionner) deux types d’objets différents:
        un tuple et une liste ('list')

    L'exécution s'est arrêtée à la ligne 37 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       35:         a_tuple = (1, 2, 3)
       36:         a_list = [1, 2, 3]
    -->37:         result = a_tuple + a_list
       38:     except Exception:
    a_tuple: (1, 2, 3)
    a_list: [1, 2, 3]


TypeError - 2: unsupported operand type(s) for +
------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for +: 'int' and 'NoneType'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez essayé d’additionner deux types d’objets incompatibles:
        un entier ('int') et une variable de valeur 'None' ('NoteType')

    L'exécution s'est arrêtée à la ligne 49 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       47:         one = 1
       48:         none = None
    -->49:         result = one + none
       50:     except Exception:
    one: 1
    none: None


TypeError - 2a: unsupported operand type(s) for +=
--------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for +=: 'int' and 'str'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez essayé d’additionner deux types d’objets incompatibles:
        un entier ('int') et une chaîne de caractères ('str')

    L'exécution s'est arrêtée à la ligne 61 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       59:         one = 1
       60:         two = "two"
    -->61:         one += two
       62:     except Exception:
    one: 1
    two: 'two'


TypeError - 3: unsupported operand type(s) for -
------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for -: 'tuple' and 'list'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez tenté de soustraire deux types d’objets incompatibles:
        un tuple et une liste ('list')

    L'exécution s'est arrêtée à la ligne 73 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       71:         a = (1, 2)
       72:         b = [3, 4]
    -->73:         result = a - b
       74:     except Exception:
    a: (1, 2)
    b: [3, 4]


TypeError - 3a: unsupported operand type(s) for -=
--------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for -=: 'tuple' and 'list'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez tenté de soustraire deux types d’objets incompatibles:
        un tuple et une liste ('list')

    L'exécution s'est arrêtée à la ligne 85 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       83:         a = (1, 2)
       84:         b = [3, 4]
    -->85:         a -= b
       86:     except Exception:
    a: (1, 2)
    b: [3, 4]


TypeError - 4: unsupported operand type(s) for *
------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for *: 'complex' and 'set'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez essayé de multiplier deux types d’objets différents:
        un nombre complexe ('complex') et un ensemble ('set')

    L'exécution s'est arrêtée à la ligne 97 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       95:         a = 1j
       96:         b = {2, 3}
    -->97:         result = a * b
       98:     except Exception:
    a: 1j
    b: {2, 3}


TypeError - 4a: unsupported operand type(s) for ``*=``
------------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for *=: 'complex' and 'set'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez essayé de multiplier deux types d’objets différents:
        un nombre complexe ('complex') et un ensemble ('set')

    L'exécution s'est arrêtée à la ligne 109 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       107:         a = 1j
       108:         b = {2, 3}
    -->109:         a *= b
       110:     except Exception:
    a: 1j
    b: {2, 3}


TypeError - 5: unsupported operand type(s) for /
------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for /: 'dict' and 'float'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez essayé de diviser deux types d’objets différents:
        un dictionnaire ('dict') et un nombre ('float')

    L'exécution s'est arrêtée à la ligne 121 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       119:         a = {1: 1, 2: 2}
       120:         b = 3.1416
    -->121:         result = a / b
       122:     except Exception:
    a: {1: 1, 2: 2}
    b: 3.1416


TypeError - 5a: unsupported operand type(s) for /=
--------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for /=: 'dict' and 'float'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez essayé de diviser deux types d’objets différents:
        un dictionnaire ('dict') et un nombre ('float')

    L'exécution s'est arrêtée à la ligne 133 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       131:         a = {1: 1, 2: 2}
       132:         b = 3.1416
    -->133:         a /= b
       134:     except Exception:
    a: {1: 1, 2: 2}
    b: 3.1416


TypeError - 5b: unsupported operand type(s) for //
--------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for //: 'dict' and 'float'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez essayé de diviser deux types d’objets différents:
        un dictionnaire ('dict') et un nombre ('float')

    L'exécution s'est arrêtée à la ligne 145 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       143:         a = {1: 1, 2: 2}
       144:         b = 3.1416
    -->145:         result = a // b
       146:     except Exception:
    a: {1: 1, 2: 2}
    b: 3.1416


TypeError - 5c: unsupported operand type(s) for //=
---------------------------------------------------

.. code-block:: none


    Exception Python: 
        AttributeError: module 'test_type_error' has no attribute 'test_type_error5c'

    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues

    L'exécution s'est arrêtée à la ligne 147 du fichier 'C:\Users\andre\github\friendly-traceback\tests\trb_common.py'

       145:                     mod = __import__(name)
       146:                     if function is not None:
    -->147:                         result = getattr(mod, function)()
       148:                         write(result)
    result: "\n    Exception Python: \n        TypeError:..."  | len(result): 724
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error5c'

TypeError - 6: unsupported operand type(s) for &
------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for &: 'str' and 'int'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez essayé d’effectuer l’opération binaire bit à bit &
        sur deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int')

    L'exécution s'est arrêtée à la ligne 169 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       167:         a = "a"
       168:         b = 2
    -->169:         result = a & b
       170:     except Exception:
    a: 'a'
    b: 2


TypeError - 6a: unsupported operand type(s) for &=
--------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for &=: 'str' and 'int'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Je ne reconnais pas ce cas. Veuillez le signaler à
        https://github.com/aroberge/friendly-traceback/issues

    L'exécution s'est arrêtée à la ligne 181 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       179:         a = "a"
       180:         b = 2
    -->181:         a &= b
       182:     except Exception:
    a: 'a'
    b: 2


TypeError - 7: unsupported operand type(s) for **
-------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for ** or pow(): 'dict' and 'float'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez essayé d'élever à une puissance
        en utilisant deux types d’objets incompatibles:
        un dictionnaire ('dict') et un nombre ('float')

    L'exécution s'est arrêtée à la ligne 193 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       191:         a = {1: 1, 2: 2}
       192:         b = 3.1416
    -->193:         result = a ** b
       194:     except Exception:
    a: {1: 1, 2: 2}
    b: 3.1416


TypeError - 7a: unsupported operand type(s) for ``**=``
-------------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for ** or pow(): 'dict' and 'float'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez essayé d'élever à une puissance
        en utilisant deux types d’objets incompatibles:
        un dictionnaire ('dict') et un nombre ('float')

    L'exécution s'est arrêtée à la ligne 205 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       203:         a = {1: 1, 2: 2}
       204:         b = 3.1416
    -->205:         a **= b
       206:     except Exception:
    a: {1: 1, 2: 2}
    b: 3.1416


TypeError - 8: unsupported operand type(s) for >>
-------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for >>: 'str' and 'int'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez essayé d’effectuer l’opération de décalage >>
        sur deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int')

    L'exécution s'est arrêtée à la ligne 217 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       215:         a = "a"
       216:         b = 42
    -->217:         result = a >> b
       218:     except Exception:
    a: 'a'
    b: 42


TypeError - 8a: unsupported operand type(s) for >>=
---------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for >>=: 'str' and 'int'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Je ne reconnais pas ce cas. Veuillez le signaler à
        https://github.com/aroberge/friendly-traceback/issues

    L'exécution s'est arrêtée à la ligne 229 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       227:         a = "a"
       228:         b = 42
    -->229:         a >>= b
       230:     except Exception:
    a: 'a'
    b: 42


TypeError - 9: unsupported operand type(s) for @
------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for @: 'str' and 'int'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Vous avez essayé d’utiliser l’opérateur @
        à l’aide de deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int').
        Cet opérateur est normalement utilisé uniquement
        pour la multiplication des matrices.

    L'exécution s'est arrêtée à la ligne 241 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       239:         a = "a"
       240:         b = 2
    -->241:         result = a @ b
       242:     except Exception:
    a: 'a'
    b: 2


TypeError - 9a: unsupported operand type(s) for @=
--------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: unsupported operand type(s) for @=: 'str' and 'int'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        Je ne reconnais pas ce cas. Veuillez le signaler à
        https://github.com/aroberge/friendly-traceback/issues

    L'exécution s'est arrêtée à la ligne 253 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       251:         a = "a"
       252:         b = 2
    -->253:         a @= b
       254:     except Exception:
    a: 'a'
    b: 2


TypeError - 10: comparison between incompatible types
-----------------------------------------------------

.. code-block:: none


    Exception Python: 
        TypeError: '<' not supported between instances of 'int' and 'str'

    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.

    Cause probable : 
        En utilisant <, vous avez tenté de comparer
        deux types d’objets incompatibles:
        un entier ('int') et une chaîne de caractères ('str')

    L'exécution s'est arrêtée à la ligne 265 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_type_error.py'

       263:         a = "a"
       264:         b = 42
    -->265:         b < a
       266:     except Exception:
    b: 42
    a: 'a'


UnboundLocalError
-----------------

.. code-block:: none


    Exception Python: 
        UnboundLocalError: local variable 'a' referenced before assignment

    En Python, les variables utilisées à l’intérieur d’une fonction sont appelées
    variables «locales».
    Avant d’utiliser une variable locale, une valeur doit lui être attribuée.
    Une variable utilisée avant l’attribution d’une valeur est supposée
    être définie en dehors de cette fonction;
    elle est connu comme une variable «globale» ('global' ou parfois 'nonlocal').
    Vous ne pouvez pas assigner une valeur à une telle variable globale
    à l’intérieur d’une fonction sans d’abord confirmer à python
    qu’il s’agit d’une variable globale, sinon vous verrez une exception UnboundLocalError.

    Cause probable : 
        La variable qui semble causer le problème est' a '.
        Il est possible que vous avez oublié d'écrire l’instruction
            global a
        comme première ligne à l’intérieur de votre fonction.

    L'exécution s'est arrêtée à la ligne 21 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_unbound_local_error.py'

       19: 
       20:     try:
    -->21:         outer()
       22:     except Exception:
    global outer: <function outer at 0x035B4D20>

    Exception levée à la ligne du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_unbound_local_error.py'.

       11:     def inner():
       12:         c = 3
    -->13:         a = a + b + c
       14:     inner()
    global b: 2
    c: 3


Unknown exception
-----------------

.. code-block:: none


    Exception Python: 
        MyException: Some informative message

    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues

    L'exécution s'est arrêtée à la ligne 11 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_unknown_error.py'

        9: def test_unknown_error():
       10:     try:
    -->11:         raise MyException("Some informative message")
       12:     except Exception:
    global MyException: <class 'test_unknown_error.MyException'>


ZeroDivisionError - 1
---------------------

.. code-block:: none


    Exception Python: 
        ZeroDivisionError: division by zero

    Une exception de type ZeroDivisionError se produit lorsque
    vous tentez de diviser une valeur par zéro:
        résultat = ma_variable / 0
    Ceci peut également se produire si vous calculez le reste d’une division 
    à l’aide de l’opérateur modulo '%'
        résultat = ma_variable % 0

    L'exécution s'est arrêtée à la ligne 7 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_zero_division_error.py'

       5: def test_zero_division_error():
       6:     try:
    -->7:         1 / 0
       8:     except Exception:

ZeroDivisionError - 2
---------------------

.. code-block:: none


    Exception Python: 
        ZeroDivisionError: integer division or modulo by zero

    Une exception de type ZeroDivisionError se produit lorsque
    vous tentez de diviser une valeur par zéro:
        résultat = ma_variable / 0
    Ceci peut également se produire si vous calculez le reste d’une division 
    à l’aide de l’opérateur modulo '%'
        résultat = ma_variable % 0

    L'exécution s'est arrêtée à la ligne 17 du fichier 'C:\Users\andre\github\friendly-traceback\tests\test_zero_division_error.py'

       15: def test_zero_division_error2():
       16:     try:
    -->17:         1 % 0
       18:     except Exception:
