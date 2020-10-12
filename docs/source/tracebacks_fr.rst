
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

Friendly-traceback version: 0.1.1a
Python version: 3.8.4



ArithmeticError
---------------

.. code-block:: none


    Exception Python:
        ArithmeticError: 
        
    `ArithmeticError` est la classe de base pour les exceptions
    qui sont soulevées pour diverses erreurs arithmétiques.
    Il est inhabituel que vous voyiez cette exception;
    normalement, une exception plus spécifique aurait dû être soulevée.
    
    Exception levée à la ligne 9 du fichier 'TESTS:\except\test_arithmetic_error.py'.
    
        7:         # Usually, a subclass such as ZeroDivisionError, etc., would
        8:         # likely be raised.
    --> 9:         raise ArithmeticError

        Identificateurs connus :
            ArithmeticError: <class 'ArithmeticError'>
        


AttributeError - class attribute
--------------------------------

.. code-block:: none


    Exception Python:
        AttributeError: type object 'A' has no attribute 'x'
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    Cause probable basée sur les informations données par Python :
        Dans votre programme, l’objet est `A` et l’attribut est `x`.
        
    Exception levée à la ligne 10 du fichier 'TESTS:\except\test_attribute_error.py'.
    
        8:     A()
        9:     try:
    -->10:         A.x

        Identificateurs connus :
            A: <class 'test_attribute_error.test_attrib...>
        


AttributeError - typo in module attribute
-----------------------------------------

.. code-block:: none


    Exception Python:
        AttributeError: module 'string' has no attribute 'ascii_lowecase'
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    Cause probable basée sur les informations données par Python :
        Peut-être que vous vouliez plutôt écrire : `ascii_lowercase` au lieu de `ascii_lowecase`.
        
    Exception levée à la ligne 25 du fichier 'TESTS:\except\test_attribute_error.py'.
    
       23: 
       24:     try:
    -->25:         string.ascii_lowecase

        Identificateurs connus :
            string: <module 'string'>
        


AttributeError - typo in module attribute 2
-------------------------------------------

.. code-block:: none


    Exception Python:
        AttributeError: module 'math' has no attribute 'cost'
        
    Une exception `AttributeError` se produit lorsque le code contient quelque chose comme
        `object.x`
    et `x` n’est pas une méthode ou un attribut (variable) appartenant à `objet`.
    
    Cause probable basée sur les informations données par Python :
        Au lieu d’écrire `cost`, peut-être que vous vouliez écrire l'un des attributs suivants :
        [`cos`, `cosh`, `acos`]
        
    Exception levée à la ligne 40 du fichier 'TESTS:\except\test_attribute_error.py'.
    
       38: 
       39:     try:
    -->40:         math.cost

        Identificateurs connus :
            math: <module 'math' (built-in)>
        


FileNotFoundError
-----------------

.. code-block:: none


    Exception Python:
        FileNotFoundError: [Errno 2] No such file or directory: 'does_not_exist'
        
    Une exception `FileNotFoundError` indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe en
    écrivant le nom du fichier.
    
    Cause probable basée sur les informations données par Python :
        Dans votre programme, le nom du fichier inconnu est `does_not_exist`.
        
    Exception levée à la ligne 6 du fichier 'TESTS:\except\test_file_not_found_error.py'.
    
       4: def test_file_not_found_error():
       5:     try:
    -->6:         open("does_not_exist")

        Identificateurs connus :
            open: <built-in function open>
        


ImportError
-----------

.. code-block:: none


    Exception Python:
        ImportError: cannot import name 'Pi' from 'math' (unknown location)
        
    L'exception `ImportError` indique qu’un certain objet n’a pas pu
    être importé à partir d’un module ou d’un paquet. Très souvent, c’est
    parce que le nom de l’objet n’est pas écrit correctement.
    
    Cause probable basée sur les informations données par Python :
        L’objet qui n’a pas pu être importé est `Pi`.
        Le module ou le paquet d'où il devait être importé est `math`.
        
    Exception levée à la ligne 6 du fichier 'TESTS:\except\test_import_error.py'.
    
       4: def test_import_error():
       5:     try:
    -->6:         from math import Pi


KeyError
--------

.. code-block:: none


    Exception Python:
        KeyError: 'c'
        
    Une exception `KeyError` est levée lorsqu’une valeur n’est pas trouvée
    en tant que clé dans un dictionnaire (dict) Python.
    
    Cause probable basée sur les informations données par Python :
        Dans votre programme, le nom de la clé inconnue est `c`.
        
    Exception levée à la ligne 7 du fichier 'TESTS:\except\test_key_error.py'.
    
       5:     d = {"a": 1, "b": 2}
       6:     try:
    -->7:         d["c"]

        Identificateurs connus :
            d: {'a': 1, 'b': 2}
        


LookupError
-----------

.. code-block:: none


    Exception Python:
        LookupError: 
        
    `LookupError` est la classe de base pour les exceptions qui sont levées
    lorsqu’une clé ou un index utilisé sur un tableau de correspondance ou une séquence est invalide.
    Elle peut également être levée directement par codecs.lookup().
    
    Exception levée à la ligne 10 du fichier 'TESTS:\except\test_lookup_error.py'.
    
        8:         # other than possibly codecs.lookup(), which is why we raise
        9:         # it directly here for our example.
    -->10:         raise LookupError

        Identificateurs connus :
            LookupError: <class 'LookupError'>
        


IndexError - short tuple
------------------------

.. code-block:: none


    Exception Python:
        IndexError: tuple index out of range
        
    Une exception `IndexError` se produit lorsque vous essayez d’obtenir un élément
    d'une liste, d'un tuple, ou d'un objet similaire (séquence), à l’aide d’un index qui
    n’existe pas; typiquement, c’est parce que l’index que vous donnez
    est plus grand que la longueur de la séquence.
    Rappel: le premier élément d'une séquence est à l'index 0.
    
    Exception levée à la ligne 8 du fichier 'TESTS:\except\test_index_error.py'.
    
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
        IndexError: list index out of range
        
    Une exception `IndexError` se produit lorsque vous essayez d’obtenir un élément
    d'une liste, d'un tuple, ou d'un objet similaire (séquence), à l’aide d’un index qui
    n’existe pas; typiquement, c’est parce que l’index que vous donnez
    est plus grand que la longueur de la séquence.
    Rappel: le premier élément d'une séquence est à l'index 0.
    
    Exception levée à la ligne 21 du fichier 'TESTS:\except\test_index_error.py'.
    
       19:     b = tuple(range(50))
       20:     try:
    -->21:         print(a[50], b[0])

        Identificateurs connus :
            print: <built-in function print>
            a: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 1...]  | len(a): 40
            b: (0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 1...)  | len(b): 50
        


ModuleNotFoundError
-------------------

.. code-block:: none


    Exception Python:
        ModuleNotFoundError: No module named 'does_not_exist'
        
    Une exception `ModuleNotFoundError` indique que vous
    essayez d’importer un module qui ne peut pas être trouvé par Python.
    Cela pourrait être parce que vous fait une faute d'orthographe en
    écrivant le nom du module, ou parce qu’il n’est pas installé sur votre ordinateur.
    
    Cause probable basée sur les informations données par Python :
        Dans votre programme, le nom du module inconnu est `does_not_exist`.
        
    Exception levée à la ligne 6 du fichier 'TESTS:\except\test_module_not_found_error.py'.
    
       4: def test_module_not_found_error():
       5:     try:
    -->6:         import does_not_exist


NameError - 1
-------------

.. code-block:: none


    Exception Python:
        NameError: name 'something' is not defined
        
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
    Cause probable basée sur les informations données par Python :
        Dans votre programme, le nom inconnu est `something`.
        
    Exception levée à la ligne 6 du fichier 'TESTS:\except\test_name_error.py'.
    
       4: def test_name_error():
       5:     try:
    -->6:         this = something


NameError - 2
-------------

.. code-block:: none


    Exception Python:
        NameError: name 'babs' is not defined
        
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
    Cause probable basée sur les informations données par Python :
        Dans votre programme, le nom inconnu est `babs`.
        Au lieu d’écrire `babs`, peut-être que vous vouliez écrire l'un des noms suivants :
        *    Portée locale : `nabs`
        *    Portée globale : `fabs`
        *    Identifiant Python (builtins) : `abs`
        
    Exception levée à la ligne 19 du fichier 'TESTS:\except\test_name_error.py'.
    
       17:     nabs = 1
       18:     try:
    -->19:         x = babs(-1)


NameError - 3
-------------

.. code-block:: none


    Exception Python:
        NameError: name 'x' is not defined
        
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
    Cause probable basée sur les informations données par Python :
        Dans votre programme, le nom inconnu est `x`.
        Annotation de type trouvée pour `x` en tant que variable globale.
        Peut-être aviez-vous écrit `x : 3` au lieu de `x = 3`.
        
    Exception levée à la ligne 33 du fichier 'TESTS:\except\test_name_error.py'.
    
       31: def test_name_error3():
       32:     try:
    -->33:         y = x


NameError - 4
-------------

.. code-block:: none


    Exception Python:
        NameError: name 'cost' is not defined
        
    Une exception `NameError` indique que le nom d'une variable
    ou d'une fonction n'est pas connue par Python.
    Habituellement, ceci indique une simple faute d'orthographe.
    Cependant, cela peut également indiquer que le nom a été
    utilisé avant qu'on ne lui ait associé une valeur.
    
    Cause probable basée sur les informations données par Python :
        Dans votre programme, le nom inconnu est `cost`.
        Au lieu d’écrire `cost`, peut-être que vous vouliez écrire l'un des noms suivants :
        *    Portée globale : `cos`, `cosh`, `acos`
        
    Exception levée à la ligne 45 du fichier 'TESTS:\except\test_name_error.py'.
    
       43: def test_name_error4():
       44:     try:
    -->45:         cost  # wrote from math import * above


OverflowError
-------------

.. code-block:: none


    Exception Python:
        OverflowError: (34, 'Result too large')
        
    Une exception de type `OverflowError` est levée lorsque le résultat d’une opération arithmétique
    est trop grand pour être manipulé par le processeur de l’ordinateur.
    
    Exception levée à la ligne 6 du fichier 'TESTS:\except\test_overflow_error.py'.
    
       4: def test_overflow_error():
       5:     try:
    -->6:         2.0 ** 1600


RecursionError
--------------

.. code-block:: none


    Exception Python:
        RecursionError: maximum recursion depth exceeded
        
    Une exception de type `RecursionError` est levée lorsqu’une fonction s'invoque elle-même,
    directement ou indirectement, trop de fois.
    Cette exception indique presque toujours que vous avez fait une erreur dans votre code
    et que votre programme ne terminerait jamais.
    
    L'exécution s'est arrêtée à la ligne 8 du fichier 'TESTS:\except\test_recursion_error.py'
    
        6:         return a()
        7:     try:
    --> 8:         a()

        Identificateurs connus :
            a: <function test_recursion_error.<locals>.a>
        
    Exception levée à la ligne 6 du fichier 'TESTS:\except\test_recursion_error.py'.
    
       4: def test_recursion_error():
       5:     def a():
    -->6:         return a()

        Identificateurs connus :
            a: <function test_recursion_error.<locals>.a>
        


TypeError - 1: concatenate two different types
----------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: can only concatenate str (not "int") to str
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de concaténer (additionner) deux types d’objets différents:
        une chaîne de caractères ('str') et un entier ('int')
        
    Exception levée à la ligne 8 du fichier 'TESTS:\except\test_type_error.py'.
    
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
        TypeError: can only concatenate str (not "list") to str
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de concaténer (additionner) deux types d’objets différents:
        une chaîne de caractères ('str') et une liste ('list')
        
    Exception levée à la ligne 25 du fichier 'TESTS:\except\test_type_error.py'.
    
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
        TypeError: can only concatenate tuple (not "list") to tuple
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de concaténer (additionner) deux types d’objets différents:
        un tuple et une liste ('list')
        
    Exception levée à la ligne 42 du fichier 'TESTS:\except\test_type_error.py'.
    
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
        TypeError: unsupported operand type(s) for +: 'int' and 'NoneType'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’additionner deux types d’objets incompatibles:
        un entier ('int') et a variable equal to `None` (`NoneType`)
        
    Exception levée à la ligne 57 du fichier 'TESTS:\except\test_type_error.py'.
    
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
        TypeError: unsupported operand type(s) for +=: 'int' and 'str'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’additionner deux types d’objets incompatibles:
        un entier ('int') et une chaîne de caractères ('str')
        
    Exception levée à la ligne 72 du fichier 'TESTS:\except\test_type_error.py'.
    
       70:         one = 1
       71:         two = "two"
    -->72:         one += two

        Identificateurs connus :
            one: 1
            two: 'two'
        


TypeError - 3: unsupported operand type(s) for -
------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for -: 'tuple' and 'list'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez tenté de soustraire deux types d’objets incompatibles:
        un tuple et une liste ('list')
        
    Exception levée à la ligne 87 du fichier 'TESTS:\except\test_type_error.py'.
    
       85:         a = (1, 2)
       86:         b = [3, 4]
    -->87:         result = a - b

        Identificateurs connus :
            a: (1, 2)
            b: [3, 4]
        


TypeError - 3a: unsupported operand type(s) for -=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for -=: 'list' and 'tuple'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez tenté de soustraire deux types d’objets incompatibles:
        une liste ('list') et un tuple
        
    Exception levée à la ligne 102 du fichier 'TESTS:\except\test_type_error.py'.
    
       100:         a = (1, 2)
       101:         b = [3, 4]
    -->102:         b -= a

        Identificateurs connus :
            b: [3, 4]
            a: (1, 2)
        


TypeError - 4: unsupported operand type(s) for *
------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for *: 'complex' and 'set'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de multiplier deux types d’objets différents:
        un nombre complexe ('complex') et un ensemble ('set')
        
    Exception levée à la ligne 117 du fichier 'TESTS:\except\test_type_error.py'.
    
       115:         a = 1j
       116:         b = {2, 3}
    -->117:         result = a * b

        Identificateurs connus :
            a: 1j
            b: {2, 3}
        


TypeError - 4a: unsupported operand type(s) for ``*=``
------------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for *=: 'set' and 'complex'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de multiplier deux types d’objets différents:
        un ensemble ('set') et un nombre complexe ('complex')
        
    Exception levée à la ligne 132 du fichier 'TESTS:\except\test_type_error.py'.
    
       130:         a = 1j
       131:         b = {2, 3}
    -->132:         b *= a

        Identificateurs connus :
            b: {2, 3}
            a: 1j
        


TypeError - 5: unsupported operand type(s) for /
------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for /: 'dict' and 'float'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de diviser deux types d’objets différents:
        un dictionnaire ('dict') et un nombre ('float')
        
    Exception levée à la ligne 147 du fichier 'TESTS:\except\test_type_error.py'.
    
       145:         a = {1: 1, 2: 2}
       146:         b = 3.1416
    -->147:         result = a / b

        Identificateurs connus :
            a: {1: 1, 2: 2}
            b: 3.1416
        


TypeError - 5a: unsupported operand type(s) for /=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for /=: 'float' and 'dict'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de diviser deux types d’objets différents:
        un nombre ('float') et un dictionnaire ('dict')
        
    Exception levée à la ligne 162 du fichier 'TESTS:\except\test_type_error.py'.
    
       160:         a = {1: 1, 2: 2}
       161:         b = 3.1416
    -->162:         b /= a

        Identificateurs connus :
            b: 3.1416
            a: {1: 1, 2: 2}
        


TypeError - 5b: unsupported operand type(s) for //
--------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for //: 'dict' and 'int'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de diviser deux types d’objets différents:
        un dictionnaire ('dict') et un entier ('int')
        
    Exception levée à la ligne 177 du fichier 'TESTS:\except\test_type_error.py'.
    
       175:         a = {1: 1, 2: 2}
       176:         b = 1
    -->177:         result = a // b

        Identificateurs connus :
            a: {1: 1, 2: 2}
            b: 1
        


TypeError - 5c: unsupported operand type(s) for //=
---------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for //=: 'float' and 'dict'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de diviser deux types d’objets différents:
        un nombre ('float') et un dictionnaire ('dict')
        
    Exception levée à la ligne 192 du fichier 'TESTS:\except\test_type_error.py'.
    
       190:         a = {1: 1, 2: 2}
       191:         b = 3.1416
    -->192:         b //= a

        Identificateurs connus :
            b: 3.1416
            a: {1: 1, 2: 2}
        


TypeError - 6: unsupported operand type(s) for &
------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for &: 'str' and 'int'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’effectuer l’opération binaire bit à bit &
        sur deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int')
        
    Exception levée à la ligne 207 du fichier 'TESTS:\except\test_type_error.py'.
    
       205:         a = "a"
       206:         b = 2
    -->207:         result = a & b

        Identificateurs connus :
            a: 'a'
            b: 2
        


TypeError - 6a: unsupported operand type(s) for &=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for &=: 'int' and 'str'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’effectuer l’opération binaire bit à bit &=
        sur deux types d’objets incompatibles:
        un entier ('int') et une chaîne de caractères ('str')
        
    Exception levée à la ligne 222 du fichier 'TESTS:\except\test_type_error.py'.
    
       220:         a = "a"
       221:         b = 2
    -->222:         b &= a

        Identificateurs connus :
            b: 2
            a: 'a'
        


TypeError - 7: unsupported operand type(s) for **
-------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for ** or pow(): 'dict' and 'float'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d'élever à une puissance
        en utilisant deux types d’objets incompatibles:
        un dictionnaire ('dict') et un nombre ('float')
        
    Exception levée à la ligne 237 du fichier 'TESTS:\except\test_type_error.py'.
    
       235:         a = {1: 1, 2: 2}
       236:         b = 3.1416
    -->237:         result = a ** b

        Identificateurs connus :
            a: {1: 1, 2: 2}
            b: 3.1416
        


TypeError - 7a: unsupported operand type(s) for ``**=``
-------------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for ** or pow(): 'dict' and 'float'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d'élever à une puissance
        en utilisant deux types d’objets incompatibles:
        un dictionnaire ('dict') et un nombre ('float')
        
    Exception levée à la ligne 252 du fichier 'TESTS:\except\test_type_error.py'.
    
       250:         a = {1: 1, 2: 2}
       251:         b = 3.1416
    -->252:         a **= b

        Identificateurs connus :
            a: {1: 1, 2: 2}
            b: 3.1416
        


TypeError - 8: unsupported operand type(s) for >>
-------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for >>: 'str' and 'int'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’effectuer l’opération de décalage >>
        sur deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int')
        
    Exception levée à la ligne 267 du fichier 'TESTS:\except\test_type_error.py'.
    
       265:         a = "a"
       266:         b = 42
    -->267:         result = a >> b

        Identificateurs connus :
            a: 'a'
            b: 42
        


TypeError - 8a: unsupported operand type(s) for >>=
---------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for >>=: 'str' and 'int'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’effectuer l’opération de décalage >>=
        sur deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int')
        
    Exception levée à la ligne 282 du fichier 'TESTS:\except\test_type_error.py'.
    
       280:         a = "a"
       281:         b = 42
    -->282:         a >>= b

        Identificateurs connus :
            a: 'a'
            b: 42
        


TypeError - 9: unsupported operand type(s) for @
------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for @: 'str' and 'int'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’utiliser l’opérateur @
        à l’aide de deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int').
        Cet opérateur est normalement utilisé uniquement
        pour la multiplication des matrices.
        
    Exception levée à la ligne 297 du fichier 'TESTS:\except\test_type_error.py'.
    
       295:         a = "a"
       296:         b = 2
    -->297:         result = a @ b

        Identificateurs connus :
            a: 'a'
            b: 2
        


TypeError - 9a: unsupported operand type(s) for @=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for @=: 'str' and 'int'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’utiliser l’opérateur @=
        à l’aide de deux types d’objets incompatibles:
        une chaîne de caractères ('str') et un entier ('int').
        Cet opérateur est normalement utilisé uniquement
        pour la multiplication des matrices.
        
    Exception levée à la ligne 312 du fichier 'TESTS:\except\test_type_error.py'.
    
       310:         a = "a"
       311:         b = 2
    -->312:         a @= b

        Identificateurs connus :
            a: 'a'
            b: 2
        


TypeError - 10: comparison between incompatible types
-----------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: '<' not supported between instances of 'int' and 'str'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        En utilisant <, vous avez tenté de comparer
        deux types d’objets incompatibles:
        un entier ('int') et une chaîne de caractères ('str')
        
    Exception levée à la ligne 327 du fichier 'TESTS:\except\test_type_error.py'.
    
       325:         a = "a"
       326:         b = 42
    -->327:         b < a

        Identificateurs connus :
            b: 42
            a: 'a'
        


TypeError - 11: bad operand type for unary +
--------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: bad operand type for unary +: 'str'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’utiliser l’opérateur unaire '+'
        avec le type d’objet suivant: une chaîne de caractères ('str').
        Cette opération n’est pas définie pour ce type d’objet.
        
    Exception levée à la ligne 340 du fichier 'TESTS:\except\test_type_error.py'.
    
       338: def test_type_error11():
       339:     try:
    -->340:         a = +"abc"


TypeError - 11a: bad operand type for unary -
---------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: bad operand type for unary -: 'list'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’utiliser l’opérateur unaire '-'
        avec le type d’objet suivant: une liste ('list').
        Cette opération n’est pas définie pour ce type d’objet.
        
    Exception levée à la ligne 354 du fichier 'TESTS:\except\test_type_error.py'.
    
       352: def test_type_error11a():
       353:     try:
    -->354:         a = -[1, 2, 3]


TypeError - 11b: bad operand type for unary ~
---------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: bad operand type for unary ~: 'tuple'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’utiliser l’opérateur unaire '~'
        avec le type d’objet suivant: un tuple.
        Cette opération n’est pas définie pour ce type d’objet.
        
    Exception levée à la ligne 368 du fichier 'TESTS:\except\test_type_error.py'.
    
       366: def test_type_error11b():
       367:     try:
    -->368:         a = ~(1, 2, 3)


TypeError - 12: object does not support item assignment
-------------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: 'tuple' object does not support item assignment
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Dans Python, certains objets sont connus comme immuables:
        une fois définis, leur valeur ne peut pas être modifiée.
        Vous avez essayé de modifier une partie d’un tel objet immuable: un tuple,
        probablement en utilisant une opération d’indexation.
        
    Exception levée à la ligne 383 du fichier 'TESTS:\except\test_type_error.py'.
    
       381:     a = (1, 2, 3)
       382:     try:
    -->383:         a[0] = 0

        Identificateurs connus :
            a: (1, 2, 3)
        


TypeError - 13: wrong number of positional arguments
----------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: fn() takes 0 positional arguments but 1 was given
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez apparemment invoqué la fonction `fn` avec
        1 arguments positionnels alors qu'elle en requiert 0.
        
    Exception levée à la ligne 399 du fichier 'TESTS:\except\test_type_error.py'.
    
       397: 
       398:     try:
    -->399:         fn(1)

        Identificateurs connus :
            fn: <function test_type_error13.<locals>.fn>
        


TypeError - 14: missing positional arguments
--------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: fn() missing 2 required positional arguments: 'b' and 'c'
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez apparemment invoqué la fonction 'fn()' avec
        moins d'arguments positionnels qu'il n'en faut (2 manquent).
        
    Exception levée à la ligne 435 du fichier 'TESTS:\except\test_type_error.py'.
    
       433: 
       434:     try:
    -->435:         fn(1)

        Identificateurs connus :
            fn: <function test_type_error14.<locals>.fn>
        


TypeError - 15: tuple object is not callable
--------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: 'tuple' object is not callable
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Je soupçonne que vous aviez un objet du type « un tuple »,
        suivi de ce qui ressemblait à un tuple, '(...) ',
        que Python a pris comme indiquant une invocation de fonction.
        Peut-être que vous aviez une virgule manquante entre deux tuples.
        
    Exception levée à la ligne 449 du fichier 'TESTS:\except\test_type_error.py'.
    
       447: def test_type_error15():
       448:     try:
    -->449:         _ = (1, 2)(3, 4)


TypeError - 15a: list object is not callable
--------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: 'list' object is not callable
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Je soupçonne que vous aviez un objet du type « une liste ('list') »,
        suivi de ce qui ressemblait à un tuple, '(...) ',
        que Python a pris comme indiquant une invocation de fonction.
        Peut-être que vous aviez une virgule manquante avant le tuple.
        
    Exception levée à la ligne 462 du fichier 'TESTS:\except\test_type_error.py'.
    
       460: def test_type_error15a():
       461:     try:
    -->462:         _ = [1, 2](3, 4)


TypeError - 16: exception derived from BaseException
----------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: exceptions must derive from BaseException
        
    Une exception `TypeError` est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Dans Python 3, les exceptions doivent être dérivées de BaseException.
        
    Exception levée à la ligne 475 du fichier 'TESTS:\except\test_type_error.py'.
    
       473: def test_type_error16():
       474:     try:
    -->475:         raise "exception"


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
    elle est connu comme une variable «globale» (`global` ou parfois `nonlocal`).
    Vous ne pouvez pas assigner une valeur à une telle variable globale
    à l’intérieur d’une fonction sans d’abord confirmer à python
    qu’il s’agit d’une variable globale, sinon vous verrez une exception `UnboundLocalError`.
    
    Cause probable basée sur les informations données par Python :
        La variable qui semble causer le problème est `a`.
        Il est possible que vous avez oublié d'écrire l’instruction
        
            global a
        
        comme première ligne à l’intérieur de votre fonction.
        
    L'exécution s'est arrêtée à la ligne 21 du fichier 'TESTS:\except\test_unbound_local_error.py'
    
       19: 
       20:     try:
    -->21:         outer()

        Identificateurs connus :
            global outer: <function outer>
        
    Exception levée à la ligne 12 du fichier 'TESTS:\except\test_unbound_local_error.py'.
    
       10:     def inner():
       11:         c = 3
    -->12:         a = a + b + c

        Identificateurs connus :
            global b: 2
            c: 3
        


Unknown exception
-----------------

.. code-block:: none


    Exception Python:
        MyException: Some informative message about an unknown exception.
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    Exception levée à la ligne 10 du fichier 'TESTS:\except\test_unknown_error.py'.
    
        8: def test_unknown_error():
        9:     try:
    -->10:         raise MyException("Some informative message about an unknown exception.")

        Identificateurs connus :
            global MyException: <class 'test_unknown_error.MyException'>
        


ZeroDivisionError - 1
---------------------

.. code-block:: none


    Exception Python:
        ZeroDivisionError: division by zero
        
    Une exception de type `ZeroDivisionError` se produit lorsque
    vous tentez de diviser une valeur par zéro:
        `résultat = ma_variable / 0.`
    Ceci peut également se produire si vous calculez le reste d’une division 
    à l’aide de l’opérateur modulo '%'
        `résultat = ma_variable % 0`
    
    Exception levée à la ligne 6 du fichier 'TESTS:\except\test_zero_division_error.py'.
    
       4: def test_zero_division_error():
       5:     try:
    -->6:         1 / 0


ZeroDivisionError - 2
---------------------

.. code-block:: none


    Exception Python:
        ZeroDivisionError: integer division or modulo by zero
        
    Une exception de type `ZeroDivisionError` se produit lorsque
    vous tentez de diviser une valeur par zéro:
        `résultat = ma_variable / 0.`
    Ceci peut également se produire si vous calculez le reste d’une division 
    à l’aide de l’opérateur modulo '%'
        `résultat = ma_variable % 0`
    
    Exception levée à la ligne 20 du fichier 'TESTS:\except\test_zero_division_error.py'.
    
       18:     zero = 0
       19:     try:
    -->20:         1 % zero

        Identificateurs connus :
            zero: 0
        

