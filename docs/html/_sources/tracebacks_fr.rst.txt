
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

Friendly-traceback version: 0.0.19a
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
    
    L'exécution s'est arrêtée à la ligne 8 du fichier 'TESTS:\except\test_arithmetic_error.py'
    
        6:         # Usually, a subclass such as ZeroDivisionError, etc., would
        7:         # likely be raised.
    --> 8:         raise ArithmeticError
        9:     except Exception:


FileNotFoundError
-----------------

.. code-block:: none


    Exception Python:
        FileNotFoundError: [Errno 2] No such file or directory: 'does_not_exist'
        
    Une exception FileNotFoundError indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe en
    écrivant le nom du fichier.
    
    Cause probable basée sur les informations données par Python :
        Dans votre programme, le nom du fichier inconnu est 'does_not_exist'.
        
    L'exécution s'est arrêtée à la ligne 6 du fichier 'TESTS:\except\test_file_not_found_error.py'
    
       4: def test_file_not_found_error():
       5:     try:
    -->6:         open("does_not_exist")
       7:     except Exception:


ImportError
-----------

.. code-block:: none


    Exception Python:
        ImportError: cannot import name 'Pi' from 'math' (unknown location)
        
    Cette exception indique qu’un certain objet n’a pas pu
    être importé à partir d’un module ou d’un paquet. Très souvent, c’est
    parce que le nom de l’objet n’est pas écrit correctement.
    
    Cause probable basée sur les informations données par Python :
        L’objet qui n’a pas pu être importé est 'Pi'.
        Le module ou le paquet d'où il devait être importé est 'math'.
        
    L'exécution s'est arrêtée à la ligne 6 du fichier 'TESTS:\except\test_import_error.py'
    
       4: def test_import_error():
       5:     try:
    -->6:         from math import Pi
       7:     except Exception:


IndentationError - 1: expected an indented block
------------------------------------------------

.. code-block:: none


    Exception Python:
        IndentationError: expected an indented block
        
    Une exception de type IndentationError se produit lorsqu'une ligne de code
    n'est pas indentée (c'est-à-dire alignée verticalement avec les autres lignes)
    de la façon attendue.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_indentation_error1.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: '''Should raise IndentationError'''
       2: 
       3: if True:
    -->4: pass
             ^

    Cause probable basée sur les informations données par Python :
        Dans ce cas-ci, la ligne indiquée ci-dessus par --> devrait
        normalement commencer un nouveau bloc de code indenté.
        

IndentationError - 2: unexpected indent
---------------------------------------

.. code-block:: none


    Exception Python:
        IndentationError: unexpected indent
        
    Une exception de type IndentationError se produit lorsqu'une ligne de code
    n'est pas indentée (c'est-à-dire alignée verticalement avec les autres lignes)
    de la façon attendue.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_indentation_error2.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: '''Should raise IndentationError'''
       2: if True:
       3:     pass
    -->4:       pass
               ^

    Cause probable basée sur les informations données par Python :
        Dans ce cas-ci, la ligne indiquée ci-dessus par -->
        est plus indentée que ce qui était attendu et ne
        correspond pas à l'indentation de la ligne précédente.
        

IndentationError - 3: unindent does not match ...
-------------------------------------------------

.. code-block:: none


    Exception Python:
        IndentationError: unindent does not match any outer indentation level
        
    Une exception de type IndentationError se produit lorsqu'une ligne de code
    n'est pas indentée (c'est-à-dire alignée verticalement avec les autres lignes)
    de la façon attendue.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_indentation_error3.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: '''Should raise IndentationError'''
       2: if True:
       3:       pass
    -->4:     pass
                  ^

    Cause probable basée sur les informations données par Python :
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
    
    Cause probable basée sur les informations données par Python :
        Dans votre programme, le nom de la clé inconnue est 'c'.
        
    L'exécution s'est arrêtée à la ligne 7 du fichier 'TESTS:\except\test_key_error.py'
    
       5:     d = {'a': 1, 'b': 2}
       6:     try:
    -->7:         d['c']
       8:     except Exception:

    d: {'a': 1, 'b': 2}


LookupError
-----------

.. code-block:: none


    Exception Python:
        LookupError: 
        
    LookupError est la classe de base pour les exceptions qui sont levées
    lorsqu’une clé ou un index utilisé sur un tableau de correspondance ou une séquence est invalide.
    Elle peut également être levée directement par codecs.lookup().
    
    L'exécution s'est arrêtée à la ligne 10 du fichier 'TESTS:\except\test_lookup_error.py'
    
        8:         # other than possibly codecs.lookup(), which is why we raise
        9:         # it directly here for our example.
    -->10:         raise LookupError
       11:     except Exception:


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
    
    Cause probable basée sur les informations données par Python :
        Dans ce cas, la séquence est un tuple.
        
    L'exécution s'est arrêtée à la ligne 8 du fichier 'TESTS:\except\test_index_error.py'
    
        6:     b = [1, 2, 3]
        7:     try:
    --> 8:         print(a[3], b[2])
        9:     except Exception:

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
    
    Cause probable basée sur les informations données par Python :
        Dans ce cas, la séquence est une liste.
        
    L'exécution s'est arrêtée à la ligne 20 du fichier 'TESTS:\except\test_index_error.py'
    
       18:     b = tuple(range(50))
       19:     try:
    -->20:         print(a[50], b[0])
       21:     except Exception:

    a: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13...]  | len(a): 40
    b: (0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13...)  | len(b): 50


ModuleNotFoundError
-------------------

.. code-block:: none


    Exception Python:
        ModuleNotFoundError: No module named 'does_not_exist'
        
    Une exception ModuleNotFoundError indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe en
    écrivant le nom du module, ou parce qu’il n’est pas installé sur votre ordinateur.
    
    Cause probable basée sur les informations données par Python :
        Dans votre programme, le nom du module inconnu est 'does_not_exist'.
        
    L'exécution s'est arrêtée à la ligne 5 du fichier 'TESTS:\except\test_module_not_found_error.py'
    
       3: def test_module_not_found_error():
       4:     try:
    -->5:         import does_not_exist
       6:     except Exception:


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
    
    Cause probable basée sur les informations données par Python :
        Dans votre programme, le nom inconnu est 'c'.
        
    L'exécution s'est arrêtée à la ligne 6 du fichier 'TESTS:\except\test_name_error.py'
    
       4: def test_name_error():
       5:     try:
    -->6:         b = c
       7:     except Exception:


OverflowError
-------------

.. code-block:: none


    Exception Python:
        OverflowError: (34, 'Result too large')
        
    Une exception de type OverflowError est levée lorsque le résultat d’une opération arithmétique
    est trop grand pour être manipulé par le processeur de l’ordinateur.
    
    L'exécution s'est arrêtée à la ligne 6 du fichier 'TESTS:\except\test_overflow_error.py'
    
       4: def test_overflow_error():
       5:     try:
    -->6:         2. ** 1600
       7:     except Exception:


TabError
--------

.. code-block:: none


    Exception Python:
        TabError: inconsistent use of tabs and spaces in indentation
        
    Une exception de type TabError indique que vous avez utilisé des espaces
    ainsi que des caractères de tabulation pour indenter votre code.
    Cela n’est pas autorisé dans Python.
    L’indentation de votre code signifie que le bloc de codes est aligné
    verticalement en insérant des espaces ou des tabulations au début des lignes.
    La recommandation de Python est de toujours utiliser des espaces
    pour indenter votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_tab_error.py'
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
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de concaténer (additionner) deux types d’objets différents:
        une chaîne de caractères ('str') et un entier ('int')
        
    L'exécution s'est arrêtée à la ligne 8 du fichier 'TESTS:\except\test_type_error.py'
    
        6:         a = "a"
        7:         one = 1
    --> 8:         result = a + one
        9:     except Exception:

    a: 'a'
    one: 1


TypeError - 1a: concatenate two different types
-----------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: can only concatenate str (not "list") to str
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de concaténer (additionner) deux types d’objets différents:
        une chaîne de caractères ('str') et une liste ('list')
        
    L'exécution s'est arrêtée à la ligne 22 du fichier 'TESTS:\except\test_type_error.py'
    
       20:         a = "a"
       21:         a_list = [1, 2, 3]
    -->22:         result = a + a_list
       23:     except Exception:

    a: 'a'
    a_list: [1, 2, 3]


TypeError - 1b: concatenate two different types
-----------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: can only concatenate tuple (not "list") to tuple
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de concaténer (additionner) deux types d’objets différents:
        un tuple et une liste ('list')
        
    L'exécution s'est arrêtée à la ligne 36 du fichier 'TESTS:\except\test_type_error.py'
    
       34:         a_tuple = (1, 2, 3)
       35:         a_list = [1, 2, 3]
    -->36:         result = a_tuple + a_list
       37:     except Exception:

    a_tuple: (1, 2, 3)
    a_list: [1, 2, 3]


TypeError - 2: unsupported operand type(s) for +
------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for +: 'int' and 'NoneType'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’additionner deux types d’objets incompatibles:
        un entier ('int') et une variable de valeur 'None' ('NoteType')
        
    L'exécution s'est arrêtée à la ligne 48 du fichier 'TESTS:\except\test_type_error.py'
    
       46:         one = 1
       47:         none = None
    -->48:         result = one + none
       49:     except Exception:

    one: 1
    none: None


TypeError - 2a: unsupported operand type(s) for +=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for +=: 'int' and 'str'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’additionner deux types d’objets incompatibles:
        un entier ('int') et une chaîne de caractères ('str')
        
    L'exécution s'est arrêtée à la ligne 60 du fichier 'TESTS:\except\test_type_error.py'
    
       58:         one = 1
       59:         two = "two"
    -->60:         one += two
       61:     except Exception:

    one: 1
    two: 'two'


TypeError - 3: unsupported operand type(s) for -
------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for -: 'tuple' and 'list'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez tenté de soustraire deux types d’objets incompatibles:
        un tuple et une liste ('list')
        
    L'exécution s'est arrêtée à la ligne 72 du fichier 'TESTS:\except\test_type_error.py'
    
       70:         a = (1, 2)
       71:         b = [3, 4]
    -->72:         result = a - b
       73:     except Exception:

    a: (1, 2)
    b: [3, 4]


TypeError - 3a: unsupported operand type(s) for -=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for -=: 'tuple' and 'list'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez tenté de soustraire deux types d’objets incompatibles:
        un tuple et une liste ('list')
        
    L'exécution s'est arrêtée à la ligne 84 du fichier 'TESTS:\except\test_type_error.py'
    
       82:         a = (1, 2)
       83:         b = [3, 4]
    -->84:         a -= b
       85:     except Exception:

    a: (1, 2)
    b: [3, 4]


TypeError - 4: unsupported operand type(s) for *
------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for *: 'complex' and 'set'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de multiplier deux types d’objets différents:
        un nombre complexe ('complex') et un ensemble ('set')
        
    L'exécution s'est arrêtée à la ligne 96 du fichier 'TESTS:\except\test_type_error.py'
    
       94:         a = 1j
       95:         b = {2, 3}
    -->96:         result = a * b
       97:     except Exception:

    a: 1j
    b: {2, 3}


TypeError - 4a: unsupported operand type(s) for ``*=``
------------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for *=: 'complex' and 'set'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de multiplier deux types d’objets différents:
        un nombre complexe ('complex') et un ensemble ('set')
        
    L'exécution s'est arrêtée à la ligne 108 du fichier 'TESTS:\except\test_type_error.py'
    
       106:         a = 1j
       107:         b = {2, 3}
    -->108:         a *= b
       109:     except Exception:

    a: 1j
    b: {2, 3}


TypeError - 5: unsupported operand type(s) for /
------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for /: 'dict' and 'float'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de diviser deux types d’objets différents:
        un dictionnaire ('dict') et un nombre ('float')
        
    L'exécution s'est arrêtée à la ligne 120 du fichier 'TESTS:\except\test_type_error.py'
    
       118:         a = {1: 1, 2: 2}
       119:         b = 3.1416
    -->120:         result = a / b
       121:     except Exception:

    a: {1: 1, 2: 2}
    b: 3.1416


TypeError - 5a: unsupported operand type(s) for /=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for /=: 'dict' and 'float'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de diviser deux types d’objets différents:
        un dictionnaire ('dict') et un nombre ('float')
        
    L'exécution s'est arrêtée à la ligne 132 du fichier 'TESTS:\except\test_type_error.py'
    
       130:         a = {1: 1, 2: 2}
       131:         b = 3.1416
    -->132:         a /= b
       133:     except Exception:

    a: {1: 1, 2: 2}
    b: 3.1416


TypeError - 5b: unsupported operand type(s) for //
--------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for //: 'dict' and 'float'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de diviser deux types d’objets différents:
        un dictionnaire ('dict') et un nombre ('float')
        
    L'exécution s'est arrêtée à la ligne 144 du fichier 'TESTS:\except\test_type_error.py'
    
       142:         a = {1: 1, 2: 2}
       143:         b = 3.1416
    -->144:         result = a // b
       145:     except Exception:

    a: {1: 1, 2: 2}
    b: 3.1416


TypeError - 5c: unsupported operand type(s) for //=
---------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for //=: 'dict' and 'float'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de diviser deux types d’objets différents:
        un dictionnaire ('dict') et un nombre ('float')
        
    L'exécution s'est arrêtée à la ligne 156 du fichier 'TESTS:\except\test_type_error.py'
    
       154:         a = {1: 1, 2: 2}
       155:         b = 3.1416
    -->156:         a //= b
       157:     except Exception:

    a: {1: 1, 2: 2}
    b: 3.1416


TypeError - 6: unsupported operand type(s) for &
------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for &: 'str' and 'int'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’effectuer l’opération binaire bit à bit &
        sur deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int')
        
    L'exécution s'est arrêtée à la ligne 168 du fichier 'TESTS:\except\test_type_error.py'
    
       166:         a = "a"
       167:         b = 2
    -->168:         result = a & b
       169:     except Exception:

    a: 'a'
    b: 2


TypeError - 6a: unsupported operand type(s) for &=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for &=: 'str' and 'int'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’effectuer l’opération binaire bit à bit &=
        sur deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int')
        
    L'exécution s'est arrêtée à la ligne 180 du fichier 'TESTS:\except\test_type_error.py'
    
       178:         a = "a"
       179:         b = 2
    -->180:         a &= b
       181:     except Exception:

    a: 'a'
    b: 2


TypeError - 7: unsupported operand type(s) for **
-------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for ** or pow(): 'dict' and 'float'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d'élever à une puissance
        en utilisant deux types d’objets incompatibles:
        un dictionnaire ('dict') et un nombre ('float')
        
    L'exécution s'est arrêtée à la ligne 192 du fichier 'TESTS:\except\test_type_error.py'
    
       190:         a = {1: 1, 2: 2}
       191:         b = 3.1416
    -->192:         result = a ** b
       193:     except Exception:

    a: {1: 1, 2: 2}
    b: 3.1416


TypeError - 7a: unsupported operand type(s) for ``**=``
-------------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for ** or pow(): 'dict' and 'float'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d'élever à une puissance
        en utilisant deux types d’objets incompatibles:
        un dictionnaire ('dict') et un nombre ('float')
        
    L'exécution s'est arrêtée à la ligne 204 du fichier 'TESTS:\except\test_type_error.py'
    
       202:         a = {1: 1, 2: 2}
       203:         b = 3.1416
    -->204:         a **= b
       205:     except Exception:

    a: {1: 1, 2: 2}
    b: 3.1416


TypeError - 8: unsupported operand type(s) for >>
-------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for >>: 'str' and 'int'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’effectuer l’opération de décalage >>
        sur deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int')
        
    L'exécution s'est arrêtée à la ligne 216 du fichier 'TESTS:\except\test_type_error.py'
    
       214:         a = "a"
       215:         b = 42
    -->216:         result = a >> b
       217:     except Exception:

    a: 'a'
    b: 42


TypeError - 8a: unsupported operand type(s) for >>=
---------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for >>=: 'str' and 'int'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’effectuer l’opération de décalage >>=
        sur deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int')
        
    L'exécution s'est arrêtée à la ligne 228 du fichier 'TESTS:\except\test_type_error.py'
    
       226:         a = "a"
       227:         b = 42
    -->228:         a >>= b
       229:     except Exception:

    a: 'a'
    b: 42


TypeError - 9: unsupported operand type(s) for @
------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for @: 'str' and 'int'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’utiliser l’opérateur @
        à l’aide de deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int').
        Cet opérateur est normalement utilisé uniquement
        pour la multiplication des matrices.
        
    L'exécution s'est arrêtée à la ligne 240 du fichier 'TESTS:\except\test_type_error.py'
    
       238:         a = "a"
       239:         b = 2
    -->240:         result = a @ b
       241:     except Exception:

    a: 'a'
    b: 2


TypeError - 9a: unsupported operand type(s) for @=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for @=: 'str' and 'int'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’utiliser l’opérateur @=
        à l’aide de deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int').
        Cet opérateur est normalement utilisé uniquement
        pour la multiplication des matrices.
        
    L'exécution s'est arrêtée à la ligne 252 du fichier 'TESTS:\except\test_type_error.py'
    
       250:         a = "a"
       251:         b = 2
    -->252:         a @= b
       253:     except Exception:

    a: 'a'
    b: 2


TypeError - 10: comparison between incompatible types
-----------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: '<' not supported between instances of 'int' and 'str'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        En utilisant <, vous avez tenté de comparer
        deux types d’objets incompatibles:
        un entier ('int') et une chaîne de caractères ('str')
        
    L'exécution s'est arrêtée à la ligne 264 du fichier 'TESTS:\except\test_type_error.py'
    
       262:         a = "a"
       263:         b = 42
    -->264:         b < a
       265:     except Exception:

    b: 42
    a: 'a'


TypeError - 11: bad operand type for unary +
--------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: bad operand type for unary +: 'str'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’utiliser l’opérateur unaire '+'
        avec le type d’objet suivant: une chaîne de caractères ('str').
        Cette opération n’est pas définie pour ce type d’objet.
        
    L'exécution s'est arrêtée à la ligne 274 du fichier 'TESTS:\except\test_type_error.py'
    
       272: def test_type_error11():
       273:     try:
    -->274:         a = +"abc"
       275:         print(a)


TypeError - 11a: bad operand type for unary -
---------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: bad operand type for unary -: 'list'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’utiliser l’opérateur unaire '-'
        avec le type d’objet suivant: une liste ('list').
        Cette opération n’est pas définie pour ce type d’objet.
        
    L'exécution s'est arrêtée à la ligne 285 du fichier 'TESTS:\except\test_type_error.py'
    
       283: def test_type_error11a():
       284:     try:
    -->285:         a = - [1, 2, 3]
       286:         print(a)


TypeError - 11b: bad operand type for unary ~
---------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: bad operand type for unary ~: 'tuple'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’utiliser l’opérateur unaire '~'
        avec le type d’objet suivant: un tuple.
        Cette opération n’est pas définie pour ce type d’objet.
        
    L'exécution s'est arrêtée à la ligne 296 du fichier 'TESTS:\except\test_type_error.py'
    
       294: def test_type_error11b():
       295:     try:
    -->296:         a = ~ (1, 2, 3)
       297:         print(a)


TypeError - 12: object does not support item assignment
-------------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: 'tuple' object does not support item assignment
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Dans Python, certains objets sont connus comme immuables:
        une fois définis, leur valeur ne peut pas être modifiée.
        Vous avez essayé de modifier une partie d’un tel objet immuable: un tuple,
        probablement en utilisant une opération d’indexation.
        
    L'exécution s'est arrêtée à la ligne 308 du fichier 'TESTS:\except\test_type_error.py'
    
       306:     a = (1, 2, 3)
       307:     try:
    -->308:         a[0] = 0
       309:     except Exception:

    a: (1, 2, 3)


TypeError - 13: wrong number of positional arguments
----------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: fn() takes 0 positional arguments but 1 was given
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez apparemment invoqué la fonction 'fn()' avec
        1 arguments positionnels alors qu'elle en requiert 0.
        
    L'exécution s'est arrêtée à la ligne 320 du fichier 'TESTS:\except\test_type_error.py'
    
       318:         pass
       319:     try:
    -->320:         fn(1)
       321:     except Exception:

    fn: <function test_type_error13.<locals>.fn>


TypeError - 14: missing positional arguments
--------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: fn() missing 2 required positional arguments: 'b' and 'c'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez apparemment invoqué la fonction 'fn()' avec
        moins d'arguments positionnels qu'il n'en faut (2 manquent).
        
    L'exécution s'est arrêtée à la ligne 332 du fichier 'TESTS:\except\test_type_error.py'
    
       330:         pass
       331:     try:
    -->332:         fn(1)
       333:     except Exception:

    fn: <function test_type_error14.<locals>.fn>


TypeError - 15: tuple object is not callable
--------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: 'tuple' object is not callable
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Je soupçonne que vous aviez un objet du type <un tuple>,
        suivi de ce qui ressemblait à un tuple, '(...) ',
        que Python a pris comme indiquant une invocation de fonction.
        Il est possible que vous ayez oublié d'écrire une virgule avant le tuple.
        
    L'exécution s'est arrêtée à la ligne 342 du fichier 'TESTS:\except\test_type_error.py'
    
       340: def test_type_error15():
       341:     try:
    -->342:         _ = (1, 2)(3, 4)
       343:     except Exception:


TypeError - 15a: list object is not callable
--------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: 'list' object is not callable
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Je soupçonne que vous aviez un objet du type <une liste ('list')>,
        suivi de ce qui ressemblait à un tuple, '(...) ',
        que Python a pris comme indiquant une invocation de fonction.
        Il est possible que vous ayez oublié d'écrire une virgule avant le tuple.
        
    L'exécution s'est arrêtée à la ligne 352 du fichier 'TESTS:\except\test_type_error.py'
    
       350: def test_type_error15a():
       351:     try:
    -->352:         _ = [1, 2](3, 4)
       353:     except Exception:


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
    
    Cause probable basée sur les informations données par Python :
        La variable qui semble causer le problème est' a '.
        Il est possible que vous avez oublié d'écrire l’instruction
            global a
        comme première ligne à l’intérieur de votre fonction.
        
    L'exécution s'est arrêtée à la ligne 20 du fichier 'TESTS:\except\test_unbound_local_error.py'
    
       18: 
       19:     try:
    -->20:         outer()
       21:     except Exception:

    global outer: <function outer>

    Exception levée à la ligne 12 du fichier 'TESTS:\except\test_unbound_local_error.py'.
    
       10:     def inner():
       11:         c = 3
    -->12:         a = a + b + c
       13:     inner()

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
    
    L'exécution s'est arrêtée à la ligne 10 du fichier 'TESTS:\except\test_unknown_error.py'
    
        8: def test_unknown_error():
        9:     try:
    -->10:         raise MyException("Some informative message")
       11:     except Exception:

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
    
    L'exécution s'est arrêtée à la ligne 6 du fichier 'TESTS:\except\test_zero_division_error.py'
    
       4: def test_zero_division_error():
       5:     try:
    -->6:         1 / 0
       7:     except Exception:


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
    
    L'exécution s'est arrêtée à la ligne 17 du fichier 'TESTS:\except\test_zero_division_error.py'
    
       15:     zero = 0
       16:     try:
    -->17:         1 % zero
       18:     except Exception:

    zero: 0

