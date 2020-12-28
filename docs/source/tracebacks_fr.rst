
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

Friendly-traceback version: 0.2.14a
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
        


Nonetype
~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 152, in test_Nonetype
        a.b
    AttributeError: 'NoneType' object has no attribute 'b'
    
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        Exception soulevée par Friendly-traceback.
        Veuillez signaler cet exemple à
        https://github.com/aroberge/friendly-traceback/issues
        
    Exception levée à la ligne 152 du fichier TESTS:\runtime\test_attribute_error.py.
    
       150:     a = None
       151:     try:
    -->152:         a.b
       153:     except Exception as e:

            a: None
        


Object attribute typo
~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 52, in test_Object_attribute_typo
        a.appendh(4)
    AttributeError: 'list' object has no attribute 'appendh'
    
        Vouliez-vous dire `append` ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        Peut-être que vous vouliez plutôt écrire : `a.append` au lieu de `a.appendh`.
        
    Exception levée à la ligne 52 du fichier TESTS:\runtime\test_attribute_error.py.
    
       50:     try:
       51:         a = [1, 2, 3]
    -->52:         a.appendh(4)
                   ^^^^^^^^^
       53:     except Exception as e:

            a: [1, 2, 3]
        


Perhaps comma
~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 171, in test_Perhaps_comma
        a = [abcd
    AttributeError: 'str' object has no attribute 'defg'
    
        Vouliez-vous séparer les noms d’objets par une virgule ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        `defg` n’est pas un attribut de `abcd`.
        Cependant, les objets `abcd` et `defg` sont des objets connus.
        Peut-être avez-vous écrit une période pour séparer ces deux objets, 
        au lieu d’utiliser une virgule.
        
    Exception levée à la ligne 171 du fichier TESTS:\runtime\test_attribute_error.py.
    
       169:     # fmt: off
       170:     try:
    -->171:         a = [abcd
       172:         .defg]

            abcd: 'hello'
            defg: 'world'
        


Shadow stdlib module
~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 134, in test_Shadow_stdlib_module
        turtle.Pen
    AttributeError: module 'turtle' has no attribute 'Pen'
    
        Avez-vous donné à votre programme le même nom qu’un module Python ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        Vous avez importé un module nommé `turtle` de `TESTS:\turtle.py`.
        Il y a aussi un module nommé `turtle` dans la bibliothèque standard de Python.
        Peut-être avez-vous besoin de renommer votre module.
        
    Exception levée à la ligne 134 du fichier TESTS:\runtime\test_attribute_error.py.
    
       132: 
       133:     try:
    -->134:         turtle.Pen
       135:     except Exception as e:

            turtle: <module turtle> from TESTS:\turtle.py
        


Use builtin
~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 68, in test_Use_builtin
        a.length()
    AttributeError: 'list' object has no attribute 'length'
    
        Vouliez-vous utiliser `len(a)` ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        L’objet `a` n’a pas d’attribut nommé `length`.
        Peut-être pouvez-vous utiliser la fonction Python builtin `len` à la place:
        `len(a)`.
    Exception levée à la ligne 68 du fichier TESTS:\runtime\test_attribute_error.py.
    
       66:     try:
       67:         a = [1, 2, 3]
    -->68:         a.length()
                   ^^^^^^^^
       69:     except Exception as e:

            a: [1, 2, 3]
        


Use synonym
~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 84, in test_Use_synonym
        a.add(4)
    AttributeError: 'list' object has no attribute 'add'
    
        Vouliez-vous dire `append` ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        L’objet `a` n’a pas d’attribut nommé `add`.
        Toutefois, `a` a les attributs suivants avec des sens similaires:
        'append, extend, insert'.
        
    Exception levée à la ligne 84 du fichier TESTS:\runtime\test_attribute_error.py.
    
       82:     try:
       83:         a = [1, 2, 3]
    -->84:         a.add(4)
                   ^^^^^
       85:     except Exception as e:

            a: [1, 2, 3]
        


FileNotFoundError
-----------------


Generic
~~~~~~~

.. code-block:: none


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
      File "TESTS:\runtime\test_index_error.py", line 24, in test_Long_list
        print(a[50], b[0])
    IndexError: list index out of range
    
    Une exception `IndexError` se produit lorsque vous essayez d’obtenir un élément
    d'une liste, d'un tuple, ou d'un objet similaire (séquence), à l’aide d’un index qui
    n’existe pas; typiquement, c’est parce que l’index que vous donnez
    est plus grand que la longueur de la séquence.
    
        Vous avez essayé d’obtenir l’élément avec l’index `50` de `a`,
        une liste (`list`) de longueur `40`.
        
    Exception levée à la ligne 24 du fichier TESTS:\runtime\test_index_error.py.
    
       22:     b = tuple(range(50))
       23:     try:
    -->24:         print(a[50], b[0])
                         ^^^^^
       25:     except Exception as e:

            a: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, ...]
                len(a): 40
        


Short tuple
~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_index_error.py", line 8, in test_Short_tuple
        print(a[3], b[2])
    IndexError: tuple index out of range
    
        N’oubliez pas : le premier élément d'un objet de type `un `tuple`` est à l’indice 0.
        
    Une exception `IndexError` se produit lorsque vous essayez d’obtenir un élément
    d'une liste, d'un tuple, ou d'un objet similaire (séquence), à l’aide d’un index qui
    n’existe pas; typiquement, c’est parce que l’index que vous donnez
    est plus grand que la longueur de la séquence.
    
        Vous avez essayé d’obtenir l’élément avec l’index `3` de `a`,
        un `tuple` de longueur `3`.
        Le plus grand indice valide de `a` est `2`.
        
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


Not a package
~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_module_not_found_error.py", line 41, in test_Not_a_package
        import os.pathh
    ModuleNotFoundError: No module named 'os.pathh'; 'os' is not a package
    
        Vouliez-vous dire `import os.path` ?
        
    Une exception `ModuleNotFoundError` indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe en
    écrivant le nom du module, ou parce qu’il n’est pas installé sur votre ordinateur.
    
        Peut-être que vous vouliez dire `import os.path`.
        `path` est un nom semblable à `pathh` et est un module qui
        peut être importé de `os`.
        D’autres objets avec des noms similaires qui font partie de
        `os` comprennent `fspath`.
        
    Exception levée à la ligne 41 du fichier TESTS:\runtime\test_module_not_found_error.py.
    
       39: 
       40:     try:
    -->41:         import os.pathh
       42:     except Exception as e:


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
                       ^
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
                         ^^^^^^^^^
       7:     except Exception as e:


Synonym
~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 66, in test_Synonym
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
        
    Exception levée à la ligne 66 du fichier TESTS:\runtime\test_name_error.py.
    
       64: 
       65:     try:
    -->66:         cost  # wrote from math import * above
                   ^^^^
       67:     except Exception as e:


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
    
        return a()
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


Bad type for unary operator
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 348, in test_Bad_type_for_unary_operator
        a =+ "def"
    TypeError: bad operand type for unary +: 'str'
    
        Peut-être que vous vouliez plutôt écrire `+=` au lieu de `=+`
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d’utiliser l’opérateur unaire '+'
        avec le type d’objet suivant: une chaîne de caractères (`str`).
        Cette opération n’est pas définie pour ce type d’objet.
        
        Peut-être que vous vouliez plutôt écrire `+=` au lieu de `=+`
        
    Exception levée à la ligne 348 du fichier TESTS:\runtime\test_type_error.py.
    
       346:         # fmt: off
       347:         a = "abc"
    -->348:         a =+ "def"
                       ^^^^^^^
       349:         # fmt: on


Can only concatenate
~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 36, in test_Can_only_concatenate
        result = a_tuple + a_list
    TypeError: can only concatenate tuple (not "list") to tuple
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé de concaténer (additionner) deux types d’objets différents:
        un `tuple` et une liste (`list`).
        
    Exception levée à la ligne 36 du fichier TESTS:\runtime\test_type_error.py.
    
       34:         a_tuple = (1, 2, 3)
       35:         a_list = [1, 2, 3]
    -->36:         result = a_tuple + a_list
                            ^^^^^^^^^^^^^^^^
       37:     except Exception as e:

            a_tuple: (1, 2, 3)
            a_list: [1, 2, 3]
        


Cannot convert dictionary update sequence
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 752, in test_Cannot_convert_dictionary_update_sequence
        dd.update([1, 2, 3])
    TypeError: cannot convert dictionary update sequence element #0 to a sequence
    
        Peut-être que vous vouliez plutôt utiliser la méthode `dict.fromkeys()`.
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        `dict.update()` n’accepte pas une séquence comme argument.
        Au lieu d’écrire `dd.update([1, 2, 3])`
        peut-être devriez-vous utiliser la méthode `dict.fromkeys()` : `dd.update( dict.fromkeys([1, 2, 3]) )`.
        
    Exception levée à la ligne 752 du fichier TESTS:\runtime\test_type_error.py.
    
       750:     dd = {"a": "a"}
       751:     try:
    -->752:         dd.update([1, 2, 3])
       753:     except Exception as e:

            dd: {'a': 'a'}
            dd.update: <builtin method update of dict object>
        


Cannot multiply by non int
~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 546, in test_Cannot_multiply_by_non_int
        "a" * "2"
    TypeError: can't multiply sequence by non-int of type 'str'
    
        Avez-vous oublié de convertir `"2"` en un entier ?
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous ne pouvez multiplier les séquences, telles que
        les listes, les tuples, les chaînes, etc., que par des entiers.
        Peut-être avez-vous oublié de convertir `"2"` en un entier.
        
    Exception levée à la ligne 546 du fichier TESTS:\runtime\test_type_error.py.
    
       544: 
       545:     try:
    -->546:         "a" * "2"
       547:     except Exception as e:


Cannot unpack non iterable object
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 724, in test_Cannot_unpack_non_iterable_object
        a, b = 42.0
    TypeError: cannot unpack non-iterable float object
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Le dépaquetage ('unpack') est un moyen pratique d’attribuer un nom
        à chaque élément d’un itérable.
        Un itérable est un objet capable de renvoyer ses membres un à la fois.
        Les contenants python (`list, tuple, dict`, etc.) sont itérables,
        mais pas les objets de type `float`.
        
    Exception levée à la ligne 724 du fichier TESTS:\runtime\test_type_error.py.
    
       722: def test_Cannot_unpack_non_iterable_object():
       723:     try:
    -->724:         a, b = 42.0
       725:     except Exception as e:


Comparison not supported
~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 298, in test_Comparison_not_supported
        b < a
    TypeError: '<' not supported between instances of 'int' and 'str'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        En utilisant <, vous avez tenté de comparer
        deux types d’objets incompatibles:
        un entier (`int`) et une chaîne de caractères (`str`).
        
    Exception levée à la ligne 298 du fichier TESTS:\runtime\test_type_error.py.
    
       296:         a = "a"
       297:         b = 42
    -->298:         b < a
       299:     except Exception as e:

            b: 42
            a: 'a'
        


Derive from BaseException
~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 489, in test_Derive_from_BaseException
        raise "exception"
    TypeError: exceptions must derive from BaseException
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Dans Python 3, les exceptions doivent être dérivées de BaseException.
        
    Exception levée à la ligne 489 du fichier TESTS:\runtime\test_type_error.py.
    
       487: def test_Derive_from_BaseException():
       488:     try:
    -->489:         raise "exception"
       490:     except Exception as e:


Indices must be integers or slices
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 628, in test_Indices_must_be_integers_or_slices
        [1, 2, 3]["2"]
    TypeError: list indices must be integers or slices, not str
    
        Avez-vous oublié de convertir `"2"` en un entier ?
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Dans l’expression `[1, 2, 3]["2"]`
        ce qui est inclus entre les crochets, `[...]`,
        doit être soit un entier ou une tranche
        (`start:stop` ou `start:stop:step`) 
        et vous l’avez utilisé une chaîne de caractères (`str`) la place.
        
        Peut-être avez-vous oublié de convertir `"2"` en un entier.
        
    Exception levée à la ligne 628 du fichier TESTS:\runtime\test_type_error.py.
    
       626: 
       627:     try:
    -->628:         [1, 2, 3]["2"]
       629:     except Exception as e:


Not an integer
~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 591, in test_Not_an_integer
        range(c, d)
    TypeError: 'str' object cannot be interpreted as an integer
    
        Avez-vous oublié de convertir `c, d` en entiers ?
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez écrit un objet de type `str` là où un entier était attendu.
        Peut-être avez-vous oublié de convertir `c, d` en entiers.
    Exception levée à la ligne 591 du fichier TESTS:\runtime\test_type_error.py.
    
       589:     c, d = "2", "3"
       590:     try:
    -->591:         range(c, d)
       592:     except Exception as e:

            c: '2'
            d: '3'
            range: <class range>
        


Not callable
~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 476, in test_Not_callable
        _ = [1, 2](3 + 4)
    TypeError: 'list' object is not callable
    
        Vouliez-vous dire `[1, 2][3 + 4]` ?
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        En raison des parenthees, `(3 + 4)` est interprété par Python
        comme indiquant une invocation de fonction pour 
        `[1, 2]`, qui est un objet de type `list`
        ne pouvant pas être invoqué.
        
        Cependant, `[1, 2]` est une séquence.
        Peut-être que vous vouliez utiliser `[]` au lieu de `()` et écrire
        `[1, 2][3 + 4]`
        
    Exception levée à la ligne 476 du fichier TESTS:\runtime\test_type_error.py.
    
       474: 
       475:     try:
    -->476:         _ = [1, 2](3 + 4)
                        ^^^^^^^^^^^^^
       477:     except Exception as e:


Object is not iterable
~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 710, in test_Object_is_not_iterable
        list(42)
    TypeError: 'int' object is not iterable
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Un itérable est un objet capable de renvoyer ses membres un à la fois.
        Les contenants python (`list, tuple, dict`, etc.) sont itérables.
        Une itérable est requis ici.
        
    Exception levée à la ligne 710 du fichier TESTS:\runtime\test_type_error.py.
    
       708: def test_Object_is_not_iterable():
       709:     try:
    -->710:         list(42)
       711:     except Exception as e:

            list: <class list>
        


Object is not subscriptable
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 696, in test_Object_is_not_subscriptable
        a = f[1]
    TypeError: 'function' object is not subscriptable
    
        Vouliez-vous dire `f(1)` ?
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Les objets subscriptibles sont généralement des conteneurs à partir
        desquels on peut tirer des éléments en utilisant la notation '[...] `.
        
        Peut-être que vous vouliez plutôt écrire `f(1)`.
        
    Exception levée à la ligne 696 du fichier TESTS:\runtime\test_type_error.py.
    
       694: 
       695:     try:
    -->696:         a = f[1]
                        ^^^^
       697:     except Exception as e:

            f: <function f> from test_Object_is_not_subscriptable
        


Slice indices must be integers or None
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 642, in test_Slice_indices_must_be_integers_or_None
        [1, 2, 3][1.0:2.0]
    TypeError: slice indices must be integers or None or have an __index__ method
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Lors de l’utilisation d’une tranche pour extraire une gamme d’éléments
        d’une séquence, c’est-à-dire quelque chose comme
        `[start:stop]` ou `[start:stop:step]`
        chacune des variables `start`, `stop`, et `step` doit être soit un entier, soit `None`,
        ou possiblement un autre objet ayant une méthode `__index__`.
        
    Exception levée à la ligne 642 du fichier TESTS:\runtime\test_type_error.py.
    
       640: def test_Slice_indices_must_be_integers_or_None():
       641:     try:
    -->642:         [1, 2, 3][1.0:2.0]
       643:     except Exception as e:


Too few positional argument
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 418, in test_Too_few_positional_argument
        fn(1)
    TypeError: fn() missing 2 required positional arguments: 'b' and 'c'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez apparemment invoqué la fonction 'fn()' avec
        moins d'arguments positionnels qu'il n'en faut (2 manquent).
        
    Exception levée à la ligne 418 du fichier TESTS:\runtime\test_type_error.py.
    
       416: 
       417:     try:
    -->418:         fn(1)
       419:     except Exception as e:

            fn: <function fn> from test_Too_few_positional_argument
        


Too many positional argument
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 399, in test_Too_many_positional_argument
        A().f(1)
    TypeError: f() takes 1 positional argument but 2 were given
    
        Peut-être avez-vous oublié `self` lors de la définition de `f`.
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez apparemment invoqué la fonction `f` avec
        2 arguments positionnels alors qu'elle en requiert 1.
        Peut-être avez-vous oublié `self` lors de la définition de `f`.
        
    Exception levée à la ligne 399 du fichier TESTS:\runtime\test_type_error.py.
    
       397: 
       398:     try:
    -->399:         A().f(1)
       400:     except Exception as e:

            A: <class A> from test_type_error.test_Too_many_positional_argument
        


Tuple no item assignment
~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 366, in test_Tuple_no_item_assignment
        a[0] = 0
    TypeError: 'tuple' object does not support item assignment
    
        Voulez-vous utiliser une liste?
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Dans Python, certains objets sont connus comme immuables:
        une fois définis, leur valeur ne peut pas être modifiée.
        Vous avez essayé de modifier une partie d’un tel objet immuable: un `tuple`,
        probablement en utilisant une opération d’indexation.
        Peut-être que vous vouliez plutôt utiliser une liste.
        
    Exception levée à la ligne 366 du fichier TESTS:\runtime\test_type_error.py.
    
       364:     a = (1, 2, 3)
       365:     try:
    -->366:         a[0] = 0
       367:     except Exception as e:

            a[0]: 1
            a: (1, 2, 3)
        


Unhachable type
~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 659, in test_Unhachable_type
        {[1, 2]: 1}
    TypeError: unhashable type: 'list'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Les objets non hachables sont des objets qui ne changent pas de valeur
        une fois qu’ils sont créés. Seuls les objets non hachables peuvent être utilisés
        comme éléments de `set` ou des clés de `dict`.
        Au lieu d’utiliser une liste (`list`), envisagez d’utiliser un `tuple`.
        
    Exception levée à la ligne 659 du fichier TESTS:\runtime\test_type_error.py.
    
       657: def test_Unhachable_type():
       658:     try:
    -->659:         {[1, 2]: 1}
       660:     except Exception as e:


Unsupported operand types
~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 282, in test_Unsupported_operand_types
        a @= b
    TypeError: unsupported operand type(s) for @=: 'str' and 'int'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d’utiliser l’opérateur @=
        à l’aide de deux types d’objets incompatibles:
        une chaîne de caractères (`str`) et un entier (`int`).
        Cet opérateur est normalement utilisé uniquement
        pour la multiplication des matrices.
        
    Exception levée à la ligne 282 du fichier TESTS:\runtime\test_type_error.py.
    
       280:         a = "a"
       281:         b = 2
    -->282:         a @= b
       283:     except Exception as e:

            a: 'a'
            b: 2
        


UnboundLocalError
-----------------


Missing global
~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_unbound_local_error.py", line 27, in test_Missing_global
        outer_missing_global()
      File "TESTS:\runtime\test_unbound_local_error.py", line 11, in outer_missing_global
        inner()
      File "TESTS:\runtime\test_unbound_local_error.py", line 9, in inner
        spam_missing_global += 1
    UnboundLocalError: local variable 'spam_missing_global' referenced before assignment
    
        Avez-vous oublié d’ajouter `global spam_missing_global` ?
        
    En Python, les variables utilisées à l’intérieur d’une fonction sont appelées
    variables «locales».
    Avant d’utiliser une variable locale, une valeur doit lui être attribuée.
    Une variable utilisée avant l’attribution d’une valeur est supposée
    être définie en dehors de cette fonction;
    elle est connu comme une variable «globale» (`global` ou parfois `nonlocal`).
    Vous ne pouvez pas assigner une valeur à une telle variable globale
    à l’intérieur d’une fonction sans d’abord confirmer à python
    qu’il s’agit d’une variable globale, sinon vous verrez une exception `UnboundLocalError`.
    
        Le nom `spam_missing_global` existe dans la portée global.
        Peut-être la déclaration
        
            global spam_missing_global
        
        aurait dû être incluse comme première ligne à l’intérieur de votre fonction.
        
    L'exécution s'est arrêtée à la ligne 27 du fichier TESTS:\runtime\test_unbound_local_error.py
    
       25: 
       26:     try:
    -->27:         outer_missing_global()
       28:     except Exception as e:

            global outer_missing_global: <function outer_missing_global>
        
    Exception levée à la ligne 9 du fichier TESTS:\runtime\test_unbound_local_error.py.
    
        7: def outer_missing_global():
        8:     def inner():
    --> 9:         spam_missing_global += 1

            global spam_missing_global: 1
        


Missing nonlocal
~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_unbound_local_error.py", line 48, in test_Missing_nonlocal
        outer_missing_nonlocal()
      File "TESTS:\runtime\test_unbound_local_error.py", line 20, in outer_missing_nonlocal
        inner()
      File "TESTS:\runtime\test_unbound_local_error.py", line 18, in inner
        spam_missing_nonlocal += 1
    UnboundLocalError: local variable 'spam_missing_nonlocal' referenced before assignment
    
        Avez-vous oublié d’ajouter `nonlocal spam_missing_nonlocal` ?
        
    En Python, les variables utilisées à l’intérieur d’une fonction sont appelées
    variables «locales».
    Avant d’utiliser une variable locale, une valeur doit lui être attribuée.
    Une variable utilisée avant l’attribution d’une valeur est supposée
    être définie en dehors de cette fonction;
    elle est connu comme une variable «globale» (`global` ou parfois `nonlocal`).
    Vous ne pouvez pas assigner une valeur à une telle variable globale
    à l’intérieur d’une fonction sans d’abord confirmer à python
    qu’il s’agit d’une variable globale, sinon vous verrez une exception `UnboundLocalError`.
    
        Le nom `spam_missing_nonlocal` existe dans la portée nonlocal.
        Peut-être la déclaration
        
            nonlocal spam_missing_nonlocal
        
        aurait dû être incluse comme première ligne à l’intérieur de votre fonction.
        
    L'exécution s'est arrêtée à la ligne 48 du fichier TESTS:\runtime\test_unbound_local_error.py
    
       46: 
       47:     try:
    -->48:         outer_missing_nonlocal()
       49:     except Exception as e:

            global outer_missing_nonlocal: <function outer_missing_nonlocal>
        
    Exception levée à la ligne 18 du fichier TESTS:\runtime\test_unbound_local_error.py.
    
       16: 
       17:     def inner():
    -->18:         spam_missing_nonlocal += 1


UnknownError
------------


Generic
~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_unknown_error.py", line 10, in test_Generic
        raise MyException("Some informative message about an unknown exception.")
    MyException: Some informative message about an unknown exception.
    
    Aucune information n’est disponible sur cette exception.
    
    Exception levée à la ligne 10 du fichier TESTS:\runtime\test_unknown_error.py.
    
        8: def test_Generic():
        9:     try:
    -->10:         raise MyException("Some informative message about an unknown exception.")
       11:     except Exception as e:

            global MyException: <class test_unknown_error.MyException>
        


ValueError
----------


Not enough values to unpack
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_value_error.py", line 28, in test_Not_enough_values_to_unpack
        a, b, c = d
    ValueError: not enough values to unpack (expected 3, got 2)
    
    Une exception `ValueError` indique qu'une fonction ou une opération
    a reçu un argument du bon type, mais une valeur inappropriée.
    
        Le dépaquetage ('unpack') est un moyen pratique d’attribuer un nom
        à chaque élément d’un itérable.
        Dans ce cas-ci, il y a plus de noms (3)
        que la longueur de l’itérable, une chaîne de caractères (`str`) de longueur 2.
        
    Exception levée à la ligne 28 du fichier TESTS:\runtime\test_value_error.py.
    
       26:     d = "ab"
       27:     try:
    -->28:         a, b, c = d
       29:     except Exception as e:

            d: 'ab'
        


Too many values to unpack
~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_value_error.py", line 43, in test_Too_many_values_to_unpack
        a, b = c
    ValueError: too many values to unpack (expected 2)
    
    Une exception `ValueError` indique qu'une fonction ou une opération
    a reçu un argument du bon type, mais une valeur inappropriée.
    
        Le dépaquetage ('unpack') est un moyen pratique d’attribuer un nom
        à chaque élément d’un itérable.
        Dans ce cas-ci, il y a moins de noms (2)
        que la longueur de l’itérable, une liste (`list`) de longueur 3.
        
    Exception levée à la ligne 43 du fichier TESTS:\runtime\test_value_error.py.
    
       41:     c = [1, 2, 3]
       42:     try:
    -->43:         a, b = c
       44:     except Exception as e:

            c: [1, 2, 3]
        


ZeroDivisionError
-----------------


Division operator
~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_zero_division_error.py", line 6, in test_Division_operator
        1 / 0
    ZeroDivisionError: division by zero
    
    Une exception de type `ZeroDivisionError` se produit lorsque
    vous tentez de diviser une valeur par zéro:
        `résultat = ma_variable / 0.`
    Ceci peut également se produire si vous calculez le reste d’une division 
    à l’aide de l’opérateur modulo '%'
        `résultat = ma_variable % 0`
    
    Exception levée à la ligne 6 du fichier TESTS:\runtime\test_zero_division_error.py.
    
       4: def test_Division_operator():
       5:     try:
    -->6:         1 / 0
       7:     except Exception as e:


Modulo operator
~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_zero_division_error.py", line 21, in test_Modulo_operator
        1 % zero
    ZeroDivisionError: integer division or modulo by zero
    
    Une exception de type `ZeroDivisionError` se produit lorsque
    vous tentez de diviser une valeur par zéro:
        `résultat = ma_variable / 0.`
    Ceci peut également se produire si vous calculez le reste d’une division 
    à l’aide de l’opérateur modulo '%'
        `résultat = ma_variable % 0`
    
    Exception levée à la ligne 21 du fichier TESTS:\runtime\test_zero_division_error.py.
    
       19:     zero = 0
       20:     try:
    -->21:         1 % zero
       22:     except Exception as e:

            zero: 0
        

