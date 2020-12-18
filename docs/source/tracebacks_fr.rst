
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

Friendly-traceback version: 0.2.7a
Python version: 3.8.4



ArithmeticError
---------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_arithmetic_error.py", line 9, in test_arithmetic_error
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


AttributeError - class attribute
--------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 35, in test_attribute_error
        a.x  # Testing instance
    AttributeError: 'A' object has no attribute 'x'
    
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        L’objet `a` n’a pas d’attribut nommé `x`.
        
    Exception levée à la ligne 35 du fichier TESTS:\runtime\test_attribute_error.py.
    
       33:     try:
       34:         a = A()
    -->35:         a.x  # Testing instance
       36:     except Exception as e:

            a: <A object> from test_attribute_error.test_attribute_error
        


AttributeError - typo in module attribute
-----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 66, in test_misspelled_module_attribute
        string.ascii_lowecase
    AttributeError: module 'string' has no attribute 'ascii_lowecase'
    
        Vouliez-vous dire `ascii_lowercase` ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        Peut-être que vous vouliez plutôt écrire : `string.ascii_lowercase` au lieu de `string.ascii_lowecase`.
        
    Exception levée à la ligne 66 du fichier TESTS:\runtime\test_attribute_error.py.
    
       64: 
       65:     try:
    -->66:         string.ascii_lowecase
       67:     except Exception as e:

            string: <module string> from PYTHON_LIB:\string.py
        


AttributeError - typo in module attribute 2
-------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 82, in test_misspelled_module_attribute_2
        math.cost
    AttributeError: module 'math' has no attribute 'cost'
    
        Vouliez-vous dire l’un des éléments suivants: `cos, cosh, acos` ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        Au lieu d’écrire `math.cost`, peut-être que vous vouliez écrire
        l'un des attributs suivants du module `math` :
        cos, cosh, acos
        
    Exception levée à la ligne 82 du fichier TESTS:\runtime\test_attribute_error.py.
    
       80: 
       81:     try:
    -->82:         math.cost
       83:     except Exception as e:

            math: <module math (builtin)>
        


FileNotFoundError
-----------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_file_not_found_error.py", line 6, in test_file_not_found_error
        open("does_not_exist")
    FileNotFoundError: [Errno 2] No such file or directory: 'does_not_exist'
    
    Une exception `FileNotFoundError` indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe en
    écrivant le nom du fichier.
    
        Dans votre programme, le nom du fichier inconnu est `does_not_exist`.
        
    Exception levée à la ligne 6 du fichier TESTS:\runtime\test_file_not_found_error.py.
    
       4: def test_file_not_found_error():
       5:     try:
    -->6:         open("does_not_exist")
       7:     except Exception as e:


ImportError
-----------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_import_error.py", line 6, in test_import_error
        from math import Pi
    ImportError: cannot import name 'Pi' from 'math' (unknown location)
    
        Vouliez-vous dire `pi` ?
        
    L'exception `ImportError` indique qu’un certain objet n’a pas pu
    être importé à partir d’un module ou d’un paquet. Très souvent, c’est
    parce que le nom de l’objet n’est pas écrit correctement.
    
        Peut-être que vous vouliez importer `pi` (de `math`) au lieu de `Pi`.
        
    Exception levée à la ligne 6 du fichier TESTS:\runtime\test_import_error.py.
    
       4: def test_import_error():
       5:     try:
    -->6:         from math import Pi
       7:     except Exception as e:


KeyError
--------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_key_error.py", line 7, in test_key_error
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

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_lookup_error.py", line 10, in test_lookup_error
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


IndexError - short tuple
------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_index_error.py", line 8, in test_index_error1
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
        


IndexError - long list
----------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_index_error.py", line 22, in test_index_error2
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
        


ModuleNotFoundError
-------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_module_not_found_error.py", line 6, in test_module_not_found_error
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
    
       4: def test_module_not_found_error():
       5:     try:
    -->6:         import Tkinter
       7:     except Exception as e:


NameError - 1
-------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 6, in test_name_error
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
    
       4: def test_name_error():
       5:     try:
    -->6:         this = something
       7:     except Exception as e:


NameError - 2
-------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 20, in test_name_error2
        x = babs(-1)
    NameError: name 'babs' is not defined
    
        Vouliez-vous dire `abs` ?
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
        Dans votre programme, `babs` est un nom inconnu.
        Au lieu d’écrire `babs`, peut-être que vous vouliez écrire l'un des noms suivants :
        *    Portée locale : `nabs`
        *    Portée globale : `fabs`
        *    Identifiant Python (builtins) : `abs`
        
    Exception levée à la ligne 20 du fichier TESTS:\runtime\test_name_error.py.
    
       18:     nabs = 1
       19:     try:
    -->20:         x = babs(-1)
       21:     except Exception as e:


NameError - 3
-------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 35, in test_name_error3
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
        
    Exception levée à la ligne 35 du fichier TESTS:\runtime\test_name_error.py.
    
       33: def test_name_error3():
       34:     try:
    -->35:         y = x
       36:     except Exception as e:


NameError - 4
-------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 48, in test_name_error4
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
        
    Exception levée à la ligne 48 du fichier TESTS:\runtime\test_name_error.py.
    
       46: def test_name_error4():
       47:     try:
    -->48:         cost  # wrote from math import * above
       49:     except Exception as e:


OverflowError
-------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_overflow_error.py", line 6, in test_overflow_error
        2.0 ** 1600
    OverflowError: (34, 'Result too large')
    
    Une exception de type `OverflowError` est levée lorsque le résultat d’une opération arithmétique
    est trop grand pour être manipulé par le processeur de l’ordinateur.
    
    Exception levée à la ligne 6 du fichier TESTS:\runtime\test_overflow_error.py.
    
       4: def test_overflow_error():
       5:     try:
    -->6:         2.0 ** 1600
       7:     except Exception as e:


RecursionError
--------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_recursion_error.py", line 8, in test_function_recursion_error
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

            a: <function a> from test_function_recursion_error
        
    Exception levée à la ligne 6 du fichier TESTS:\runtime\test_recursion_error.py.
    
       4: def test_function_recursion_error():
       5:     def a():
    -->6:         return a()
                         ^^^
       7:     try:

            a: <function a> from test_function_recursion_error
        


TypeError - 1: concatenate two different types
----------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 36, in test_type_error1
        result = a_tuple + a_list
    TypeError: can only concatenate tuple (not "list") to tuple
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé de concaténer (additionner) deux types d’objets différents:
        un `tuple` et une liste (`list`)
        
    Exception levée à la ligne 36 du fichier TESTS:\runtime\test_type_error.py.
    
       34:         a_tuple = (1, 2, 3)
       35:         a_list = [1, 2, 3]
    -->36:         result = a_tuple + a_list
                            ^^^^^^^^^^^^^^^^
       37:     except Exception as e:

            a_tuple: (1, 2, 3)
            a_list: [1, 2, 3]
        


TypeError - 2: unsupported operand type(s) for +=
-------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 90, in test_type_error2
        b -= a
    TypeError: unsupported operand type(s) for -=: 'list' and 'tuple'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez tenté de soustraire deux types d’objets incompatibles:
        une liste (`list`) et un `tuple`
        
    Exception levée à la ligne 90 du fichier TESTS:\runtime\test_type_error.py.
    
       88:         a = (1, 2)
       89:         b = [3, 4]
    -->90:         b -= a
       91:     except Exception as e:

            b: [3, 4]
            a: (1, 2)
        


TypeError - 3: unsupported operand type(s) for -=
-------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_common.py", line 171, in create_tracebacks
        result, message = getattr(mod, function)()
    AttributeError: module 'test_type_error' has no attribute 'test_type_error3'
    
        Vouliez-vous dire l’un des éléments suivants: `test_type_error13, test_type_error9, test_type_error8, test_type_error7, test_type_error6` ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        Au lieu d’écrire `test_type_error.test_type_error3`, peut-être que vous vouliez écrire
        l'un des attributs suivants du module `test_type_error` :
        test_type_error13, test_type_error9, test_type_error8, test_type_error7, test_type_error6
        
    Exception levée à la ligne 171 du fichier TESTS:\trb_common.py.
    
       169:                     mod = __import__(name)
       170:                     if function is not None:
    -->171:                         result, message = getattr(mod, function)()
                                                      ^^^^^^^^^^^^^^^^^^^^^^
       172:                         save_messages[function] = message

            mod: <module test_type_error> from TESTS:\runtime\test_type_error.py
            function: 'test_type_error3'
        

TypeError - 4: unsupported operand type(s) for ``*=``
-----------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 118, in test_type_error4
        b *= a
    TypeError: unsupported operand type(s) for *=: 'set' and 'complex'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé de multiplier deux types d’objets différents:
        un ensemble (`set`) et un nombre complexe (`complex`)
        
    Exception levée à la ligne 118 du fichier TESTS:\runtime\test_type_error.py.
    
       116:         a = 1j
       117:         b = {2, 3}
    -->118:         b *= a
       119:     except Exception as e:

            b: {2, 3}
            a: 1j
        


TypeError - 5: unsupported operand type(s) for //=
--------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 170, in test_type_error5
        b //= a
    TypeError: unsupported operand type(s) for //=: 'float' and 'dict'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé de diviser deux types d’objets différents:
        un nombre (`float`) et un dictionnaire (`dict`)
        
    Exception levée à la ligne 170 du fichier TESTS:\runtime\test_type_error.py.
    
       168:         a = {1: 1, 2: 2}
       169:         b = 3.1416
    -->170:         b //= a
       171:     except Exception as e:

            b: 3.1416
            a: {1: 1, 2: 2}
        


TypeError - 6: unsupported operand type(s) for &=
-------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 198, in test_type_error6
        b &= a
    TypeError: unsupported operand type(s) for &=: 'int' and 'str'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d’effectuer l’opération binaire bit à bit &=
        sur deux types d’objets incompatibles:
        un entier (`int`) et une chaîne de caractères (`str`)
        
    Exception levée à la ligne 198 du fichier TESTS:\runtime\test_type_error.py.
    
       196:         a = "a"
       197:         b = 2
    -->198:         b &= a
       199:     except Exception as e:

            b: 2
            a: 'a'
        


TypeError - 7: unsupported operand type(s) for ``**=``
------------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 226, in test_type_error7
        a **= b
    TypeError: unsupported operand type(s) for ** or pow(): 'dict' and 'float'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d'élever à une puissance
        en utilisant deux types d’objets incompatibles:
        un dictionnaire (`dict`) et un nombre (`float`)
        
    Exception levée à la ligne 226 du fichier TESTS:\runtime\test_type_error.py.
    
       224:         a = {1: 1, 2: 2}
       225:         b = 3.1416
    -->226:         a **= b
       227:     except Exception as e:

            a: {1: 1, 2: 2}
            b: 3.1416
        


TypeError - 8: unsupported operand type(s) for >>=
--------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 254, in test_type_error8
        a >>= b
    TypeError: unsupported operand type(s) for >>=: 'str' and 'int'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d’effectuer l’opération de décalage >>=
        sur deux types d’objets incompatibles:
        une chaîne de caractères (`str`) et un entier (`int`)
        
    Exception levée à la ligne 254 du fichier TESTS:\runtime\test_type_error.py.
    
       252:         a = "a"
       253:         b = 42
    -->254:         a >>= b
       255:     except Exception as e:

            a: 'a'
            b: 42
        


TypeError - 9: unsupported operand type(s) for @=
-------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 282, in test_type_error9
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
        


TypeError - 10: comparison between incompatible types
-----------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 298, in test_type_error10
        b < a
    TypeError: '<' not supported between instances of 'int' and 'str'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        En utilisant <, vous avez tenté de comparer
        deux types d’objets incompatibles:
        un entier (`int`) et une chaîne de caractères (`str`)
        
    Exception levée à la ligne 298 du fichier TESTS:\runtime\test_type_error.py.
    
       296:         a = "a"
       297:         b = 42
    -->298:         b < a
       299:     except Exception as e:

            b: 42
            a: 'a'
        


TypeError - 11: bad operand type for unary +
--------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_common.py", line 171, in create_tracebacks
        result, message = getattr(mod, function)()
      File "TESTS:\runtime\test_type_error.py", line 357, in test_type_error11
        assert "Perhaps you meant to write `+=`" in result
    AssertionError:
    
    Aucune information n’est disponible sur cette exception.
    
    L'exécution s'est arrêtée à la ligne 171 du fichier TESTS:\trb_common.py
    
       169:                     mod = __import__(name)
       170:                     if function is not None:
    -->171:                         result, message = getattr(mod, function)()
       172:                         save_messages[function] = message

            result: '\n    Traceback (most recent call last):\n      File "TESTS...'
                len(result): 894
            message: "'<' not supported between instances of 'int' and 'str'"
            mod: <module test_type_error> from TESTS:\runtime\test_type_error.py
            function: 'test_type_error11'
        
    Exception levée à la ligne 357 du fichier TESTS:\runtime\test_type_error.py.
    
       355:     assert not "debug_warning" in result, "Internal error found."
       356:     assert "TypeError: bad operand type for unary +: 'str'" in result
    -->357:     assert "Perhaps you meant to write `+=`" in result
       358:     if friendly_traceback.get_lang() == "en":

            result: '\n    Traceback (most recent call last):\n      File "TESTS...'
                len(result): 1053
        

TypeError - 12: object does not support item assignment
-------------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 366, in test_type_error12
        a[0] = 0
    TypeError: 'tuple' object does not support item assignment
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Dans Python, certains objets sont connus comme immuables:
        une fois définis, leur valeur ne peut pas être modifiée.
        Vous avez essayé de modifier une partie d’un tel objet immuable: un `tuple`,
        probablement en utilisant une opération d’indexation.
        
    Exception levée à la ligne 366 du fichier TESTS:\runtime\test_type_error.py.
    
       364:     a = (1, 2, 3)
       365:     try:
    -->366:         a[0] = 0
       367:     except Exception as e:

            a[0]: 1
            a: (1, 2, 3)
        


TypeError - 13: wrong number of positional arguments
----------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 398, in test_type_error13
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
        
    Exception levée à la ligne 398 du fichier TESTS:\runtime\test_type_error.py.
    
       396: 
       397:     try:
    -->398:         A().f(1)
       399:     except Exception as e:

            A: <class A> from test_type_error.test_type_error13
        


TypeError - 14: missing positional arguments
--------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 417, in test_type_error14
        fn(1)
    TypeError: fn() missing 2 required positional arguments: 'b' and 'c'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez apparemment invoqué la fonction 'fn()' avec
        moins d'arguments positionnels qu'il n'en faut (2 manquent).
        
    Exception levée à la ligne 417 du fichier TESTS:\runtime\test_type_error.py.
    
       415: 
       416:     try:
    -->417:         fn(1)
       418:     except Exception as e:

            fn: <function fn> from test_type_error14
        


TypeError - 15: list object is not callable
-------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 442, in test_type_error15
        _ = [1, 2](3, 4)
    TypeError: 'list' object is not callable
    
        Peut-être que vous aviez une virgule manquante avant le tuple.
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Je soupçonne que vous aviez un objet du type « une liste (`list`) »,
        suivi de ce qui ressemblait à un tuple, '(...) ',
        que Python a pris comme indiquant une invocation de fonction.
        Peut-être que vous aviez une virgule manquante avant le tuple.
        
    Exception levée à la ligne 442 du fichier TESTS:\runtime\test_type_error.py.
    
       440: 
       441:     try:
    -->442:         _ = [1, 2](3, 4)
                        ^^^^^^^^^^^^
       443:     except Exception as e:


TypeError - 16: exception derived from BaseException
----------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 455, in test_type_error16
        raise "exception"
    TypeError: exceptions must derive from BaseException
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Dans Python 3, les exceptions doivent être dérivées de BaseException.
        
    Exception levée à la ligne 455 du fichier TESTS:\runtime\test_type_error.py.
    
       453: def test_type_error16():
       454:     try:
    -->455:         raise "exception"
       456:     except Exception as e:


TypeError - 17: can't multiply sequence by non-int
--------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 510, in test_type_error17
        "a" * "2"
    TypeError: can't multiply sequence by non-int of type 'str'
    
        Avez-vous oublié de convertir `"2"` en un entier?
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous ne pouvez multiplier les séquences, telles que
        les listes, les tuples, les chaînes, etc., que par des entiers.
        Peut-être avez-vous oublié de convertir `"2"` en un entier.
        
    Exception levée à la ligne 510 du fichier TESTS:\runtime\test_type_error.py.
    
       508: 
       509:     try:
    -->510:         "a" * "2"
       511:     except Exception as e:


TypeError - 18: object cannot be interpreted as an integer
----------------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 558, in test_type_error18
        range(c, d)
    TypeError: 'str' object cannot be interpreted as an integer
    
        Avez-vous oublié de convertir `c, d` en entiers?
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez écrit un objet de type `str` là où un entier était attendu.
        Peut-être avez-vous oublié de convertir `c, d` en entiers?
    Exception levée à la ligne 558 du fichier TESTS:\runtime\test_type_error.py.
    
       556:     c, d = "2", "3"
       557:     try:
    -->558:         range(c, d)
       559:     except Exception as e:

            c: '2'
            d: '3'
        


UnboundLocalError - 1: missing global
-------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_unbound_local_error.py", line 27, in test_unbound_local_error_missing_global
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
        


UnboundLocalError - 2: missing nonlocal
---------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_unbound_local_error.py", line 48, in test_unbound_local_error_missing_nonlocal
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


Unknown exception
-----------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_unknown_error.py", line 10, in test_function_unknown_error
        raise MyException("Some informative message about an unknown exception.")
    MyException: Some informative message about an unknown exception.
    
    Aucune information n’est disponible sur cette exception.
    
    Exception levée à la ligne 10 du fichier TESTS:\runtime\test_unknown_error.py.
    
        8: def test_function_unknown_error():
        9:     try:
    -->10:         raise MyException("Some informative message about an unknown exception.")
       11:     except Exception as e:

            global MyException: <class test_unknown_error.MyException>
        


ZeroDivisionError - 1
---------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_zero_division_error.py", line 6, in test_zero_division_error
        1 / 0
    ZeroDivisionError: division by zero
    
    Une exception de type `ZeroDivisionError` se produit lorsque
    vous tentez de diviser une valeur par zéro:
        `résultat = ma_variable / 0.`
    Ceci peut également se produire si vous calculez le reste d’une division 
    à l’aide de l’opérateur modulo '%'
        `résultat = ma_variable % 0`
    
    Exception levée à la ligne 6 du fichier TESTS:\runtime\test_zero_division_error.py.
    
       4: def test_zero_division_error():
       5:     try:
    -->6:         1 / 0
       7:     except Exception as e:


ZeroDivisionError - 2
---------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_zero_division_error.py", line 21, in test_zero_division_error2
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
        

