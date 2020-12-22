
|france| Friendly tracebacks - en Français
===========================================

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

Friendly-traceback version: 0.2.9a
Python version: 3.8.4



ArithmeticError
---------------


Generic
~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_arithmetic_error.py", line 9, in test_Generic
        raise ArithmeticError('error')
    ArithmeticError: error
    
    `ArithmeticError` est la classe de base pour les exceptions
    qui sont soulevées pour diverses erreurs arithmétiques.
    Il est inhabituel que vous voyiez cette exception;
    normalement, une exception plus spécifique aurait dû être soulevée.
    
    Exception levée à la ligne 9 du fichier TESTS:\runtime\test_arithmetic_error.py.
    
        7:         # Usually, a subclass such as ZeroDivisionError, etc., would
        8:         # likely be raised.
    --> 9:         raise ArithmeticError('error')
       10:     except Exception as e:

            ArithmeticError: <class ArithmeticError>
        


AttributeError
--------------


Builtin function
~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 188, in test_Builtin_function
        len.text
    AttributeError: 'builtin_function_or_method' object has no attribute 'text'
    
        Vouliez-vous dire `len(text)` ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        `len` est une fonction. Peut-être que vous vouliez écrire
        `len(text)`
        
    Exception levée à la ligne 188 du fichier TESTS:\runtime\test_attribute_error.py.
    
       186:     text = 'Hello world!'
       187:     try:
    -->188:         len.text
       189:     except Exception as e:

            text: 'Hello world!'
            len: <builtin function len>
        


Builtin module with no file
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 205, in test_Builtin_module_with_no_file
        sys.foo
    AttributeError: module 'sys' has no attribute 'foo'
    
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        Python nous dit qu’aucun objet avec le nom `foo` n’est
        dans le module `sys`.
        
    Exception levée à la ligne 205 du fichier TESTS:\runtime\test_attribute_error.py.
    
       203: 
       204:     try:
    -->205:         sys.foo
       206:     except Exception as e:

            sys: <module sys (builtin)>
        


Generic
~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 36, in test_Generic
        a.x  # Testing instance
    AttributeError: 'A' object has no attribute 'x'
    
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        L’objet `a` n’a pas d’attribut nommé `x`.
        
    Exception levée à la ligne 36 du fichier TESTS:\runtime\test_attribute_error.py.
    
       34:     try:
       35:         a = A()
    -->36:         a.x  # Testing instance
       37:     except Exception as e:

            a: <A object> from test_attribute_error.test_Generic
        


Module attribute typo
~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 113, in test_Module_attribute_typo
        math.cost
    AttributeError: module 'math' has no attribute 'cost'
    
        Vouliez-vous dire l’un des éléments suivants: `cos, cosh, acos` ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        Au lieu d’écrire `math.cost`, peut-être que vous vouliez écrire
        l'un des attributs suivants du module `math` :
        cos, cosh, acos
        
    Exception levée à la ligne 113 du fichier TESTS:\runtime\test_attribute_error.py.
    
       111: 
       112:     try:
    -->113:         math.cost
       114:     except Exception as e:

            math: <module math (builtin)>
        


FileNotFoundError
-----------------


Generic
~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_common.py", line 74, in create_tracebacks
        result, message = function()
    
           ... Plus de lignes non affichées. ...
    
      File "FRIENDLY:\friendly_traceback\info_specific.py", line 41, in _attribute_error
        return attribute_error.get_cause(value, frame, tb_data)
      File "FRIENDLY:\friendly_traceback\runtime_errors\attribute_error.py", line 36, in get_cause
        cause = _(
    KeyError: 'attar'
    
    Une exception `KeyError` est levée lorsqu’une valeur n’est pas trouvée
    en tant que clé dans un dictionnaire (dict) Python.
    
        Dans votre programme, la clé inconnue est `'attar'`.
        
    L'exécution s'est arrêtée à la ligne 74 du fichier TESTS:\trb_common.py
    
       72:                             function = getattr(mod, name)
       73:                             if callable(function):
    -->74:                                 result, message = function()
       75:                                 title = name[5:].replace("_", " ")

            result: '\n    Traceback (most recent call last):\n      File "TESTS...'
                len(result): 900
            message: "module 'math' has no attribute 'cost'"
            function: <function test_Nonetype>
        
    Exception levée à la ligne 36 du fichier FRIENDLY:\friendly_traceback\runtime_errors\attribute_error.py.
    
       34:     elif match3:
       35:         if match3.group(1) == "NoneType":
    -->36:             cause = _(
       37:                 "You are attempting to access the attribute `{attr}`\n"

            _: <bound method GNUTranslations.gettext of <gettext.GNUTranslations object>
            match3: <re.Match object; span=(0, 38), match="NoneType object has no attribute b">
            match3.group: <builtin method group of re.Match object>
            format: <builtin function format>
        

    Traceback (most recent call last):
      File "TESTS:\runtime\test_file_not_found_error.py", line 6, in test_Generic
        open("does_not_exist")
    FileNotFoundError: [Errno 2] No such file or directory: 'does_not_exist'
    
    Une exception `FileNotFoundError` indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe en
    écrivant le nom du fichier.
    
        Dans votre programme, le nom du fichier inconnu est `does_not_exist`.
        
    Exception levée à la ligne 6 du fichier TESTS:\runtime\test_file_not_found_error.py.
    
       4: def test_Generic():
       5:     try:
    -->6:         open("does_not_exist")
       7:     except Exception as e:

            open: <builtin function open>
        


ImportError
-----------


Circular import
~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_import_error.py", line 20, in test_Circular_import
        import circular_a
      File "TESTS:\circular_a.py", line 2, in <module>
        import circular_b
      File "TESTS:\circular_b.py", line 2, in <module>
        from circular_a import a
    ImportError: cannot import name 'a' from partially initialized module 'circular_a' (most likely due to a circular import) (C:\Users\andre\github\friendly-traceback\tests\circular_a.py)
    
    L'exception `ImportError` indique qu’un certain objet n’a pas pu
    être importé à partir d’un module ou d’un paquet. Très souvent, c’est
    parce que le nom de l’objet n’est pas écrit correctement.
    
        L’objet qui n’a pas pu être importé est `a`.
        Le module ou le paquet d'où il devait être importé est `circular_a`.
        
        Le problème a probablement été causé par ce qu’on appelle une « importation circulaire ».
        Tout d’abord, Python a importé et a commencé à exécuter le code dans le fichier
           'TESTS:\runtime\test_import_error.py'.
        qui importe le module `circular_a`.
        Au cours de ce processus, le code d’un autre fichier,
           'TESTS:\circular_b.py'
        a été exécuté. Toutefois, dans ce dernier dossier, une tentative a été
        pour importer le module d’origine `circular_a`
        une deuxième fois, avant que Python n’ait terminé la première importation.
        
    L'exécution s'est arrêtée à la ligne 20 du fichier TESTS:\runtime\test_import_error.py
    
       18: def test_Circular_import():
       19:     try:
    -->20:         import circular_a
       21:     except Exception as e:

    Exception levée à la ligne 2 du fichier TESTS:\circular_b.py.
    
       1: """File used in for test_circular_import() in test_import_error.py"""
    -->2: from circular_a import a


Simple import error
~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_import_error.py", line 6, in test_Simple_import_error
        from math import Pi
    ImportError: cannot import name 'Pi' from 'math' (unknown location)
    
        Vouliez-vous dire `pi` ?
        
    L'exception `ImportError` indique qu’un certain objet n’a pas pu
    être importé à partir d’un module ou d’un paquet. Très souvent, c’est
    parce que le nom de l’objet n’est pas écrit correctement.
    
        Peut-être que vous vouliez importer `pi` (de `math`) au lieu de `Pi`.
        
    Exception levée à la ligne 6 du fichier TESTS:\runtime\test_import_error.py.
    
       4: def test_Simple_import_error():
       5:     try:
    -->6:         from math import Pi
       7:     except Exception as e:


IndexError
----------


Long list
~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_index_error.py", line 22, in test_Long_list
        print(a[50], b[0])
    IndexError: list index out of range
    
    Une exception `IndexError` se produit lorsque vous essayez d’obtenir un élément
    d'une liste, d'un tuple, ou d'un objet similaire (séquence), à l’aide d’un index qui
    n’existe pas; typiquement, c’est parce que l’index que vous donnez
    est plus grand que la longueur de la séquence.
    Rappel: le premier élément d'une séquence est à l'index 0.
    
    Exception levée à la ligne 22 du fichier TESTS:\runtime\test_index_error.py.
    
       20:     b = tuple(range(50))
       21:     try:
    -->22:         print(a[50], b[0])
                         ^^^^^
       23:     except Exception as e:

            a: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, ...]
                len(a): 40
        


Short tuple
~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_index_error.py", line 8, in test_Short_tuple
        print(a[3], b[2])
    IndexError: tuple index out of range
    
    Une exception `IndexError` se produit lorsque vous essayez d’obtenir un élément
    d'une liste, d'un tuple, ou d'un objet similaire (séquence), à l’aide d’un index qui
    n’existe pas; typiquement, c’est parce que l’index que vous donnez
    est plus grand que la longueur de la séquence.
    Rappel: le premier élément d'une séquence est à l'index 0.
    
    Exception levée à la ligne 8 du fichier TESTS:\runtime\test_index_error.py.
    
        6:     b = [1, 2, 3]
        7:     try:
    --> 8:         print(a[3], b[2])
                         ^^^^
        9:     except Exception as e:

            a: (1, 2, 3)
        


KeyError
--------


Generic
~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_key_error.py", line 7, in test_Generic
        d["c"]
    KeyError: 'c'
    
    Une exception `KeyError` est levée lorsqu’une valeur n’est pas trouvée
    en tant que clé dans un dictionnaire (dict) Python.
    
        Dans votre programme, la clé inconnue est `'c'`.
        
    Exception levée à la ligne 7 du fichier TESTS:\runtime\test_key_error.py.
    
       5:     d = {"a": 1, "b": 2}
       6:     try:
    -->7:         d["c"]
       8:     except Exception as e:

            d: {'a': 1, 'b': 2}
        


LookupError
-----------


Generic
~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_lookup_error.py", line 10, in test_Generic
        raise LookupError("Fake message")
    LookupError: Fake message
    
    `LookupError` est la classe de base pour les exceptions qui sont levées
    lorsqu’une clé ou un index utilisé sur un tableau de correspondance ou une séquence est invalide.
    Elle peut également être levée directement par codecs.lookup().
    
    Exception levée à la ligne 10 du fichier TESTS:\runtime\test_lookup_error.py.
    
        8:         # other than possibly codecs.lookup(), which is why we raise
        9:         # it directly here for our example.
    -->10:         raise LookupError("Fake message")
       11:     except Exception as e:

            LookupError: <class LookupError>
        


ModuleNotFoundError
-------------------


Standard library module
~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_module_not_found_error.py", line 6, in test_Standard_library_module
        import Tkinter
    ModuleNotFoundError: No module named 'Tkinter'
    
        Vouliez-vous dire `tkinter` ?
        
    Une exception `ModuleNotFoundError` indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe en
    écrivant le nom du module, ou parce qu’il n’est pas installé sur votre ordinateur.
    
        Le nom du module qui n’a pas pu être importé est `Tkinter`.
        `tkinter` est un module existant qui a un nom similaire.
        
    Exception levée à la ligne 6 du fichier TESTS:\runtime\test_module_not_found_error.py.
    
       4: def test_Standard_library_module():
       5:     try:
    -->6:         import Tkinter
       7:     except Exception as e:


NameError
---------


Annotated variable
~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 21, in test_Annotated_variable
        y = x
    NameError: name 'x' is not defined
    
        Avez-vous utilisé deux points au lieu d’un signe égal ?
        
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
        Dans votre programme, `x` est un nom inconnu.
        Une annotation de type a été trouvée pour `x` dans la portée 'global'
        Peut-être que vous aviez utilisé deux points au lieu d’un signe égal et écrit
        
            x : 3
        
        au lieu de
        
            x = 3
        
    Exception levée à la ligne 21 du fichier TESTS:\runtime\test_name_error.py.
    
       19: def test_Annotated_variable():
       20:     try:
    -->21:         y = x
       22:     except Exception as e:


Generic
~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 6, in test_Generic
        this = something
    NameError: name 'something' is not defined
    
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
        Dans votre programme, `something` est un nom inconnu.
        Je n’ai pas d’informations supplémentaires pour vous.
    Exception levée à la ligne 6 du fichier TESTS:\runtime\test_name_error.py.
    
       4: def test_Generic():
       5:     try:
    -->6:         this = something
       7:     except Exception as e:


Synonym
~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 46, in test_Synonym
        cost  # wrote from math import * above
    NameError: name 'cost' is not defined
    
        Vouliez-vous dire `cos` ?
        
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
        Dans votre programme, `cost` est un nom inconnu.
        Au lieu d’écrire `cost`, peut-être que vous vouliez écrire l'un des noms suivants :
        *    Portée globale : `cos`, `cosh`, `acos`
        
    Exception levée à la ligne 46 du fichier TESTS:\runtime\test_name_error.py.
    
       44: 
       45:     try:
    -->46:         cost  # wrote from math import * above
       47:     except Exception as e:


OverflowError
-------------


Generic
~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_overflow_error.py", line 6, in test_Generic
        2.0 ** 1600
    OverflowError: (34, 'Result too large')
    
    Une exception de type `OverflowError` est levée lorsque le résultat d’une opération arithmétique
    est trop grand pour être manipulé par le processeur de l’ordinateur.
    
    Exception levée à la ligne 6 du fichier TESTS:\runtime\test_overflow_error.py.
    
       4: def test_Generic():
       5:     try:
    -->6:         2.0 ** 1600
       7:     except Exception as e:


RecursionError
--------------


Generic
~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_recursion_error.py", line 8, in test_Generic
        a()
    
           ... Plus de lignes non affichées. ...
    
      File "TESTS:\runtime\test_recursion_error.py", line 6, in a
        return a()
      File "TESTS:\runtime\test_recursion_error.py", line 6, in a
        return a()
    RecursionError: maximum recursion depth exceeded
    
    Une exception de type `RecursionError` est levée lorsqu’une fonction s'invoque elle-même,
    directement ou indirectement, trop de fois.
    Cette exception indique presque toujours que vous avez fait une erreur dans votre code
    et que votre programme ne terminerait jamais.
    
    L'exécution s'est arrêtée à la ligne 8 du fichier TESTS:\runtime\test_recursion_error.py
    
        6:         return a()
        7:     try:
    --> 8:         a()
        9:     except Exception as e:

            a: <function a> from test_Generic
        
    Exception levée à la ligne 6 du fichier TESTS:\runtime\test_recursion_error.py.
    
       4: def test_Generic():
       5:     def a():
    -->6:         return a()
                         ^^^
       7:     try:

            a: <function a> from test_Generic
        


TypeError
---------


UnboundLocalError
-----------------


UnknownError
------------


ValueError
----------


ZeroDivisionError
-----------------

