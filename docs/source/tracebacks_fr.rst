
|france| Friendly tracebacks - en Français
===========================================

Le but principal de Friendly-traceback est de fournir des rétroactions plus
conviviales que les fameux **tracebacks** de Python lorsqu'une exception survient.
Ci-dessous, on peut voir quelques exemples. Le but éventuel est de documenter
ici tous les exemples possibles tels qu'interprétés par Friendly-traceback.

.. note::

     Le contenu de cette page a été généré par l'exécution de
     trb_french.py situé dans le répertoire ``tests/``.
     Ceci a besoin d'être fait de manière explicite lorsqu'on veut
     faire des corrections ou des ajouts, avant de faire la mise
     à jour du reste de la documentation avec Sphinx.

Friendly-traceback version: 0.1.6a
Python version: 3.8.4



ArithmeticError
---------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_arithmetic_error.py", line 9, in test_arithmetic_error
        raise ArithmeticError
    ArithmeticError: 
    
    `ArithmeticError` est la classe de base pour les exceptions
    qui sont soulevées pour diverses erreurs arithmétiques.
    Il est inhabituel que vous voyiez cette exception;
    normalement, une exception plus spécifique aurait dû être soulevée.
    
    Exception levée à la ligne 9 du fichier 'TESTS:\runtime\test_arithmetic_error.py'.
    
        7:         # Usually, a subclass such as ZeroDivisionError, etc., would
        8:         # likely be raised.
    --> 9:         raise ArithmeticError

        Identificateurs connus :
            ArithmeticError: <class 'ArithmeticError'>
        


AttributeError - class attribute
--------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 34, in test_attribute_error
        a.x  # Testing instance
    AttributeError: 'A' object has no attribute 'x'
    
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        The object `a` has no attribute named `x`.
        
    Exception levée à la ligne 34 du fichier 'TESTS:\runtime\test_attribute_error.py'.
    
       32:     try:
       33:         a = A()
    -->34:         a.x  # Testing instance

        Identificateurs connus :
            a: <test_attribute_error.test_attribute_error.<locals>.A object>
        


AttributeError - typo in module attribute
-----------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 63, in test_misspelled_module_attribute
        string.ascii_lowecase
    AttributeError: module 'string' has no attribute 'ascii_lowecase'
    
        Did you mean `ascii_lowercase`?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        Perhaps you meant to write `string.ascii_lowercase` instead of `string.ascii_lowecase`
        
    Exception levée à la ligne 63 du fichier 'TESTS:\runtime\test_attribute_error.py'.
    
       61: 
       62:     try:
    -->63:         string.ascii_lowecase

        Identificateurs connus :
            string: <module 'string'> from PYTHON_LIB:\string.py
        


AttributeError - typo in module attribute 2
-------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_attribute_error.py", line 78, in test_misspelled_module_attribute_2
        math.cost
    AttributeError: module 'math' has no attribute 'cost'
    
        Did you mean one of the following: `cos, cosh, acos`?
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
        Instead of writing `math.cost`, perhaps you meant to write one of 
        the following names which are attributes of module `math`:
        `cos, cosh, acos`
        
    Exception levée à la ligne 78 du fichier 'TESTS:\runtime\test_attribute_error.py'.
    
       76: 
       77:     try:
    -->78:         math.cost

        Identificateurs connus :
            math: <module 'math' (built-in)>
        


FileNotFoundError
-----------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_file_not_found_error.py", line 6, in test_file_not_found_error
        open("does_not_exist")
    FileNotFoundError: [Errno 2] No such file or directory: 'does_not_exist'
    
    Une exception `FileNotFoundError` indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe en
    écrivant le nom du fichier.
    
        Dans votre programme, le nom du fichier inconnu est `does_not_exist`.
        
    Exception levée à la ligne 6 du fichier 'TESTS:\runtime\test_file_not_found_error.py'.
    
       4: def test_file_not_found_error():
       5:     try:
    -->6:         open("does_not_exist")

        Identificateurs connus :
            open: <built-in function open>
        


ImportError
-----------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_import_error.py", line 6, in test_import_error
        from math import Pi
    ImportError: cannot import name 'Pi' from 'math' (unknown location)
    
        Did you mean `pi`?
        
    L'exception `ImportError` indique qu’un certain objet n’a pas pu
    être importé à partir d’un module ou d’un paquet. Très souvent, c’est
    parce que le nom de l’objet n’est pas écrit correctement.
    
        Perhaps you meant to import `pi` from `math` instead of `Pi`
        
    Exception levée à la ligne 6 du fichier 'TESTS:\runtime\test_import_error.py'.
    
       4: def test_import_error():
       5:     try:
    -->6:         from math import Pi


KeyError
--------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_key_error.py", line 7, in test_key_error
        d["c"]
    KeyError: 'c'
    
    Une exception `KeyError` est levée lorsqu’une valeur n’est pas trouvée
    en tant que clé dans un dictionnaire (dict) Python.
    
        Dans votre programme, la clé inconnue est `'c'`.
        
    Exception levée à la ligne 7 du fichier 'TESTS:\runtime\test_key_error.py'.
    
       5:     d = {"a": 1, "b": 2}
       6:     try:
    -->7:         d["c"]

        Identificateurs connus :
            d: {'a': 1, 'b': 2}
        


LookupError
-----------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_lookup_error.py", line 10, in test_lookup_error
        raise LookupError("Fake message")
    LookupError: Fake message
    
    `LookupError` est la classe de base pour les exceptions qui sont levées
    lorsqu’une clé ou un index utilisé sur un tableau de correspondance ou une séquence est invalide.
    Elle peut également être levée directement par codecs.lookup().
    
    Exception levée à la ligne 10 du fichier 'TESTS:\runtime\test_lookup_error.py'.
    
        8:         # other than possibly codecs.lookup(), which is why we raise
        9:         # it directly here for our example.
    -->10:         raise LookupError("Fake message")

        Identificateurs connus :
            LookupError: <class 'LookupError'>
        


IndexError - short tuple
------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_index_error.py", line 8, in test_index_error1
        print(a[3], b[2])
    IndexError: tuple index out of range
    
    Une exception `IndexError` se produit lorsque vous essayez d’obtenir un élément
    d'une liste, d'un tuple, ou d'un objet similaire (séquence), à l’aide d’un index qui
    n’existe pas; typiquement, c’est parce que l’index que vous donnez
    est plus grand que la longueur de la séquence.
    Rappel: le premier élément d'une séquence est à l'index 0.
    
    Exception levée à la ligne 8 du fichier 'TESTS:\runtime\test_index_error.py'.
    
        6:     b = [1, 2, 3]
        7:     try:
    --> 8:         print(a[3], b[2])

        Identificateurs connus :
            print: <built-in function print>
            a: (1, 2, 3)
            b: [1, 2, 3]
        


IndexError - long list
----------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_index_error.py", line 21, in test_index_error2
        print(a[50], b[0])
    IndexError: list index out of range
    
    Une exception `IndexError` se produit lorsque vous essayez d’obtenir un élément
    d'une liste, d'un tuple, ou d'un objet similaire (séquence), à l’aide d’un index qui
    n’existe pas; typiquement, c’est parce que l’index que vous donnez
    est plus grand que la longueur de la séquence.
    Rappel: le premier élément d'une séquence est à l'index 0.
    
    Exception levée à la ligne 21 du fichier 'TESTS:\runtime\test_index_error.py'.
    
       19:     b = tuple(range(50))
       20:     try:
    -->21:         print(a[50], b[0])

        Identificateurs connus :
            print: <built-in function print>
            a: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 1...]  | len(a): 40
            b: (0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 1...)  | len(b): 50
        


ModuleNotFoundError
-------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_module_not_found_error.py", line 6, in test_module_not_found_error
        import Tkinter
    ModuleNotFoundError: No module named 'Tkinter'
    
        Did you mean `tkinter`?
        
    Une exception `ModuleNotFoundError` indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe en
    écrivant le nom du module, ou parce qu’il n’est pas installé sur votre ordinateur.
    
        The name of the module that could not be imported is `Tkinter`.
        `tkinter` is an existing module that has a similar name.
        
    Exception levée à la ligne 6 du fichier 'TESTS:\runtime\test_module_not_found_error.py'.
    
       4: def test_module_not_found_error():
       5:     try:
    -->6:         import Tkinter


NameError - 1
-------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 6, in test_name_error
        this = something
    NameError: name 'something' is not defined
    
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
        Dans votre programme, le nom inconnu est `something`.
        
    Exception levée à la ligne 6 du fichier 'TESTS:\runtime\test_name_error.py'.
    
       4: def test_name_error():
       5:     try:
    -->6:         this = something


NameError - 2
-------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 19, in test_name_error2
        x = babs(-1)
    NameError: name 'babs' is not defined
    
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
        Dans votre programme, le nom inconnu est `babs`.
        Au lieu d’écrire `babs`, peut-être que vous vouliez écrire l'un des noms suivants :
        *    Portée locale : `nabs`
        *    Portée globale : `fabs`
        *    Identifiant Python (builtins) : `abs`
        
    Exception levée à la ligne 19 du fichier 'TESTS:\runtime\test_name_error.py'.
    
       17:     nabs = 1
       18:     try:
    -->19:         x = babs(-1)


NameError - 3
-------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 33, in test_name_error3
        y = x
    NameError: name 'x' is not defined
    
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
        Dans votre programme, le nom inconnu est `x`.
        Annotation de type trouvée pour `x` en tant que variable globale.
        Peut-être aviez-vous écrit `x : 3` au lieu de `x = 3`.
        
    Exception levée à la ligne 33 du fichier 'TESTS:\runtime\test_name_error.py'.
    
       31: def test_name_error3():
       32:     try:
    -->33:         y = x


NameError - 4
-------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_name_error.py", line 45, in test_name_error4
        cost  # wrote from math import * above
    NameError: name 'cost' is not defined
    
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
        Dans votre programme, le nom inconnu est `cost`.
        Au lieu d’écrire `cost`, peut-être que vous vouliez écrire l'un des noms suivants :
        *    Portée globale : `cos`, `cosh`, `acos`
        
    Exception levée à la ligne 45 du fichier 'TESTS:\runtime\test_name_error.py'.
    
       43: def test_name_error4():
       44:     try:
    -->45:         cost  # wrote from math import * above


OverflowError
-------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_overflow_error.py", line 6, in test_overflow_error
        2.0 ** 1600
    OverflowError: (34, 'Result too large')
    
    Une exception de type `OverflowError` est levée lorsque le résultat d’une opération arithmétique
    est trop grand pour être manipulé par le processeur de l’ordinateur.
    
    Exception levée à la ligne 6 du fichier 'TESTS:\runtime\test_overflow_error.py'.
    
       4: def test_overflow_error():
       5:     try:
    -->6:         2.0 ** 1600


RecursionError
--------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_recursion_error.py", line 8, in test_function_recursion_error
        a()
    
           ... More lines not shown. ...
    
      File "TESTS:\runtime\test_recursion_error.py", line 6, in a
        return a()
      File "TESTS:\runtime\test_recursion_error.py", line 6, in a
        return a()
    RecursionError: maximum recursion depth exceeded
    
    Une exception de type `RecursionError` est levée lorsqu’une fonction s'invoque elle-même,
    directement ou indirectement, trop de fois.
    Cette exception indique presque toujours que vous avez fait une erreur dans votre code
    et que votre programme ne terminerait jamais.
    
    L'exécution s'est arrêtée à la ligne 8 du fichier 'TESTS:\runtime\test_recursion_error.py'
    
        6:         return a()
        7:     try:
    --> 8:         a()

        Identificateurs connus :
            a: <function test_function_recursion_error.<locals>.a>
        
    Exception levée à la ligne 6 du fichier 'TESTS:\runtime\test_recursion_error.py'.
    
       4: def test_function_recursion_error():
       5:     def a():
    -->6:         return a()

        Identificateurs connus :
            a: <function test_function_recursion_error.<locals>.a>
        


TypeError - 1: concatenate two different types
----------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 8, in test_type_error1
        result = a + one
    TypeError: can only concatenate str (not "int") to str
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé de concaténer (additionner) deux types d’objets différents:
        une chaîne de caractères ('str') et un entier ('int')
        
    Exception levée à la ligne 8 du fichier 'TESTS:\runtime\test_type_error.py'.
    
        6:         a = "a"
        7:         one = 1
    --> 8:         result = a + one

        Identificateurs connus :
            a: 'a'
            one: 1
        


TypeError - 1a: concatenate two different types
-----------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 25, in test_type_error1a
        result = a + a_list
    TypeError: can only concatenate str (not "list") to str
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé de concaténer (additionner) deux types d’objets différents:
        une chaîne de caractères ('str') et une liste ('list')
        
    Exception levée à la ligne 25 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       23:         a = "a"
       24:         a_list = [1, 2, 3]
    -->25:         result = a + a_list

        Identificateurs connus :
            a: 'a'
            a_list: [1, 2, 3]
        


TypeError - 1b: concatenate two different types
-----------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 42, in test_type_error1b
        result = a_tuple + a_list
    TypeError: can only concatenate tuple (not "list") to tuple
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé de concaténer (additionner) deux types d’objets différents:
        un tuple et une liste ('list')
        
    Exception levée à la ligne 42 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       40:         a_tuple = (1, 2, 3)
       41:         a_list = [1, 2, 3]
    -->42:         result = a_tuple + a_list

        Identificateurs connus :
            a_tuple: (1, 2, 3)
            a_list: [1, 2, 3]
        


TypeError - 2: unsupported operand type(s) for +
------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 57, in test_type_error2
        result = one + none
    TypeError: unsupported operand type(s) for +: 'int' and 'NoneType'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d’additionner deux types d’objets incompatibles:
        un entier ('int') et une variable ayant la valeur `None` ('NoneType')
        
    Exception levée à la ligne 57 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       55:         one = 1
       56:         none = None
    -->57:         result = one + none

        Identificateurs connus :
            one: 1
            none: None
        


TypeError - 2a: unsupported operand type(s) for +=
--------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 74, in test_type_error2a
        one += two
    TypeError: unsupported operand type(s) for +=: 'int' and 'str'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d’additionner deux types d’objets incompatibles:
        un entier ('int') et une chaîne de caractères ('str')
        
    Exception levée à la ligne 74 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       72:         one = 1
       73:         two = "two"
    -->74:         one += two

        Identificateurs connus :
            one: 1
            two: 'two'
        


TypeError - 3: unsupported operand type(s) for -
------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 89, in test_type_error3
        result = a - b
    TypeError: unsupported operand type(s) for -: 'tuple' and 'list'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez tenté de soustraire deux types d’objets incompatibles:
        un tuple et une liste ('list')
        
    Exception levée à la ligne 89 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       87:         a = (1, 2)
       88:         b = [3, 4]
    -->89:         result = a - b

        Identificateurs connus :
            a: (1, 2)
            b: [3, 4]
        


TypeError - 3a: unsupported operand type(s) for -=
--------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 104, in test_type_error3a
        b -= a
    TypeError: unsupported operand type(s) for -=: 'list' and 'tuple'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez tenté de soustraire deux types d’objets incompatibles:
        une liste ('list') et un tuple
        
    Exception levée à la ligne 104 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       102:         a = (1, 2)
       103:         b = [3, 4]
    -->104:         b -= a

        Identificateurs connus :
            b: [3, 4]
            a: (1, 2)
        


TypeError - 4: unsupported operand type(s) for *
------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 119, in test_type_error4
        result = a * b
    TypeError: unsupported operand type(s) for *: 'complex' and 'set'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé de multiplier deux types d’objets différents:
        un nombre complexe ('complex') et un ensemble ('set')
        
    Exception levée à la ligne 119 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       117:         a = 1j
       118:         b = {2, 3}
    -->119:         result = a * b

        Identificateurs connus :
            a: 1j
            b: {2, 3}
        


TypeError - 4a: unsupported operand type(s) for ``*=``
------------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 134, in test_type_error4a
        b *= a
    TypeError: unsupported operand type(s) for *=: 'set' and 'complex'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé de multiplier deux types d’objets différents:
        un ensemble ('set') et un nombre complexe ('complex')
        
    Exception levée à la ligne 134 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       132:         a = 1j
       133:         b = {2, 3}
    -->134:         b *= a

        Identificateurs connus :
            b: {2, 3}
            a: 1j
        


TypeError - 5: unsupported operand type(s) for /
------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 149, in test_type_error5
        result = a / b
    TypeError: unsupported operand type(s) for /: 'dict' and 'float'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé de diviser deux types d’objets différents:
        un dictionnaire ('dict') et un nombre ('float')
        
    Exception levée à la ligne 149 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       147:         a = {1: 1, 2: 2}
       148:         b = 3.1416
    -->149:         result = a / b

        Identificateurs connus :
            a: {1: 1, 2: 2}
            b: 3.1416
        


TypeError - 5a: unsupported operand type(s) for /=
--------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 164, in test_type_error5a
        b /= a
    TypeError: unsupported operand type(s) for /=: 'float' and 'dict'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé de diviser deux types d’objets différents:
        un nombre ('float') et un dictionnaire ('dict')
        
    Exception levée à la ligne 164 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       162:         a = {1: 1, 2: 2}
       163:         b = 3.1416
    -->164:         b /= a

        Identificateurs connus :
            b: 3.1416
            a: {1: 1, 2: 2}
        


TypeError - 5b: unsupported operand type(s) for //
--------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 179, in test_type_error5b
        result = a // b
    TypeError: unsupported operand type(s) for //: 'dict' and 'int'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé de diviser deux types d’objets différents:
        un dictionnaire ('dict') et un entier ('int')
        
    Exception levée à la ligne 179 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       177:         a = {1: 1, 2: 2}
       178:         b = 1
    -->179:         result = a // b

        Identificateurs connus :
            a: {1: 1, 2: 2}
            b: 1
        


TypeError - 5c: unsupported operand type(s) for //=
---------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 194, in test_type_error5c
        b //= a
    TypeError: unsupported operand type(s) for //=: 'float' and 'dict'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé de diviser deux types d’objets différents:
        un nombre ('float') et un dictionnaire ('dict')
        
    Exception levée à la ligne 194 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       192:         a = {1: 1, 2: 2}
       193:         b = 3.1416
    -->194:         b //= a

        Identificateurs connus :
            b: 3.1416
            a: {1: 1, 2: 2}
        


TypeError - 6: unsupported operand type(s) for &
------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 209, in test_type_error6
        result = a & b
    TypeError: unsupported operand type(s) for &: 'str' and 'int'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d’effectuer l’opération binaire bit à bit &
        sur deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int')
        
    Exception levée à la ligne 209 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       207:         a = "a"
       208:         b = 2
    -->209:         result = a & b

        Identificateurs connus :
            a: 'a'
            b: 2
        


TypeError - 6a: unsupported operand type(s) for &=
--------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 224, in test_type_error6a
        b &= a
    TypeError: unsupported operand type(s) for &=: 'int' and 'str'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d’effectuer l’opération binaire bit à bit &=
        sur deux types d’objets incompatibles:
        un entier ('int') et une chaîne de caractères ('str')
        
    Exception levée à la ligne 224 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       222:         a = "a"
       223:         b = 2
    -->224:         b &= a

        Identificateurs connus :
            b: 2
            a: 'a'
        


TypeError - 7: unsupported operand type(s) for **
-------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 239, in test_type_error7
        result = a ** b
    TypeError: unsupported operand type(s) for ** or pow(): 'dict' and 'float'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d'élever à une puissance
        en utilisant deux types d’objets incompatibles:
        un dictionnaire ('dict') et un nombre ('float')
        
    Exception levée à la ligne 239 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       237:         a = {1: 1, 2: 2}
       238:         b = 3.1416
    -->239:         result = a ** b

        Identificateurs connus :
            a: {1: 1, 2: 2}
            b: 3.1416
        


TypeError - 7a: unsupported operand type(s) for ``**=``
-------------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 254, in test_type_error7a
        a **= b
    TypeError: unsupported operand type(s) for ** or pow(): 'dict' and 'float'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d'élever à une puissance
        en utilisant deux types d’objets incompatibles:
        un dictionnaire ('dict') et un nombre ('float')
        
    Exception levée à la ligne 254 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       252:         a = {1: 1, 2: 2}
       253:         b = 3.1416
    -->254:         a **= b

        Identificateurs connus :
            a: {1: 1, 2: 2}
            b: 3.1416
        


TypeError - 8: unsupported operand type(s) for >>
-------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 269, in test_type_error8
        result = a >> b
    TypeError: unsupported operand type(s) for >>: 'str' and 'int'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d’effectuer l’opération de décalage >>
        sur deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int')
        
    Exception levée à la ligne 269 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       267:         a = "a"
       268:         b = 42
    -->269:         result = a >> b

        Identificateurs connus :
            a: 'a'
            b: 42
        


TypeError - 8a: unsupported operand type(s) for >>=
---------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 284, in test_type_error8a
        a >>= b
    TypeError: unsupported operand type(s) for >>=: 'str' and 'int'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d’effectuer l’opération de décalage >>=
        sur deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int')
        
    Exception levée à la ligne 284 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       282:         a = "a"
       283:         b = 42
    -->284:         a >>= b

        Identificateurs connus :
            a: 'a'
            b: 42
        


TypeError - 9: unsupported operand type(s) for @
------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 299, in test_type_error9
        result = a @ b
    TypeError: unsupported operand type(s) for @: 'str' and 'int'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d’utiliser l’opérateur @
        à l’aide de deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int').
        Cet opérateur est normalement utilisé uniquement
        pour la multiplication des matrices.
        
    Exception levée à la ligne 299 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       297:         a = "a"
       298:         b = 2
    -->299:         result = a @ b

        Identificateurs connus :
            a: 'a'
            b: 2
        


TypeError - 9a: unsupported operand type(s) for @=
--------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 314, in test_type_error9a
        a @= b
    TypeError: unsupported operand type(s) for @=: 'str' and 'int'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d’utiliser l’opérateur @=
        à l’aide de deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int').
        Cet opérateur est normalement utilisé uniquement
        pour la multiplication des matrices.
        
    Exception levée à la ligne 314 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       312:         a = "a"
       313:         b = 2
    -->314:         a @= b

        Identificateurs connus :
            a: 'a'
            b: 2
        


TypeError - 10: comparison between incompatible types
-----------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 329, in test_type_error10
        b < a
    TypeError: '<' not supported between instances of 'int' and 'str'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        En utilisant <, vous avez tenté de comparer
        deux types d’objets incompatibles:
        un entier ('int') et une chaîne de caractères ('str')
        
    Exception levée à la ligne 329 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       327:         a = "a"
       328:         b = 42
    -->329:         b < a

        Identificateurs connus :
            b: 42
            a: 'a'
        


TypeError - 11: bad operand type for unary +
--------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 342, in test_type_error11
        a = +"abc"
    TypeError: bad operand type for unary +: 'str'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d’utiliser l’opérateur unaire '+'
        avec le type d’objet suivant: une chaîne de caractères ('str').
        Cette opération n’est pas définie pour ce type d’objet.
        
    Exception levée à la ligne 342 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       340: def test_type_error11():
       341:     try:
    -->342:         a = +"abc"


TypeError - 11a: bad operand type for unary -
---------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 356, in test_type_error11a
        a = -[1, 2, 3]
    TypeError: bad operand type for unary -: 'list'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d’utiliser l’opérateur unaire '-'
        avec le type d’objet suivant: une liste ('list').
        Cette opération n’est pas définie pour ce type d’objet.
        
    Exception levée à la ligne 356 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       354: def test_type_error11a():
       355:     try:
    -->356:         a = -[1, 2, 3]


TypeError - 11b: bad operand type for unary ~
---------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 370, in test_type_error11b
        a = ~(1, 2, 3)
    TypeError: bad operand type for unary ~: 'tuple'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez essayé d’utiliser l’opérateur unaire '~'
        avec le type d’objet suivant: un tuple.
        Cette opération n’est pas définie pour ce type d’objet.
        
    Exception levée à la ligne 370 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       368: def test_type_error11b():
       369:     try:
    -->370:         a = ~(1, 2, 3)


TypeError - 12: object does not support item assignment
-------------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 385, in test_type_error12
        a[0] = 0
    TypeError: 'tuple' object does not support item assignment
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Dans Python, certains objets sont connus comme immuables:
        une fois définis, leur valeur ne peut pas être modifiée.
        Vous avez essayé de modifier une partie d’un tel objet immuable: un tuple,
        probablement en utilisant une opération d’indexation.
        
    Exception levée à la ligne 385 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       383:     a = (1, 2, 3)
       384:     try:
    -->385:         a[0] = 0

        Identificateurs connus :
            a: (1, 2, 3)
        


TypeError - 13: wrong number of positional arguments
----------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 401, in test_type_error13
        fn(1)
    TypeError: fn() takes 0 positional arguments but 1 was given
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez apparemment invoqué la fonction `fn` avec
        1 arguments positionnels alors qu'elle en requiert 0.
        
    Exception levée à la ligne 401 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       399: 
       400:     try:
    -->401:         fn(1)

        Identificateurs connus :
            fn: <function test_type_error13.<locals>.fn>
        


TypeError - 13a: wrong number of positional arguments
-----------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 419, in test_type_error13a
        A().f(1)
    TypeError: f() takes 1 positional argument but 2 were given
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez apparemment invoqué la fonction `f` avec
        2 arguments positionnels alors qu'elle en requiert 1.
        Peut-être avez-vous oublié `self` lors de la définition de `f`.
        
    Exception levée à la ligne 419 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       417: 
       418:     try:
    -->419:         A().f(1)

        Identificateurs connus :
            A: <class 'test_type_error.test_type_error13a.<locals>.A'>
        


TypeError - 14: missing positional arguments
--------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 437, in test_type_error14
        fn(1)
    TypeError: fn() missing 2 required positional arguments: 'b' and 'c'
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Vous avez apparemment invoqué la fonction 'fn()' avec
        moins d'arguments positionnels qu'il n'en faut (2 manquent).
        
    Exception levée à la ligne 437 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       435: 
       436:     try:
    -->437:         fn(1)

        Identificateurs connus :
            fn: <function test_type_error14.<locals>.fn>
        


TypeError - 15: tuple object is not callable
--------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 451, in test_type_error15
        _ = (1, 2)(3, 4)
    TypeError: 'tuple' object is not callable
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Je soupçonne que vous aviez un objet du type « un tuple »,
        suivi de ce qui ressemblait à un tuple, '(...) ',
        que Python a pris comme indiquant une invocation de fonction.
        Peut-être que vous aviez une virgule manquante entre deux tuples.
        
    Exception levée à la ligne 451 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       449: def test_type_error15():
       450:     try:
    -->451:         _ = (1, 2)(3, 4)


TypeError - 15a: list object is not callable
--------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 464, in test_type_error15a
        _ = [1, 2](3, 4)
    TypeError: 'list' object is not callable
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Je soupçonne que vous aviez un objet du type « une liste ('list') »,
        suivi de ce qui ressemblait à un tuple, '(...) ',
        que Python a pris comme indiquant une invocation de fonction.
        Peut-être que vous aviez une virgule manquante avant le tuple.
        
    Exception levée à la ligne 464 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       462: def test_type_error15a():
       463:     try:
    -->464:         _ = [1, 2](3, 4)


TypeError - 16: exception derived from BaseException
----------------------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_type_error.py", line 477, in test_type_error16
        raise "exception"
    TypeError: exceptions must derive from BaseException
    
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
        Dans Python 3, les exceptions doivent être dérivées de BaseException.
        
    Exception levée à la ligne 477 du fichier 'TESTS:\runtime\test_type_error.py'.
    
       475: def test_type_error16():
       476:     try:
    -->477:         raise "exception"


UnboundLocalError - 1: missing global
-------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_unbound_local_error.py", line 27, in test_unbound_local_error_missing_global
        outer_missing_global()
      File "TESTS:\runtime\test_unbound_local_error.py", line 11, in outer_missing_global
        inner()
      File "TESTS:\runtime\test_unbound_local_error.py", line 9, in inner
        spam_missing_global += 1
    UnboundLocalError: local variable 'spam_missing_global' referenced before assignment
    
        Did you forget to add `global spam_missing_global`?
        
    En Python, les variables utilisées à l’intérieur d’une fonction sont appelées
    variables «locales».
    Avant d’utiliser une variable locale, une valeur doit lui être attribuée.
    Une variable utilisée avant l’attribution d’une valeur est supposée
    être définie en dehors de cette fonction;
    elle est connu comme une variable «globale» (`global` ou parfois `nonlocal`).
    Vous ne pouvez pas assigner une valeur à une telle variable globale
    à l’intérieur d’une fonction sans d’abord confirmer à python
    qu’il s’agit d’une variable globale, sinon vous verrez une exception `UnboundLocalError`.
    
        The identifier `spam_missing_global` exists in the global scope.
        Perhaps the statement
        
            global spam_missing_global
        
        should have been included as the first line inside your function.
        
    L'exécution s'est arrêtée à la ligne 27 du fichier 'TESTS:\runtime\test_unbound_local_error.py'
    
       25: 
       26:     try:
    -->27:         outer_missing_global()

        Identificateurs connus :
            global outer_missing_global: <function outer_missing_global>
        
    Exception levée à la ligne 9 du fichier 'TESTS:\runtime\test_unbound_local_error.py'.
    
        7: def outer_missing_global():
        8:     def inner():
    --> 9:         spam_missing_global += 1

        Identificateurs connus :
            global spam_missing_global: 1
        


UnboundLocalError - 2: missing nonlocal
---------------------------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_unbound_local_error.py", line 47, in test_unbound_local_error_missing_nonlocal
        outer_missing_nonlocal()
      File "TESTS:\runtime\test_unbound_local_error.py", line 20, in outer_missing_nonlocal
        inner()
      File "TESTS:\runtime\test_unbound_local_error.py", line 18, in inner
        spam_missing_nonlocal += 1
    UnboundLocalError: local variable 'spam_missing_nonlocal' referenced before assignment
    
        Did you forget to add `nonlocal spam_missing_nonlocal`?
        
    En Python, les variables utilisées à l’intérieur d’une fonction sont appelées
    variables «locales».
    Avant d’utiliser une variable locale, une valeur doit lui être attribuée.
    Une variable utilisée avant l’attribution d’une valeur est supposée
    être définie en dehors de cette fonction;
    elle est connu comme une variable «globale» (`global` ou parfois `nonlocal`).
    Vous ne pouvez pas assigner une valeur à une telle variable globale
    à l’intérieur d’une fonction sans d’abord confirmer à python
    qu’il s’agit d’une variable globale, sinon vous verrez une exception `UnboundLocalError`.
    
        The identifier `spam_missing_nonlocal` exists in the nonlocal scope.
        Perhaps the statement
        
            nonlocal spam_missing_nonlocal
        
        should have been included as the first line inside your function.
        
    L'exécution s'est arrêtée à la ligne 47 du fichier 'TESTS:\runtime\test_unbound_local_error.py'
    
       45: 
       46:     try:
    -->47:         outer_missing_nonlocal()

        Identificateurs connus :
            global outer_missing_nonlocal: <function outer_missing_nonlocal>
        
    Exception levée à la ligne 18 du fichier 'TESTS:\runtime\test_unbound_local_error.py'.
    
       16: 
       17:     def inner():
    -->18:         spam_missing_nonlocal += 1


Unknown exception
-----------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_unknown_error.py", line 10, in test_function_unknown_error
        raise MyException("Some informative message about an unknown exception.")
    MyException: Some informative message about an unknown exception.
    
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/Friendly-traceback/issues
    
    Exception levée à la ligne 10 du fichier 'TESTS:\runtime\test_unknown_error.py'.
    
        8: def test_function_unknown_error():
        9:     try:
    -->10:         raise MyException("Some informative message about an unknown exception.")

        Identificateurs connus :
            global MyException: <class 'test_unknown_error.MyException'>
        


ZeroDivisionError - 1
---------------------

.. code-block:: none


    Exception Python:
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
    
    Exception levée à la ligne 6 du fichier 'TESTS:\runtime\test_zero_division_error.py'.
    
       4: def test_zero_division_error():
       5:     try:
    -->6:         1 / 0


ZeroDivisionError - 2
---------------------

.. code-block:: none


    Exception Python:
    Traceback (most recent call last):
      File "TESTS:\runtime\test_zero_division_error.py", line 20, in test_zero_division_error2
        1 % zero
    ZeroDivisionError: integer division or modulo by zero
    
    Une exception de type `ZeroDivisionError` se produit lorsque
    vous tentez de diviser une valeur par zéro:
        `résultat = ma_variable / 0.`
    Ceci peut également se produire si vous calculez le reste d’une division 
    à l’aide de l’opérateur modulo '%'
        `résultat = ma_variable % 0`
    
    Exception levée à la ligne 20 du fichier 'TESTS:\runtime\test_zero_division_error.py'.
    
       18:     zero = 0
       19:     try:
    -->20:         1 % zero

        Identificateurs connus :
            zero: 0
        

