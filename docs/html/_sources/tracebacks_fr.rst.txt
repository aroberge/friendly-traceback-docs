
|france| Friendly tracebacks - en Français
===========================================

Le but principal de friendly est de fournir des rétroactions plus
conviviales que les fameux **tracebacks** de Python lorsqu'une exception survient.

.. note::

     Le contenu de cette page a été généré par l'exécution de
     trb_french.py situé dans le répertoire ``tests/``.
     Ceci a besoin d'être fait de manière explicite lorsqu'on veut
     faire des corrections ou des ajouts, avant de faire la mise
     à jour du reste de la documentation avec Sphinx.

Friendly version: 0.3.142
Python version: 3.8.10



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
       10:     except ArithmeticError as e:

            ArithmeticError:  <class ArithmeticError>
        


AssertionError
--------------


Generic
~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_assertion_error.py", line 8, in test_Generic
        raise AssertionError("Fake message")
    AssertionError: Fake message
    
    Dans Python, le mot clé `assert` est utilisé dans des énoncés ayant la forme
    `assert condition`, pour confirmer que `condition` n’est pas `False`;
    ni équivalente à `False` comme une liste vide, etc.
    
    Si `condition` est `False` ou son équivalent, une exception de type `AssertionError` est levée.
    
    Exception levée à la ligne 8 du fichier TESTS:\runtime\test_assertion_error.py.
    
        6:         # We raise it explicitly, rather than with the keyword assert, since
        7:         # we don't want pytest to rewrite out test.
    --> 8:         raise AssertionError("Fake message")
        9:     except AssertionError as e:

            AssertionError:  <class AssertionError>
        


AttributeError
--------------


Attribute from other module
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 299, in test_Attribute_from_other_module
        keyword.pi
    AttributeError: module 'keyword' has no attribute 'pi'
    
        Vouliez-vous dire l’un des modules suivants: `math, cmath` ?
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    Au lieu du module `keyword`, peut-être vouliez-vous utiliser l’attribut `pi` de 
    l'un des modules suivants:
    `math, cmath` .
    
    Exception levée à la ligne 299 du fichier TESTS:\runtime\test_attribute_error.py.
    
       297:     import cmath
       298:     try:
    -->299:         keyword.pi
       300:     except AttributeError as e:

            keyword:  <module keyword> from PYTHON_LIB:\keyword.py
        


Builtin function
~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 217, in test_Builtin_function
        len.text
    AttributeError: 'builtin_function_or_method' object has no attribute 'text'
    
        Vouliez-vous dire `len(text)` ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    `len` est une fonction. Peut-être que vous vouliez écrire
    `len(text)`
    
    Exception levée à la ligne 217 du fichier TESTS:\runtime\test_attribute_error.py.
    
       215:     text = 'Hello world!'
       216:     try:
    -->217:         len.text
       218:     except AttributeError as e:

            text:  'Hello world!'
            len:  <builtin function len>
        


Builtin module with no file
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 234, in test_Builtin_module_with_no_file
        sys.foo
    AttributeError: module 'sys' has no attribute 'foo'
    
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    Python nous dit qu’aucun objet avec le nom `foo` n’est
    dans le module `sys`.
    
    Exception levée à la ligne 234 du fichier TESTS:\runtime\test_attribute_error.py.
    
       232: 
       233:     try:
    -->234:         sys.foo
       235:     except AttributeError as e:

            sys:  <module sys (builtin)>
        


Circular import
~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 329, in test_Circular_import
        import my_turtle1
      File "TESTS:\my_turtle1.py", line 4, in <module>
        a = my_turtle1.something
    AttributeError: partially initialized module 'my_turtle1' has no attribute 'something' (most likely due to a circular import)
    
        Avez-vous donné à votre programme le même nom qu’un module Python ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    Je soupçonne que vous avez utilisé le nom `my_turtle1.py` pour votre programme
    et que vous vouliez aussi importer un module du même nom
    de la bibliothèque standard de Python.
    Si c’est le cas, vous devriez utiliser un nom différent pour votre programme.
    
    L'exécution s'est arrêtée à la ligne 329 du fichier TESTS:\runtime\test_attribute_error.py
    
       327:     stdlib_modules.names.append("my_turtle1")
       328:     try:
    -->329:        import my_turtle1
       330:     except AttributeError as e:

    Exception levée à la ligne 4 du fichier TESTS:\my_turtle1.py.
    
       2: import my_turtle1
       3: 
    -->4: a = my_turtle1.something
              ^^^^^^^^^^^^^^^^^^^^

            my_turtle1:  <module my_turtle1> from TESTS:\my_turtle1.py
        


Circular import b
~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 346, in test_Circular_import_b
        import circular_c
      File "TESTS:\circular_c.py", line 4, in <module>
        a = circular_c.something
    AttributeError: partially initialized module 'circular_c' has no attribute 'something' (most likely due to a circular import)
    
        Vous avez une importation circulaire.
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    Python a indiqué que le module `{module}` n'était pas complètement importé.
    Cela peut se produire si, pendant l'exécution du code du module `circular_c`
    une tentative est faite d'importer à nouveau le même module.
    
    L'exécution s'est arrêtée à la ligne 346 du fichier TESTS:\runtime\test_attribute_error.py
    
       344: def test_Circular_import_b():
       345:     try:
    -->346:         import circular_c
       347:     except AttributeError as e:

    Exception levée à la ligne 4 du fichier TESTS:\circular_c.py.
    
       2: import circular_c
       3: 
    -->4: a = circular_c.something
              ^^^^^^^^^^^^^^^^^^^^

            circular_c:  <module circular_c> from TESTS:\circular_c.py
        


Generic
~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 24, in test_Generic
        A.x  # testing type
    AttributeError: type object 'A' has no attribute 'x'
    
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    L’objet `A` n’a pas d’attribut nommé `x`.
    
    Exception levée à la ligne 24 du fichier TESTS:\runtime\test_attribute_error.py.
    
       22: 
       23:     try:
    -->24:         A.x  # testing type
       25:     except AttributeError as e:

            A:  <class A> from test_attribute_error.test_Generic
        


Generic different frame
~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 47, in test_Generic_different_frame
        a.attr
    AttributeError: 'A' object has no attribute 'attr'
    
        Vouliez-vous dire `attr2` ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    L’objet `a` n’a pas d’attribut nommé `attr`.
    Peut-être que vous vouliez plutôt écrire : `a.attr2` au lieu de `a.attr`.
    
    Exception levée à la ligne 47 du fichier TESTS:\runtime\test_attribute_error.py.
    
       45:     a = f()
       46:     try:
    -->47:         a.attr
       48:     except AttributeError as e:

            a:  <f.A object> from test_attribute_error.test_Generic_different_frame
        


Generic instance
~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 65, in test_Generic_instance
        a.x
    AttributeError: 'A' object has no attribute 'x'
    
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    L’objet `a` n’a pas d’attribut nommé `x`.
    
    Exception levée à la ligne 65 du fichier TESTS:\runtime\test_attribute_error.py.
    
       63:     a = A()
       64:     try:
    -->65:         a.x
       66:     except AttributeError as e:

            a:  <A object> from test_attribute_error.test_Generic_instance
        


Module attribute typo
~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 142, in test_Module_attribute_typo
        math.cost
    AttributeError: module 'math' has no attribute 'cost'
    
        Vouliez-vous dire `cos` ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    Au lieu d’écrire `math.cost`, peut-être que vous vouliez écrire
    l'un des attributs suivants du module `math` :
    cos, cosh, acos
    
    Exception levée à la ligne 142 du fichier TESTS:\runtime\test_attribute_error.py.
    
       140: 
       141:     try:
    -->142:         math.cost
       143:     except AttributeError as e:

            math:  <module math (builtin)>
        


Nonetype
~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 181, in test_Nonetype
        a.b
    AttributeError: 'NoneType' object has no attribute 'b'
    
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    Vous tentez d’accéder à l’attribut `b`
    pour une variable dont la valeur est `None`.
    Exception levée à la ligne 181 du fichier TESTS:\runtime\test_attribute_error.py.
    
       179:     a = None
       180:     try:
    -->181:         a.b
       182:     except AttributeError as e:

            a:  None
        


Object attribute typo
~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 81, in test_Object_attribute_typo
        a.appendh(4)
    AttributeError: 'list' object has no attribute 'appendh'
    
        Vouliez-vous dire `append` ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    L’objet `a` n’a pas d’attribut nommé `appendh`.
    Peut-être que vous vouliez plutôt écrire : `a.append` au lieu de `a.appendh`.
    
    Exception levée à la ligne 81 du fichier TESTS:\runtime\test_attribute_error.py.
    
       79:     try:
       80:         a = [1, 2, 3]
    -->81:         a.appendh(4)
                   ^^^^^^^^^
       82:     except AttributeError as e:

            a:  [1, 2, 3]
        


Perhaps comma
~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 200, in test_Perhaps_comma
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
    
    Exception levée à la ligne 200 du fichier TESTS:\runtime\test_attribute_error.py.
    
       198:     # fmt: off
       199:     try:
    -->200:         a = [abcd
       201:         .defg]

            abcd:  'hello'
            defg:  'world'
        


Shadow stdlib module
~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 163, in test_Shadow_stdlib_module
        turtle.Pen
    AttributeError: module 'turtle' has no attribute 'Pen'
    
        Avez-vous donné à votre programme le même nom qu’un module Python ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    Vous avez importé un module nommé `turtle` de `TESTS:\turtle.py`.
    Il y a aussi un module nommé `turtle` dans la bibliothèque standard de Python.
    Peut-être avez-vous besoin de renommer votre module.
    
    Exception levée à la ligne 163 du fichier TESTS:\runtime\test_attribute_error.py.
    
       161: 
       162:     try:
    -->163:         turtle.Pen
       164:     except AttributeError as e:

            turtle:  <module turtle> from TESTS:\turtle.py
        


Tuple by accident
~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 269, in test_Tuple_by_accident
        something.upper()
    AttributeError: 'tuple' object has no attribute 'upper'
    
        Avez-vous écrit une virgule par erreur ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    `something` est un tuple qui contient un seul élément
    ayant `upper` comme attribut.
    Peut-être avez-vous ajouté une virgule par erreur à la fin de la ligne
    lorsque vous avez défini `something`.
    
    Exception levée à la ligne 269 du fichier TESTS:\runtime\test_attribute_error.py.
    
       267:     something = "abc",  # note trailing comma
       268:     try:
    -->269:         something.upper()
                    ^^^^^^^^^^^^^^^
       270:     except AttributeError as e:

            something:  ('abc',)
        


Use builtin
~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 97, in test_Use_builtin
        a.length()
    AttributeError: 'list' object has no attribute 'length'
    
        Vouliez-vous utiliser `len(a)` ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    L’objet `a` n’a pas d’attribut nommé `length`.
    Peut-être pouvez-vous utiliser la fonction Python builtin `len` à la place:
    `len(a)`.
    Exception levée à la ligne 97 du fichier TESTS:\runtime\test_attribute_error.py.
    
       95:     try:
       96:         a = [1, 2, 3]
    -->97:         a.length()
                   ^^^^^^^^
       98:     except AttributeError as e:

            a:  [1, 2, 3]
        


Use join with str
~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 313, in test_Use_join_with_str
        a = ['a', '2'].join('abc') + ['b', '3'].join('\n')
    AttributeError: 'list' object has no attribute 'join'
    
        Voulez-vous dire `'abc'.join(['a', '2'])` ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    L’objet `['a', '2']` n’a pas d’attribut nommé `join`.
    Vous vouliez peut-être plutôt écrire quelque chose comme `'...'.join(['a', '2'])`.
    
    Exception levée à la ligne 313 du fichier TESTS:\runtime\test_attribute_error.py.
    
       311: def test_Use_join_with_str():
       312:     try:
    -->313:         a = ['a', '2'].join('abc') + ['b', '3'].join('\n')
                        ^^^^^^^^^^^^^^^
       314:     except AttributeError as e:


Use synonym
~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 113, in test_Use_synonym
        a.add(4)
    AttributeError: 'list' object has no attribute 'add'
    
        Vouliez-vous dire `append` ?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    L’objet `a` n’a pas d’attribut nommé `add`.
    Toutefois, `a` a les attributs suivants avec des sens similaires:
    'append, extend, insert'.
    
    Exception levée à la ligne 113 du fichier TESTS:\runtime\test_attribute_error.py.
    
       111:     try:
       112:         a = [1, 2, 3]
    -->113:         a.add(4)
                    ^^^^^
       114:     except AttributeError as e:

            a:  [1, 2, 3]
        


Using slots
~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 254, in test_Using_slots
        f.b = 1
    AttributeError: 'F' object has no attribute 'b'
    
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    L’objet `f` n’a pas d’attribut nommé `b`.
    Notez que l’objet `f` utilise `__slots__` qui empêche
    la création de nouveaux attributs.
    Voici quelques-uns de ses attributs connus :
    `a`.
    Exception levée à la ligne 254 du fichier TESTS:\runtime\test_attribute_error.py.
    
       252:     f = F()
       253:     try:
    -->254:         f.b = 1
       255:     except AttributeError as e:

            f:  <F object> from test_attribute_error.test_Using_slots
        


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
       7:     except FileNotFoundError as e:

            open:  <builtin function open>
        


ImportError
-----------


Circular import
~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_import_error.py", line 58, in test_Circular_import
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
    
    L'exécution s'est arrêtée à la ligne 58 du fichier TESTS:\runtime\test_import_error.py
    
       56: def test_Circular_import():
       57:     try:
    -->58:         import circular_a
       59:     except ImportError as e:

    Exception levée à la ligne 2 du fichier TESTS:\circular_b.py.
    
       1: """File used in for test_circular_import() in test_import_error.py"""
    -->2: from circular_a import a


Simple import error
~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_import_error.py", line 44, in test_Simple_import_error
        from math import Pi
    ImportError: cannot import name 'Pi' from 'math' (unknown location)
    
        Vouliez-vous dire `pi` ?
        
    L'exception `ImportError` indique qu’un certain objet n’a pas pu
    être importé à partir d’un module ou d’un paquet. Très souvent, c’est
    parce que le nom de l’objet n’est pas écrit correctement.
    
    Peut-être que vous vouliez importer `pi` (de `math`) au lieu de `Pi`.
    
    Exception levée à la ligne 44 du fichier TESTS:\runtime\test_import_error.py.
    
       42: 
       43:     try:
    -->44:         from math import Pi
       45:     except ImportError as e:


IndexError
----------


Empty
~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_index_error.py", line 38, in test_Empty
        c = a[1]
    IndexError: list index out of range
    
        `a` ne contient aucun élément.
        
    Une exception `IndexError` se produit lorsque vous essayez d’obtenir un élément
    d'une liste, d'un tuple, ou d'un objet similaire (séquence), à l’aide d’un indice qui
    n’existe pas; typiquement, c’est parce que l’indice que vous donnez
    est plus grand que la longueur de la séquence.
    
    Vous avez essayé d’obtenir l’élément avec l’indice `1` de `a`,
    une liste (`list`) qui ne contient aucun élément.
    
    Exception levée à la ligne 38 du fichier TESTS:\runtime\test_index_error.py.
    
       36:     a = []
       37:     try:
    -->38:         c = a[1]
                       ^^^^
       39:     except IndexError as e:

            a:  []
        


Long list
~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_index_error.py", line 24, in test_Long_list
        print(a[60], b[0])
    IndexError: list index out of range
    
    Une exception `IndexError` se produit lorsque vous essayez d’obtenir un élément
    d'une liste, d'un tuple, ou d'un objet similaire (séquence), à l’aide d’un indice qui
    n’existe pas; typiquement, c’est parce que l’indice que vous donnez
    est plus grand que la longueur de la séquence.
    
    Vous avez essayé d’obtenir l’élément avec l’indice `60` de `a`,
    une liste (`list`) de longueur `40`.
    Les indices valides de `a` sont les entiers allant de `-40` à `39`.
    
    Exception levée à la ligne 24 du fichier TESTS:\runtime\test_index_error.py.
    
       22:     b = tuple(range(50))
       23:     try:
    -->24:         print(a[60], b[0])
                         ^^^^^
       25:     except IndexError as e:

            a:  [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, ...]
                len(a): 40
        
        


Short tuple
~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_index_error.py", line 8, in test_Short_tuple
        print(a[3], b[2])
    IndexError: tuple index out of range
    
        N’oubliez pas : le premier élément d'un objet de type `un `tuple`` est à l’indice 0
        et non pas à l'indice 1.
        
    Une exception `IndexError` se produit lorsque vous essayez d’obtenir un élément
    d'une liste, d'un tuple, ou d'un objet similaire (séquence), à l’aide d’un indice qui
    n’existe pas; typiquement, c’est parce que l’indice que vous donnez
    est plus grand que la longueur de la séquence.
    
    Vous avez essayé d’obtenir l’élément avec l’indice `3` de `a`,
    un `tuple` de longueur `3`.
    Les indices valides de `a` sont les entiers allant de `-3` à `2`.
    
    Exception levée à la ligne 8 du fichier TESTS:\runtime\test_index_error.py.
    
        6:     b = [1, 2, 3]
        7:     try:
    --> 8:         print(a[3], b[2])
                         ^^^^
        9:     except IndexError as e:

            a:  (1, 2, 3)
        


KeyError
--------


ChainMap
~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "PYTHON_LIB:\collections\__init__.py", line 965, in pop
        return self.maps[0].pop(key, *args)
    KeyError: 42
    
        During handling of the above exception, another exception occurred:
    
    Traceback (most recent call last):
      File "TESTS:\runtime\test_key_error.py", line 62, in test_ChainMap
        d.pop(42)
      File "PYTHON_LIB:\collections\__init__.py", line 967, in pop
        raise KeyError('Key not found in the first mapping: {!r}'.format(key))
    KeyError: 'Key not found in the first mapping: 42'
    
    Une `KeyError` est levée lorsqu'une valeur n'est pas trouvée en tant que
    clé dans un dict Python ou dans un objet similaire.
    
    La clé `42` est introuvable dans `d`, un objet de type `ChainMap`.
    
    L'exécution s'est arrêtée à la ligne 62 du fichier TESTS:\runtime\test_key_error.py
    
       60:     d = ChainMap({}, {})
       61:     try:
    -->62:         d.pop(42)
       63:     except KeyError as e:

            d:  ChainMap({}, {})
            d.pop:  <bound method ChainMap.pop of ChainMap({}, {})>
        
    Exception levée à la ligne 967 du fichier PYTHON_LIB:\collections\__init__.py.
    
       965:             return self.maps[0].pop(key, *args)
       966:         except KeyError:
    -->967:             raise KeyError('Key not found in the first mapping: {!r}'.format(key))

            key:  42
            KeyError:  <class KeyError>
            format:  <builtin function format>
            'Key not found in the first mapping: {!r}'.format:  <builtin method format of str object>
        


Forgot to convert to string
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_key_error.py", line 115, in test_Forgot_to_convert_to_string
        print(squares[2])
    KeyError: 2
    
        Avez-vous oublié de convertir `2` en une chaîne ?
        
    Une `KeyError` est levée lorsqu'une valeur n'est pas trouvée en tant que
    clé dans un dict Python ou dans un objet similaire.
    
    La clé `2` est introuvable dans le dict `squares`.
    `squares` contient une clé identique à `str(2)`.
    Peut-être avez-vous oublié de convertir la clé en une chaîne.
    
    Exception levée à la ligne 115 du fichier TESTS:\runtime\test_key_error.py.
    
       113:     squares = {"1": 1, "2": 4, "3": 9}
       114:     try:
    -->115:         print(squares[2])
                          ^^^^^^^^^^
       116:     except KeyError as e:

            squares:  {'1': 1, '2': 4, '3': 9}
        


Generic key error
~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_key_error.py", line 44, in test_Generic_key_error
        d["c"]
    KeyError: 'c'
    
    Une `KeyError` est levée lorsqu'une valeur n'est pas trouvée en tant que
    clé dans un dict Python ou dans un objet similaire.
    
    La clé `'c'` est introuvable dans le dict `d`.
    
    Exception levée à la ligne 44 du fichier TESTS:\runtime\test_key_error.py.
    
       42:     d = {"a": 1, "b": 2}
       43:     try:
    -->44:         d["c"]
       45:     except KeyError as e:

            d:  {'a': 1, 'b': 2}
        


Popitem empty ChainMap
~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "PYTHON_LIB:\collections\__init__.py", line 958, in popitem
        return self.maps[0].popitem()
    KeyError: 'popitem(): dictionary is empty'
    
        During handling of the above exception, another exception occurred:
    
    Traceback (most recent call last):
      File "TESTS:\runtime\test_key_error.py", line 26, in test_Popitem_empty_ChainMap
        alpha.popitem()
      File "PYTHON_LIB:\collections\__init__.py", line 960, in popitem
        raise KeyError('No keys found in the first mapping.')
    KeyError: 'No keys found in the first mapping.'
    
        `alpha` est une `ChainMap` vide.
        
    Une `KeyError` est levée lorsqu'une valeur n'est pas trouvée en tant que
    clé dans un dict Python ou dans un objet similaire.
    
    Vous avez essayé de récupérer un élément de `alpha` qui est une `ChainMap` vide.
    
    L'exécution s'est arrêtée à la ligne 26 du fichier TESTS:\runtime\test_key_error.py
    
       24:     alpha = ChainMap({}, {})
       25:     try:
    -->26:         alpha.popitem()
       27:     except KeyError as e:

            alpha:  ChainMap({}, {})
            alpha.popitem:  <bound method ChainMap.popitem of ChainMap({}, {})>
        
    Exception levée à la ligne 960 du fichier PYTHON_LIB:\collections\__init__.py.
    
       958:             return self.maps[0].popitem()
       959:         except KeyError:
    -->960:             raise KeyError('No keys found in the first mapping.')

            KeyError:  <class KeyError>
        


Popitem empty dict
~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_key_error.py", line 8, in test_Popitem_empty_dict
        d.popitem()
    KeyError: 'popitem(): dictionary is empty'
    
        `d` est un `dict` vide.
        
    Une `KeyError` est levée lorsqu'une valeur n'est pas trouvée en tant que
    clé dans un dict Python ou dans un objet similaire.
    
    Vous avez essayé de récupérer un élément de `d` qui est un `dict` vide.
    
    Exception levée à la ligne 8 du fichier TESTS:\runtime\test_key_error.py.
    
        6:     d = {}
        7:     try:
    --> 8:         d.popitem()
        9:     except KeyError as e:

            d:  {}
            d.popitem:  <builtin method popitem of dict object>
        


Similar names
~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_key_error.py", line 145, in test_Similar_names
        a = second["alpha"]
    KeyError: 'alpha'
    
        Vouliez-vous dire `'alpha0'` ?
        
    Une `KeyError` est levée lorsqu'une valeur n'est pas trouvée en tant que
    clé dans un dict Python ou dans un objet similaire.
    
    La clé `'alpha'` est introuvable dans le dict `second`.
    `second` a quelques clés similaires à `'alpha'` dont :
    `'alpha0', 'alpha12', 'alpha11'`.
    
    Exception levée à la ligne 145 du fichier TESTS:\runtime\test_key_error.py.
    
       143:     second = {"alpha0": 1, "alpha11": 2, "alpha12": 3}
       144:     try:
    -->145:         a = second["alpha"]
                        ^^^^^^^^^^^^^^^
       146:     except KeyError as e:

            second:  {'alpha0': 1, 'alpha11': 2, 'alpha12': 3}
        


String by mistake
~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_key_error.py", line 98, in test_String_by_mistake
        d["(0, 0)"]
    KeyError: '(0, 0)'
    
        Avez-vous converti `(0, 0)` en une chaîne par erreur ?
        
    Une `KeyError` est levée lorsqu'une valeur n'est pas trouvée en tant que
    clé dans un dict Python ou dans un objet similaire.
    
    La clé `'(0, 0)'` est introuvable dans le dict `d`.
    `'(0, 0)'` est une chaîne de caractères.
    Il y a une clé de `d` dont la représentation en une chaîne
    est identique à `'(0, 0)'`.
    
    Exception levée à la ligne 98 du fichier TESTS:\runtime\test_key_error.py.
    
        96:     d = {(0, 0): "origin"}
        97:     try:
    --> 98:         d["(0, 0)"]
        99:     except KeyError as e:

            d:  {(0, 0): 'origin'}
        


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
    lorsqu’une clé ou un indice utilisé sur un tableau de correspondance ou une séquence est invalide.
    Elle peut également être levée directement par codecs.lookup().
    
    Exception levée à la ligne 10 du fichier TESTS:\runtime\test_lookup_error.py.
    
        8:         # other than possibly codecs.lookup(), which is why we raise
        9:         # it directly here for our example.
    -->10:         raise LookupError("Fake message")
       11:     except LookupError as e:

            LookupError:  <class LookupError>
        


ModuleNotFoundError
-------------------


Need to install module
~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_module_not_found_error.py", line 76, in test_Need_to_install_module
        import alphabet
    ModuleNotFoundError: No module named 'alphabet'
    
    Une exception `ModuleNotFoundError` indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe en
    écrivant le nom du module, ou parce qu’il n’est pas installé sur votre ordinateur.
    
    Aucun module nommé `alphabet` ne peut être importé.
    Vous devez peut-être l'installer.
    
    Exception levée à la ligne 76 du fichier TESTS:\runtime\test_module_not_found_error.py.
    
       74: def test_Need_to_install_module():
       75:     try:
    -->76:         import alphabet
       77:     except ModuleNotFoundError as e:


Not a package
~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_module_not_found_error.py", line 22, in test_Not_a_package
        import os.xxx
    ModuleNotFoundError: No module named 'os.xxx'; 'os' is not a package
    
    Une exception `ModuleNotFoundError` indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe en
    écrivant le nom du module, ou parce qu’il n’est pas installé sur votre ordinateur.
    
    `xxx` ne peut pas être importé de `os`.
    
    
    Exception levée à la ligne 22 du fichier TESTS:\runtime\test_module_not_found_error.py.
    
       20: 
       21:     try:
    -->22:         import os.xxx
       23:     except ModuleNotFoundError as e:


Not a package similar name
~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_module_not_found_error.py", line 36, in test_Not_a_package_similar_name
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
    
    Exception levée à la ligne 36 du fichier TESTS:\runtime\test_module_not_found_error.py.
    
       34: def test_Not_a_package_similar_name():
       35:     try:
    -->36:         import os.pathh
       37:     except ModuleNotFoundError as e:


Object not module
~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_module_not_found_error.py", line 49, in test_Object_not_module
        import os.open
    ModuleNotFoundError: No module named 'os.open'; 'os' is not a package
    
        Vouliez-vous dire `from os import open` ?
        
    Une exception `ModuleNotFoundError` indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe en
    écrivant le nom du module, ou parce qu’il n’est pas installé sur votre ordinateur.
    
    `open` n’est pas un module distinct, mais un objet qui fait partie de `os`.
    
    Exception levée à la ligne 49 du fichier TESTS:\runtime\test_module_not_found_error.py.
    
       47: def test_Object_not_module():
       48:     try:
    -->49:         import os.open
       50:     except ModuleNotFoundError as e:

            open:  <builtin function open>
        


Similar object not module
~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_module_not_found_error.py", line 62, in test_Similar_object_not_module
        import os.opend
    ModuleNotFoundError: No module named 'os.opend'; 'os' is not a package
    
        Vouliez-vous dire `from os import open` ?
        
    Une exception `ModuleNotFoundError` indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe en
    écrivant le nom du module, ou parce qu’il n’est pas installé sur votre ordinateur.
    
    Peut-être vouliez-vous dire `from os import open`.
    `open` est un nom similaire à `opend` et est un objet qui
    peut être importé de `os`.
    D’autres objets avec des noms similaires qui font partie de
    `os` comprennent `popen, fdopen`.
    
    Exception levée à la ligne 62 du fichier TESTS:\runtime\test_module_not_found_error.py.
    
       60: def test_Similar_object_not_module():
       61:     try:
    -->62:         import os.opend
       63:     except ModuleNotFoundError as e:


Standard library module
~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_module_not_found_error.py", line 7, in test_Standard_library_module
        import Tkinter
    ModuleNotFoundError: No module named 'Tkinter'
    
        Vouliez-vous dire `tkinter` ?
        
    Une exception `ModuleNotFoundError` indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe en
    écrivant le nom du module, ou parce qu’il n’est pas installé sur votre ordinateur.
    
    Aucun module nommé `Tkinter` ne peut être importé.
    Vous devez peut-être l'installer.
    `tkinter` est un module existant qui a un nom similaire.
    
    Exception levée à la ligne 7 du fichier TESTS:\runtime\test_module_not_found_error.py.
    
       5: def test_Standard_library_module():
       6:     try:
    -->7:         import Tkinter
       8:     except ModuleNotFoundError as e:


no curses
~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_module_not_found_error.py", line 92, in test_no_curses
        import curses
      File "PYTHON_LIB:\curses\__init__.py", line 13, in <module>
        from _curses import *
    ModuleNotFoundError: No module named '_curses'
    
        Le module curses est rarement installé avec Python sur Windows.
        
    Une exception `ModuleNotFoundError` indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe en
    écrivant le nom du module, ou parce qu’il n’est pas installé sur votre ordinateur.
    
    Vous avez essayé d’importer le module curses.
    Le module curses est rarement installé avec Python sur Windows.
    
    L'exécution s'est arrêtée à la ligne 92 du fichier TESTS:\runtime\test_module_not_found_error.py
    
       90:     def test_no_curses():
       91:         try:
    -->92:             import curses
       93:         except ModuleNotFoundError as e:

    Exception levée à la ligne 13 du fichier PYTHON_LIB:\curses\__init__.py.
    
       11: """
       12: 
    -->13: from _curses import *
       14: import os as _os


NameError
---------


Annotated variable
~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 24, in test_Annotated_variable
        y = x
    NameError: name 'x' is not defined
    
        Avez-vous utilisé deux points au lieu d’un signe égal ?
        
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
    Dans votre programme, aucun objet portant le nom `x` n'existe.
    Une annotation de type a été trouvée pour `x` dans la portée 'global'
    Peut-être que vous aviez utilisé deux points au lieu d’un signe égal et écrit
    
        x : 3
    
    au lieu de
    
        x = 3
    
    Exception levée à la ligne 24 du fichier TESTS:\runtime\test_name_error.py.
    
       22: def test_Annotated_variable():
       23:     try:
    -->24:         y = x
                       ^
       25:     except NameError as e:


Custom name
~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 163, in test_Custom_name
        python
    NameError: name 'python' is not defined
    
        Vous utilisez déjà Python!
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
    Vous utilisez déjà Python!
    Exception levée à la ligne 163 du fichier TESTS:\runtime\test_name_error.py.
    
       161: def test_Custom_name():
       162:     try:
    -->163:         python
                    ^^^^^^
       164:     except NameError as e:


Free variable referenced
~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 149, in test_Free_variable_referenced
        outer()
      File "TESTS:\runtime\test_name_error.py", line 145, in outer
        inner()
      File "TESTS:\runtime\test_name_error.py", line 144, in inner
        return var
    NameError: free variable 'var' referenced before assignment in enclosing scope
    
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
    Dans votre programme, `var` est un nom inconnu
    qui existe dans une portée englobante,
    mais qui n'a pas encore reçu de valeur.
    
    L'exécution s'est arrêtée à la ligne 149 du fichier TESTS:\runtime\test_name_error.py
    
       147: 
       148:     try:
    -->149:         outer()
       150:     except NameError as e:

            outer:  <function outer> from test_Free_variable_referenced
        
    Exception levée à la ligne 144 du fichier TESTS:\runtime\test_name_error.py.
    
       142:     def outer():
       143:         def inner():
    -->144:             return var
                               ^^^
       145:         inner()


Generic
~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 9, in test_Generic
        this = something
    NameError: name 'something' is not defined
    
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
    Dans votre programme, aucun objet portant le nom `something` n'existe.
    Je n’ai pas d’informations supplémentaires pour vous.
    
    Exception levée à la ligne 9 du fichier TESTS:\runtime\test_name_error.py.
    
        7: def test_Generic():
        8:     try:
    --> 9:         this = something
                          ^^^^^^^^^
       10:     except NameError as e:


Missing import
~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 129, in test_Missing_import
        unicodedata.something
    NameError: name 'unicodedata' is not defined
    
        Avez-vous oublié d’importer `unicodedata` ?
        
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
    Le nom `unicodedata` n’est pas défini dans votre programme.
    Peut-être avez-vous oublié d’importer `unicodedata` qui se trouve
    dans la bibliothèque standard de Python.
    
    Exception levée à la ligne 129 du fichier TESTS:\runtime\test_name_error.py.
    
       127: 
       128:     try:
    -->129:         unicodedata.something
                    ^^^^^^^^^^^
       130:     except NameError as e:


Synonym
~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 89, in test_Synonym
        cost  # wrote from math import * above
    NameError: name 'cost' is not defined
    
        Vouliez-vous dire `cos` ?
        
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
    Dans votre programme, aucun objet portant le nom `cost` n'existe.
    Au lieu d’écrire `cost`, peut-être que vous vouliez écrire l'un des noms suivants :
    *    Portée globale : `cos`, `cosh`, `acos`
    
    Exception levée à la ligne 89 du fichier TESTS:\runtime\test_name_error.py.
    
       87: 
       88:     try:
    -->89:         cost  # wrote from math import * above
                   ^^^^
       90:     except NameError as e:


OsError
-------


Urllib error
~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "PYTHON_LIB:\urllib\request.py", line 1354, in do_open
           ... Plus de lignes non affichées. ...
      File "PYTHON_LIB:\socket.py", line 787, in create_connection
        for res in getaddrinfo(host, port, 0, SOCK_STREAM):
      File "PYTHON_LIB:\socket.py", line 918, in getaddrinfo
        for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
    socket.gaierror: [Errno 11001] getaddrinfo failed
    
        During handling of the above exception, another exception occurred:
    
    Traceback (most recent call last):
      File "TESTS:\runtime\test_os_error.py", line 7, in test_Urllib_error
        request.urlopen("http://does_not_exist")
           ... Plus de lignes non affichées. ...
      File "PYTHON_LIB:\urllib\request.py", line 1383, in http_open
        return self.do_open(http.client.HTTPConnection, req)
      File "PYTHON_LIB:\urllib\request.py", line 1357, in do_open
        raise URLError(err)
    URLError: <urlopen error [Errno 11001] getaddrinfo failed>
    
    Une exception de type `URLError` est une sous-classe de `OSError`.
    Une exception `OSError` est généralement levée par le système d’exploitation
    pour indiquer qu’une opération n’est pas autorisée ou
    qu'une ressource n’est pas disponible.
    
    Je soupçonne que vous essayez de vous connecter à un serveur et
    qu’une connexion ne peut être faite.
    
    Si c’est le cas, vérifiez les fautes de frappe dans l’URL
    et vérifiez votre connectivité Internet.
    
    L'exécution s'est arrêtée à la ligne 7 du fichier TESTS:\runtime\test_os_error.py
    
       5:     from urllib import request, error
       6:     try:
    -->7:         request.urlopen("http://does_not_exist")
       8:     except error.URLError as e:

            request:  <module urllib.request> from PYTHON_LIB:\urllib\request.py
            request.urlopen:  <function urlopen>
        
    Exception levée à la ligne 1357 du fichier PYTHON_LIB:\urllib\request.py.
    
       1355:                           encode_chunked=req.has_header('Transfer-encoding'))
       1356:             except OSError as err: # timeout error
    -->1357:                 raise URLError(err)
       1358:             r = h.getresponse()

            global URLError:  <class urllib.error.URLError>
        


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
       7:     except OverflowError as e:


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
        9:     except RecursionError as e:

            a:  <function a> from test_Generic
        
    Exception levée à la ligne 6 du fichier TESTS:\runtime\test_recursion_error.py.
    
       4: def test_Generic():
       5:     def a():
    -->6:         return a()
                         ^^^
       7:     try:

            a:  <function a> from test_Generic
        


TypeError
---------


Bad type for unary operator
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 371, in test_Bad_type_for_unary_operator
        a =+ "def"
    TypeError: bad operand type for unary +: 'str'
    
        Peut-être que vous vouliez plutôt écrire `+=` au lieu de `=+`
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Vous avez essayé d’utiliser l’opérateur unaire '+'
    avec le type d’objet suivant: une chaîne de caractères (`str`).
    Cette opération n’est pas définie pour ce type d’objet.
    
    Peut-être que vous vouliez plutôt écrire `+=` au lieu de `=+`
    
    Exception levée à la ligne 371 du fichier TESTS:\runtime\test_type_error.py.
    
       369:         # fmt: off
       370:         a = "abc"
    -->371:         a =+ "def"
                       ^^^^^^^
       372:         # fmt: on


Builtin has no len
~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 780, in test_Builtin_has_no_len
        len("Hello world".split)
    TypeError: object of type 'builtin_function_or_method' has no len()
    
        Avez-vous oublié d’invoquer `"Hello world".split` ?
        
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Je soupçonne que vous avez oublié d’ajouter des parenthèses pour invoquer `"Hello world".split`.
    Vous avez peut-être voulu écrire :
    `len("Hello world".split())`
    
    Exception levée à la ligne 780 du fichier TESTS:\runtime\test_type_error.py.
    
       778: def test_Builtin_has_no_len():
       779:     try:
    -->780:         len("Hello world".split)
       781:     except TypeError as e:

            len:  <builtin function len>
            "Hello world".split:  <builtin method split of str object>
        


Can only concatenate
~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 37, in test_Can_only_concatenate
        result = a_tuple + a_list
    TypeError: can only concatenate tuple (not "list") to tuple
    
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Vous avez essayé de concaténer (additionner) deux types d’objets différents:
    un `tuple` et une liste (`list`).
    
    Exception levée à la ligne 37 du fichier TESTS:\runtime\test_type_error.py.
    
       35:         a_tuple = (1, 2, 3)
       36:         a_list = [1, 2, 3]
    -->37:         result = a_tuple + a_list
                            ^^^^^^^^^^^^^^^^
       38:     except TypeError as e:

            a_list:  [1, 2, 3]
            a_tuple:  (1, 2, 3)
        


Cannot convert dictionary update sequence
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 766, in test_Cannot_convert_dictionary_update_sequence
        dd.update([1, 2, 3])
    TypeError: cannot convert dictionary update sequence element #0 to a sequence
    
        Peut-être que vous vouliez plutôt utiliser la méthode `dict.fromkeys()`.
        
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    `dict.update()` n’accepte pas une séquence comme argument.
    Au lieu d’écrire `dd.update([1, 2, 3])`
    peut-être devriez-vous utiliser la méthode `dict.fromkeys()` : `dd.update( dict.fromkeys([1, 2, 3]) )`.
    
    Exception levée à la ligne 766 du fichier TESTS:\runtime\test_type_error.py.
    
       764:     dd = {"a": "a"}
       765:     try:
    -->766:         dd.update([1, 2, 3])
       767:     except TypeError as e:

            dd:  {'a': 'a'}
            dd.update:  <builtin method update of dict object>
        


Cannot multiply by non int
~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 570, in test_Cannot_multiply_by_non_int
        "a" * "2"
    TypeError: can't multiply sequence by non-int of type 'str'
    
        Avez-vous oublié de convertir `"2"` en un entier ?
        
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Vous ne pouvez multiplier les séquences, telles que
    les listes, les tuples, les chaînes, etc., que par des entiers.
    Peut-être avez-vous oublié de convertir `"2"` en un entier.
    
    Exception levée à la ligne 570 du fichier TESTS:\runtime\test_type_error.py.
    
       568: 
       569:     try:
    -->570:         "a" * "2"
       571:     except TypeError as e:


Cannot unpack non iterable object
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 738, in test_Cannot_unpack_non_iterable_object
        a, b = 42.0
    TypeError: cannot unpack non-iterable float object
    
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Le dépaquetage ('unpack') est un moyen pratique d’attribuer un nom
    à chaque élément d’un itérable.
    Un itérable est un objet capable de renvoyer ses membres un à la fois.
    Les contenants python (`list, tuple, dict`, etc.) sont itérables,
    mais pas les objets de type `float`.
    
    Exception levée à la ligne 738 du fichier TESTS:\runtime\test_type_error.py.
    
       736: def test_Cannot_unpack_non_iterable_object():
       737:     try:
    -->738:         a, b = 42.0
       739:     except TypeError as e:


Comparison not supported
~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 320, in test_Comparison_not_supported
        b >= a
    TypeError: '>=' not supported between instances of 'int' and 'str'
    
        Avez-vous oublié de convertir `a` en un entier (`int`) ?
        
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    En utilisant >=, vous avez tenté de comparer
    deux types d’objets incompatibles:
    un entier (`int`) et une chaîne de caractères (`str`).
    Peut-être avez-vous oublié de convertir `a` en un entier (`int`).
    
    Exception levée à la ligne 320 du fichier TESTS:\runtime\test_type_error.py.
    
       318:         a = "2"
       319:         b = 42
    -->320:         b >= a
       321:     except TypeError as e:

            a:  '2'
            b:  42
        


Derive from BaseException
~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 513, in test_Derive_from_BaseException
        raise "exception"  # noqa
    TypeError: exceptions must derive from BaseException
    
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Dans Python 3, les exceptions doivent être dérivées de BaseException.
    
    Exception levée à la ligne 513 du fichier TESTS:\runtime\test_type_error.py.
    
       511: def test_Derive_from_BaseException():
       512:     try:
    -->513:         raise "exception"  # noqa
       514:     except TypeError as e:


Indices must be integers or slices
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 652, in test_Indices_must_be_integers_or_slices
        [1, 2, 3]["2"]
    TypeError: list indices must be integers or slices, not str
    
        Avez-vous oublié de convertir `"2"` en un entier ?
        
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Dans l’expression `[1, 2, 3]["2"]`
    ce qui est inclus entre les crochets, `[...]`,
    doit être soit un entier ou une tranche
    (`start:stop` ou `start:stop:step`) 
    et vous l’avez utilisé une chaîne de caractères (`str`) la place.
    
    Peut-être avez-vous oublié de convertir `"2"` en un entier.
    
    Exception levée à la ligne 652 du fichier TESTS:\runtime\test_type_error.py.
    
       650: 
       651:     try:
    -->652:         [1, 2, 3]["2"]
       653:     except TypeError as e:


Not an integer
~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 615, in test_Not_an_integer
        range(c, d)
    TypeError: 'str' object cannot be interpreted as an integer
    
        Avez-vous oublié de convertir `c, d` en entiers ?
        
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Vous avez écrit un objet de type `str` là où un entier était attendu.
    Peut-être avez-vous oublié de convertir `c, d` en entiers.
    Exception levée à la ligne 615 du fichier TESTS:\runtime\test_type_error.py.
    
       613:     c, d = "2", "3"
       614:     try:
    -->615:         range(c, d)
       616:     except TypeError as e:

            c:  '2'
            d:  '3'
            range:  <class range>
        


Not callable
~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 500, in test_Not_callable
        _ = [1, 2](a + b)
    TypeError: 'list' object is not callable
    
        Vouliez-vous dire `[1, 2][a + b]` ?
        
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    En raison des parenthees, `(a + b)` est interprété par Python
    comme indiquant une invocation de fonction pour 
    `[1, 2]`, qui est un objet de type `list`
    ne pouvant pas être invoqué.
    
    Cependant, `[1, 2]` est une séquence.
    Peut-être que vous vouliez utiliser `[]` au lieu de `()` et écrire
    `[1, 2][a + b]`
    
    Exception levée à la ligne 500 du fichier TESTS:\runtime\test_type_error.py.
    
       498:     try:
       499:         a, b = 3, 7
    -->500:         _ = [1, 2](a + b)
                        ^^^^^^^^^^^^^
       501:     except TypeError as e:

            a:  3
            b:  7
            a + b:  10
        


Object is not iterable
~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 724, in test_Object_is_not_iterable
        list(42)
    TypeError: 'int' object is not iterable
    
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Un itérable est un objet capable de renvoyer ses membres un à la fois.
    Les contenants python (`list, tuple, dict`, etc.) sont itérables.
    Une itérable est requis ici.
    
    Exception levée à la ligne 724 du fichier TESTS:\runtime\test_type_error.py.
    
       722: def test_Object_is_not_iterable():
       723:     try:
    -->724:         list(42)
       725:     except TypeError as e:

            list:  <class list>
        


Object is not subscriptable
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 710, in test_Object_is_not_subscriptable
        a = f[1]
    TypeError: 'function' object is not subscriptable
    
        Vouliez-vous dire `f(1)` ?
        
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Les objets subscriptibles sont généralement des conteneurs à partir
    desquels on peut tirer des éléments en utilisant la notation `[...]`.
    
    Peut-être que vous vouliez plutôt écrire `f(1)`.
    
    Exception levée à la ligne 710 du fichier TESTS:\runtime\test_type_error.py.
    
       708: 
       709:     try:
    -->710:         a = f[1]
                        ^^^^
       711:     except TypeError as e:

            f:  <function f> from test_Object_is_not_subscriptable
        


Slice indices must be integers or None
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 666, in test_Slice_indices_must_be_integers_or_None
        [1, 2, 3][1.0:2.0]
    TypeError: slice indices must be integers or None or have an __index__ method
    
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Lors de l’utilisation d’une tranche pour extraire une gamme d’éléments
    d’une séquence, c’est-à-dire quelque chose comme
    `[start:stop]` ou `[start:stop:step]`
    chacune des variables `start`, `stop`, et `step` doit être soit un entier, soit `None`,
    ou possiblement un autre objet ayant une méthode `__index__`.
    
    Exception levée à la ligne 666 du fichier TESTS:\runtime\test_type_error.py.
    
       664: def test_Slice_indices_must_be_integers_or_None():
       665:     try:
    -->666:         [1, 2, 3][1.0:2.0]
       667:     except TypeError as e:


Too few positional argument
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 441, in test_Too_few_positional_argument
        fn(1)
    TypeError: fn() missing 2 required positional arguments: 'b' and 'c'
    
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Vous avez apparemment invoqué la fonction 'fn()' avec
    moins d'arguments positionnels qu'il n'en faut (2 manquent).
    
    Exception levée à la ligne 441 du fichier TESTS:\runtime\test_type_error.py.
    
       439: 
       440:     try:
    -->441:         fn(1)
       442:     except TypeError as e:

            fn:  <function fn> from test_Too_few_positional_argument
        


Too many positional argument
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 422, in test_Too_many_positional_argument
        A().f(1)
    TypeError: f() takes 1 positional argument but 2 were given
    
        Peut-être avez-vous oublié `self` lors de la définition de `f`.
        
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Vous avez apparemment invoqué la fonction `f` avec
    2 arguments positionnels alors qu'elle en requiert 1.
    Peut-être avez-vous oublié `self` lors de la définition de `f`.
    
    Exception levée à la ligne 422 du fichier TESTS:\runtime\test_type_error.py.
    
       420: 
       421:     try:
    -->422:         A().f(1)
       423:     except TypeError as e:

            A:  <class A> from test_type_error.test_Too_many_positional_argument
        


Tuple no item assignment
~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 389, in test_Tuple_no_item_assignment
        a[0] = 0
    TypeError: 'tuple' object does not support item assignment
    
        Voulez-vous utiliser une liste?
        
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Dans Python, certains objets sont connus comme immuables:
    une fois définis, leur valeur ne peut pas être modifiée.
    Vous avez essayé de modifier une partie d’un tel objet immuable: un `tuple`,
    probablement en utilisant une opération d’indexation.
    Peut-être que vous vouliez plutôt utiliser une liste.
    
    Exception levée à la ligne 389 du fichier TESTS:\runtime\test_type_error.py.
    
       387:     a = (1, 2, 3)
       388:     try:
    -->389:         a[0] = 0
       390:     except TypeError as e:

            a:  (1, 2, 3)
            a[0]:  1
        


Unhachable type
~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 683, in test_Unhachable_type
        {[1, 2]: 1}
    TypeError: unhashable type: 'list'
    
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Seuls les objets hachables peuvent être utilisés
    comme éléments de `set` ou des clés de `dict`.
    Les objets hachables sont des objets qui ne changent pas de valeur
    une fois qu’ils ont été créés.Au lieu d’utiliser une liste (`list`), envisagez d’utiliser un `tuple`.
    
    Exception levée à la ligne 683 du fichier TESTS:\runtime\test_type_error.py.
    
       681: def test_Unhachable_type():
       682:     try:
    -->683:         {[1, 2]: 1}
       684:     except TypeError as e:


Unsupported operand types
~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 283, in test_Unsupported_operand_types
        a @= b
    TypeError: unsupported operand type(s) for @=: 'str' and 'int'
    
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Vous avez essayé d’utiliser l’opérateur @=
    à l’aide de deux types d’objets incompatibles:
    une chaîne de caractères (`str`) et un entier (`int`).
    Cet opérateur est normalement utilisé uniquement
    pour la multiplication des matrices.
    
    Exception levée à la ligne 283 du fichier TESTS:\runtime\test_type_error.py.
    
       281:         a = "a"
       282:         b = 2
    -->283:         a @= b
       284:     except TypeError as e:

            a:  'a'
            b:  2
        


function has no len
~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 796, in test_function_has_no_len
        len(bad)
    TypeError: object of type 'function' has no len()
    
        Avez-vous oublié d’invoquer `bad` ?
        
    Une exception `TypeError` est généralement causée par une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Je soupçonne que vous avez oublié d’ajouter des parenthèses pour invoquer `bad`.
    Vous avez peut-être voulu écrire :
    `len(bad())`
    
    Exception levée à la ligne 796 du fichier TESTS:\runtime\test_type_error.py.
    
       794:         pass
       795:     try:
    -->796:         len(bad)
       797:     except TypeError as e:

            bad:  <function bad> from test_function_has_no_len
            len:  <builtin function len>
        


UnboundLocalError
-----------------


Missing both
~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_unbound_local_error.py", line 61, in test_Missing_both
        outer_missing_both()
      File "TESTS:\runtime\test_unbound_local_error.py", line 22, in outer_missing_both
        inner()
      File "TESTS:\runtime\test_unbound_local_error.py", line 21, in inner
        spam_missing_both += 1
    UnboundLocalError: local variable 'spam_missing_both' referenced before assignment
    
        Avez-vous oublié d’ajouter soit `global spam_missing_both` ou 
        `nonlocal spam_missing_both` ?
        
    En Python, les variables utilisées à l’intérieur d’une fonction sont appelées
    variables «locales».
    Avant d’utiliser une variable locale, une valeur doit lui être attribuée.
    Une variable utilisée avant l’attribution d’une valeur est supposée
    être définie en dehors de cette fonction;
    elle est connu comme une variable «globale» (`global` ou parfois `nonlocal`).
    Vous ne pouvez pas assigner une valeur à une telle variable globale
    à l’intérieur d’une fonction sans d’abord confirmer à python
    qu’il s’agit d’une variable globale, sinon vous verrez une exception `UnboundLocalError`.
    
    Le nom `spam_missing_both` existe à la fois dans la portée globale et non locale.
    Cela peut être assez déroutant et n’est pas recommandé.
    Selon la variable à laquelle vous vouliez vous référer, vous deviez ajouter
    
        global spam_missing_both
    
    ou
    
        nonlocal spam_missing_both
    
    comme la première ligne à l’intérieur de votre fonction.
    
    L'exécution s'est arrêtée à la ligne 61 du fichier TESTS:\runtime\test_unbound_local_error.py
    
       59: def test_Missing_both():
       60:     try:
    -->61:         outer_missing_both()
       62:     except UnboundLocalError as e:

            global outer_missing_both:  <function outer_missing_both>
        
    Exception levée à la ligne 21 du fichier TESTS:\runtime\test_unbound_local_error.py.
    
       19:     spam_missing_both = 2
       20:     def inner():
    -->21:         spam_missing_both += 1
       22:     inner()

            global spam_missing_both:  1
        


Missing global
~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_unbound_local_error.py", line 27, in test_Missing_global
        outer_missing_global()
      File "TESTS:\runtime\test_unbound_local_error.py", line 10, in outer_missing_global
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
    
       25: def test_Missing_global():
       26:     try:
    -->27:         outer_missing_global()
       28:     except UnboundLocalError as e:

            global outer_missing_global:  <function outer_missing_global>
        
    Exception levée à la ligne 9 du fichier TESTS:\runtime\test_unbound_local_error.py.
    
        7: def outer_missing_global():
        8:     def inner():
    --> 9:         spam_missing_global += 1
       10:     inner()

            global spam_missing_global:  1
        


Missing nonlocal
~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_unbound_local_error.py", line 44, in test_Missing_nonlocal
        outer_missing_nonlocal()
      File "TESTS:\runtime\test_unbound_local_error.py", line 16, in outer_missing_nonlocal
        inner()
      File "TESTS:\runtime\test_unbound_local_error.py", line 15, in inner
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
    
    L'exécution s'est arrêtée à la ligne 44 du fichier TESTS:\runtime\test_unbound_local_error.py
    
       42: def test_Missing_nonlocal():
       43:     try:
    -->44:         outer_missing_nonlocal()
       45:     except UnboundLocalError as e:

            global outer_missing_nonlocal:  <function outer_missing_nonlocal>
        
    Exception levée à la ligne 15 du fichier TESTS:\runtime\test_unbound_local_error.py.
    
       13:     spam_missing_nonlocal = 1
       14:     def inner():
    -->15:         spam_missing_nonlocal += 1
       16:     inner()


Typo in local
~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_unbound_local_error.py", line 97, in test_Typo_in_local
        test2()
      File "TESTS:\runtime\test_unbound_local_error.py", line 94, in test2
        alpha3 += 1
    UnboundLocalError: local variable 'alpha3' referenced before assignment
    
        Vouliez-vous dire `alpha2` ?
        
    En Python, les variables utilisées à l’intérieur d’une fonction sont appelées
    variables «locales».
    Avant d’utiliser une variable locale, une valeur doit lui être attribuée.
    Une variable utilisée avant l’attribution d’une valeur est supposée
    être définie en dehors de cette fonction;
    elle est connu comme une variable «globale» (`global` ou parfois `nonlocal`).
    Vous ne pouvez pas assigner une valeur à une telle variable globale
    à l’intérieur d’une fonction sans d’abord confirmer à python
    qu’il s’agit d’une variable globale, sinon vous verrez une exception `UnboundLocalError`.
    
    Au lieu d’écrire `alpha3`, peut-être que vous vouliez écrire l'un des noms suivants :
    *    Portée locale : `alpha2`, `alpha1`
    
    L'exécution s'est arrêtée à la ligne 97 du fichier TESTS:\runtime\test_unbound_local_error.py
    
       95: 
       96:     try:
    -->97:         test2()
       98:     except UnboundLocalError as e:

            test2:  <function test2> from test_Typo_in_local
        
    Exception levée à la ligne 94 du fichier TESTS:\runtime\test_unbound_local_error.py.
    
       92:         alpha1 = 1
       93:         alpha2 = 1
    -->94:         alpha3 += 1


UnknownError
------------


Generic
~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_unknown_error.py", line 12, in test_Generic
        raise MyException("Some informative message about an unknown exception.")
    MyException: Some informative message about an unknown exception.
    
    Aucune information n’est disponible au sujet de cette exception.
    Veuillez signaler cet exemple à https://github.com/aroberge/friendly/issues.
    Si vous utilisez un REPL, utilisez `www('bug')` pour le faire.
    
    Si vous utilisez la console Friendly, utilisez `www()` pour
    faire une recherche sur Internet pour ce cas particulier.
    
    Exception levée à la ligne 12 du fichier TESTS:\runtime\test_unknown_error.py.
    
       10:     friendly_traceback.debug_helper.DEBUG = False
       11:     try:
    -->12:         raise MyException("Some informative message about an unknown exception.")
       13:     except Exception as e:

            global MyException:  <class test_unknown_error.MyException>
        


ValueError
----------


Date invalid month
~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_value_error.py", line 58, in test_Date_invalid_month
        d = date(2021, 13, 1)
    ValueError: month must be in 1..12
    
        Avez-vous spécifié un mois inexistant ?
        
    Une exception `ValueError` indique qu'une fonction ou une opération
    a reçu un argument du bon type, mais une valeur inappropriée.
    
    Je crois que vous avez indiqué une valeur non valide pour le mois
    dans un objet de type `date`. Les valeurs valides sont les entiers de 1 à 12.
    
    Exception levée à la ligne 58 du fichier TESTS:\runtime\test_value_error.py.
    
       56:     from datetime import date
       57:     try:
    -->58:         d = date(2021, 13, 1)
                       ^^^^^^^^^^^^^^^^^
       59:     except ValueError as e:

            date:  <class datetime.date>
        


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
       29:     except ValueError as e:

            d:  'ab'
        


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
       44:     except ValueError as e:

            c:  [1, 2, 3]
        


ZeroDivisionError
-----------------


Complex division
~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_zero_division_error.py", line 155, in test_Complex_division
        1 / zero
    ZeroDivisionError: complex division by zero
    
    Une exception de type `ZeroDivisionError` se produit lorsque vous essayez de diviser une valeur
    par zéro soit directement ou en utilisant une autre opération mathématique.
    
    Vous divisez par le terme suivant
    
         zero
    
    qui est égal à zéro.
    
    Exception levée à la ligne 155 du fichier TESTS:\runtime\test_zero_division_error.py.
    
       153:     zero = 0j
       154:     try:
    -->155:         1 / zero
       156:     except ZeroDivisionError as e:

            zero:  0j
        


Division by zero literal
~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_zero_division_error.py", line 199, in test_Division_by_zero_literal
        1. / 0
    ZeroDivisionError: float division by zero
    
    Une exception de type `ZeroDivisionError` se produit lorsque vous essayez de diviser une valeur
    par zéro soit directement ou en utilisant une autre opération mathématique.
    
    Vous divisez par zéro.
    
    Exception levée à la ligne 199 du fichier TESTS:\runtime\test_zero_division_error.py.
    
       197: 
       198:     try:
    -->199:         1. / 0
       200:     except ZeroDivisionError as e:


Division operator
~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_zero_division_error.py", line 17, in test_Division_operator
        1 / zero
    ZeroDivisionError: division by zero
    
    Une exception de type `ZeroDivisionError` se produit lorsque vous essayez de diviser une valeur
    par zéro soit directement ou en utilisant une autre opération mathématique.
    
    Vous divisez par le terme suivant
    
         zero
    
    qui est égal à zéro.
    
    Exception levée à la ligne 17 du fichier TESTS:\runtime\test_zero_division_error.py.
    
       15: 
       16:     try:
    -->17:         1 / zero
       18:     except ZeroDivisionError as e:

            zero:  0
        


Divmod
~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_zero_division_error.py", line 82, in test_Divmod
        divmod(1, zero)
    ZeroDivisionError: integer division or modulo by zero
    
    Une exception de type `ZeroDivisionError` se produit lorsque vous essayez de diviser une valeur
    par zéro soit directement ou en utilisant une autre opération mathématique.
    
    Le deuxième argument de la fonction `divmod()` est égal à zéro.
    
    Exception levée à la ligne 82 du fichier TESTS:\runtime\test_zero_division_error.py.
    
       80:     zero = 0
       81:     try:
    -->82:         divmod(1, zero)
       83:     except ZeroDivisionError as e:

            zero:  0
            divmod:  <builtin function divmod>
        


Float division
~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_zero_division_error.py", line 125, in test_Float_division
        1 / zero
    ZeroDivisionError: float division by zero
    
    Une exception de type `ZeroDivisionError` se produit lorsque vous essayez de diviser une valeur
    par zéro soit directement ou en utilisant une autre opération mathématique.
    
    Vous divisez par le terme suivant
    
         zero
    
    qui est égal à zéro.
    
    Exception levée à la ligne 125 du fichier TESTS:\runtime\test_zero_division_error.py.
    
       123:     zero = 0.
       124:     try:
    -->125:         1 / zero
       126:     except ZeroDivisionError as e:

            zero:  0.0
        


Float divmod
~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_zero_division_error.py", line 140, in test_Float_divmod
        divmod(1, zero)
    ZeroDivisionError: float divmod()
    
    Une exception de type `ZeroDivisionError` se produit lorsque vous essayez de diviser une valeur
    par zéro soit directement ou en utilisant une autre opération mathématique.
    
    Le deuxième argument de la fonction `divmod()` est égal à zéro.
    
    Exception levée à la ligne 140 du fichier TESTS:\runtime\test_zero_division_error.py.
    
       138:     zero = 0.
       139:     try:
    -->140:         divmod(1, zero)
       141:     except ZeroDivisionError as e:

            zero:  0.0
            divmod:  <builtin function divmod>
        


Float modulo
~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_zero_division_error.py", line 110, in test_Float_modulo
        1 % zero
    ZeroDivisionError: float modulo
    
    Une exception de type `ZeroDivisionError` se produit lorsque vous essayez de diviser une valeur
    par zéro soit directement ou en utilisant une autre opération mathématique.
    
    En utilisant l’opérateur modulo, vous divisez par le terme suivant
    
         zero
    
    qui est égal à zéro.
    
    Exception levée à la ligne 110 du fichier TESTS:\runtime\test_zero_division_error.py.
    
       108: 
       109:     try:
    -->110:         1 % zero
       111:     except ZeroDivisionError as e:

            zero:  0.0
        


Integer division operator
~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_zero_division_error.py", line 42, in test_Integer_division_operator
        1 // zero
    ZeroDivisionError: integer division or modulo by zero
    
    Une exception de type `ZeroDivisionError` se produit lorsque vous essayez de diviser une valeur
    par zéro soit directement ou en utilisant une autre opération mathématique.
    
    Vous divisez par le terme suivant
    
         zero
    
    qui est égal à zéro.
    
    Exception levée à la ligne 42 du fichier TESTS:\runtime\test_zero_division_error.py.
    
       40: 
       41:     try:
    -->42:         1 // zero
       43:     except ZeroDivisionError as e:

            zero:  0
        


Mixed operations
~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_zero_division_error.py", line 212, in test_Mixed_operations
        a = divmod(8, 1 // 2)
    ZeroDivisionError: integer division or modulo by zero
    
    Une exception de type `ZeroDivisionError` se produit lorsque vous essayez de diviser une valeur
    par zéro soit directement ou en utilisant une autre opération mathématique.
    
    L’expression mathématique suivante inclut une division par zéro :
    
        divmod(8, 1 // 2)
    
    Exception levée à la ligne 212 du fichier TESTS:\runtime\test_zero_division_error.py.
    
       210: def test_Mixed_operations():
       211:     try:
    -->212:         a = divmod(8, 1 // 2)
                        ^^^^^^^^^^^^^^^^^
       213:     except ZeroDivisionError as e:

            divmod:  <builtin function divmod>
            1 // 2:  0
        


Modulo operator
~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_zero_division_error.py", line 67, in test_Modulo_operator
        1 % zero
    ZeroDivisionError: integer division or modulo by zero
    
    Une exception de type `ZeroDivisionError` se produit lorsque vous essayez de diviser une valeur
    par zéro soit directement ou en utilisant une autre opération mathématique.
    
    En utilisant l’opérateur modulo, vous divisez par le terme suivant
    
         zero
    
    qui est égal à zéro.
    
    Exception levée à la ligne 67 du fichier TESTS:\runtime\test_zero_division_error.py.
    
       65: 
       66:     try:
    -->67:         1 % zero
       68:     except ZeroDivisionError as e:

            zero:  0
        


Raise zero negative power
~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\runtime\test_zero_division_error.py", line 170, in test_Raise_zero_negative_power
        zero ** -1
    ZeroDivisionError: 0.0 cannot be raised to a negative power
    
    Une exception de type `ZeroDivisionError` se produit lorsque vous essayez de diviser une valeur
    par zéro soit directement ou en utilisant une autre opération mathématique.
    
    Vous essayez d'élever le nombre 0 à une puissance négative
    ce qui équivaut à diviser par zéro.
    
    Exception levée à la ligne 170 du fichier TESTS:\runtime\test_zero_division_error.py.
    
       168:     zero = 0
       169:     try:
    -->170:         zero ** -1
       171:     except ZeroDivisionError as e:

            zero:  0
        

