
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

Friendly-traceback version: 0.0.31a
Python version: 3.8.4



ArithmeticError
---------------

.. code-block:: none


    Exception Python:
        ArithmeticError: 
        
    ArithmeticError est la classe de base pour les exceptions
    qui sont soulevées pour diverses erreurs arithmétiques.
    Il est inhabituel que vous voyiez cette exception;
    normalement, une exception plus spécifique aurait dû être soulevée.
    
    L'exécution s'est arrêtée à la ligne 9 du fichier 'TESTS:\except\test_arithmetic_error.py'
    
        7:         # Usually, a subclass such as ZeroDivisionError, etc., would
        8:         # likely be raised.
    --> 9:         raise ArithmeticError


AttributeError - class attribute
--------------------------------

.. code-block:: none


    Exception Python:
        AttributeError: type object 'A' has no attribute 'x'
        
    Une erreur d’attribut se produit lorsque le code contient quelque chose comme
        objet.x
    et 'x' n’est pas une méthode ou un attribut (variable) appartenant à 'objet'
    
    Cause probable basée sur les informations données par Python :
        Dans votre programme, l’objet est 'A' et l’attribut est 'x'.
        
    L'exécution s'est arrêtée à la ligne 10 du fichier 'TESTS:\except\test_attribute_error.py'
    
        8:     A()
        9:     try:
    -->10:         A.x

    A: <class 'test_attribute_error.test_attribute_e...>


AttributeError - typo in module attribute
-----------------------------------------

.. code-block:: none


    Exception Python:
        AttributeError: module 'string' has no attribute 'ascii_lowecase'
        
    Une erreur d’attribut se produit lorsque le code contient quelque chose comme
        objet.x
    et 'x' n’est pas une méthode ou un attribut (variable) appartenant à 'objet'
    
    Cause probable basée sur les informations données par Python :
        Peut-être que vous vouliez plutôt écrire : 'ascii_lowercase' au lieu de 'ascii_lowecase'.
        
    L'exécution s'est arrêtée à la ligne 24 du fichier 'TESTS:\except\test_attribute_error.py'
    
       22: 
       23:     try:
    -->24:         string.ascii_lowecase

    string: <module 'string' from 'C:\\Users\\andre\\AppD...>


AttributeError - typo in module attribute 2
-------------------------------------------

.. code-block:: none


    Exception Python:
        AttributeError: module 'math' has no attribute 'cost'
        
    Une erreur d’attribut se produit lorsque le code contient quelque chose comme
        objet.x
    et 'x' n’est pas une méthode ou un attribut (variable) appartenant à 'objet'
    
    Cause probable basée sur les informations données par Python :
        Au lieu d’écrire cost, peut-être que vous vouliez écrire l'un des attributs suivants :
        ['cos', 'cosh']
        
    L'exécution s'est arrêtée à la ligne 41 du fichier 'TESTS:\except\test_attribute_error.py'
    
       39: 
       40:     try:
    -->41:         math.cost

    math: <module 'math' (built-in)>


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
    
       5:     d = {"a": 1, "b": 2}
       6:     try:
    -->7:         d["c"]

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
        
    L'exécution s'est arrêtée à la ligne 22 du fichier 'TESTS:\except\test_index_error.py'
    
       20:     b = tuple(range(50))
       21:     try:
    -->22:         print(a[50], b[0])

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
        
    L'exécution s'est arrêtée à la ligne 6 du fichier 'TESTS:\except\test_module_not_found_error.py'
    
       4: def test_module_not_found_error():
       5:     try:
    -->6:         import does_not_exist


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
    -->6:         2.0 ** 1600


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
        
    L'exécution s'est arrêtée à la ligne 24 du fichier 'TESTS:\except\test_type_error.py'
    
       22:         a = "a"
       23:         a_list = [1, 2, 3]
    -->24:         result = a + a_list

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
        
    L'exécution s'est arrêtée à la ligne 40 du fichier 'TESTS:\except\test_type_error.py'
    
       38:         a_tuple = (1, 2, 3)
       39:         a_list = [1, 2, 3]
    -->40:         result = a_tuple + a_list

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
        un entier ('int') et une variable de valeur None ('NoneType')
        
    L'exécution s'est arrêtée à la ligne 54 du fichier 'TESTS:\except\test_type_error.py'
    
       52:         one = 1
       53:         none = None
    -->54:         result = one + none

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
        
    L'exécution s'est arrêtée à la ligne 68 du fichier 'TESTS:\except\test_type_error.py'
    
       66:         one = 1
       67:         two = "two"
    -->68:         one += two

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
        
    L'exécution s'est arrêtée à la ligne 82 du fichier 'TESTS:\except\test_type_error.py'
    
       80:         a = (1, 2)
       81:         b = [3, 4]
    -->82:         result = a - b

    a: (1, 2)
    b: [3, 4]


TypeError - 3a: unsupported operand type(s) for -=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for -=: 'list' and 'tuple'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez tenté de soustraire deux types d’objets incompatibles:
        une liste ('list') et un tuple
        
    L'exécution s'est arrêtée à la ligne 96 du fichier 'TESTS:\except\test_type_error.py'
    
       94:         a = (1, 2)
       95:         b = [3, 4]
    -->96:         b -= a

    b: [3, 4]
    a: (1, 2)


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
        
    L'exécution s'est arrêtée à la ligne 110 du fichier 'TESTS:\except\test_type_error.py'
    
       108:         a = 1j
       109:         b = {2, 3}
    -->110:         result = a * b

    a: 1j
    b: {2, 3}


TypeError - 4a: unsupported operand type(s) for ``*=``
------------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for *=: 'set' and 'complex'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de multiplier deux types d’objets différents:
        un ensemble ('set') et un nombre complexe ('complex')
        
    L'exécution s'est arrêtée à la ligne 124 du fichier 'TESTS:\except\test_type_error.py'
    
       122:         a = 1j
       123:         b = {2, 3}
    -->124:         b *= a

    b: {2, 3}
    a: 1j


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
        
    L'exécution s'est arrêtée à la ligne 138 du fichier 'TESTS:\except\test_type_error.py'
    
       136:         a = {1: 1, 2: 2}
       137:         b = 3.1416
    -->138:         result = a / b

    a: {1: 1, 2: 2}
    b: 3.1416


TypeError - 5a: unsupported operand type(s) for /=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for /=: 'float' and 'dict'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de diviser deux types d’objets différents:
        un nombre ('float') et un dictionnaire ('dict')
        
    L'exécution s'est arrêtée à la ligne 152 du fichier 'TESTS:\except\test_type_error.py'
    
       150:         a = {1: 1, 2: 2}
       151:         b = 3.1416
    -->152:         b /= a

    b: 3.1416
    a: {1: 1, 2: 2}


TypeError - 5b: unsupported operand type(s) for //
--------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for //: 'dict' and 'int'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de diviser deux types d’objets différents:
        un dictionnaire ('dict') et un entier ('int')
        
    L'exécution s'est arrêtée à la ligne 166 du fichier 'TESTS:\except\test_type_error.py'
    
       164:         a = {1: 1, 2: 2}
       165:         b = 1
    -->166:         result = a // b

    a: {1: 1, 2: 2}
    b: 1


TypeError - 5c: unsupported operand type(s) for //=
---------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for //=: 'float' and 'dict'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé de diviser deux types d’objets différents:
        un nombre ('float') et un dictionnaire ('dict')
        
    L'exécution s'est arrêtée à la ligne 180 du fichier 'TESTS:\except\test_type_error.py'
    
       178:         a = {1: 1, 2: 2}
       179:         b = 3.1416
    -->180:         b //= a

    b: 3.1416
    a: {1: 1, 2: 2}


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
        
    L'exécution s'est arrêtée à la ligne 194 du fichier 'TESTS:\except\test_type_error.py'
    
       192:         a = "a"
       193:         b = 2
    -->194:         result = a & b

    a: 'a'
    b: 2


TypeError - 6a: unsupported operand type(s) for &=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: unsupported operand type(s) for &=: 'int' and 'str'
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    en invoquant une fonction avec le mauvais type d’objet,
    ou en tentant d'effectuer une opération non permise sur un type d'objet donné.
    
    Cause probable basée sur les informations données par Python :
        Vous avez essayé d’effectuer l’opération binaire bit à bit &=
        sur deux types d’objets incompatibles:
        un entier ('int') et une chaîne de caractères ('str')
        
    L'exécution s'est arrêtée à la ligne 208 du fichier 'TESTS:\except\test_type_error.py'
    
       206:         a = "a"
       207:         b = 2
    -->208:         b &= a

    b: 2
    a: 'a'


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
        
    L'exécution s'est arrêtée à la ligne 222 du fichier 'TESTS:\except\test_type_error.py'
    
       220:         a = {1: 1, 2: 2}
       221:         b = 3.1416
    -->222:         result = a ** b

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
        
    L'exécution s'est arrêtée à la ligne 236 du fichier 'TESTS:\except\test_type_error.py'
    
       234:         a = {1: 1, 2: 2}
       235:         b = 3.1416
    -->236:         a **= b

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
        
    L'exécution s'est arrêtée à la ligne 250 du fichier 'TESTS:\except\test_type_error.py'
    
       248:         a = "a"
       249:         b = 42
    -->250:         result = a >> b

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
        
    L'exécution s'est arrêtée à la ligne 264 du fichier 'TESTS:\except\test_type_error.py'
    
       262:         a = "a"
       263:         b = 42
    -->264:         a >>= b

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
        
    L'exécution s'est arrêtée à la ligne 278 du fichier 'TESTS:\except\test_type_error.py'
    
       276:         a = "a"
       277:         b = 2
    -->278:         result = a @ b

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
        
    L'exécution s'est arrêtée à la ligne 292 du fichier 'TESTS:\except\test_type_error.py'
    
       290:         a = "a"
       291:         b = 2
    -->292:         a @= b

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
        
    L'exécution s'est arrêtée à la ligne 306 du fichier 'TESTS:\except\test_type_error.py'
    
       304:         a = "a"
       305:         b = 42
    -->306:         b < a

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
        
    L'exécution s'est arrêtée à la ligne 318 du fichier 'TESTS:\except\test_type_error.py'
    
       316: def test_type_error11():
       317:     try:
    -->318:         a = +"abc"


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
        
    L'exécution s'est arrêtée à la ligne 331 du fichier 'TESTS:\except\test_type_error.py'
    
       329: def test_type_error11a():
       330:     try:
    -->331:         a = -[1, 2, 3]


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
        
    L'exécution s'est arrêtée à la ligne 344 du fichier 'TESTS:\except\test_type_error.py'
    
       342: def test_type_error11b():
       343:     try:
    -->344:         a = ~(1, 2, 3)


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
        
    L'exécution s'est arrêtée à la ligne 358 du fichier 'TESTS:\except\test_type_error.py'
    
       356:     a = (1, 2, 3)
       357:     try:
    -->358:         a[0] = 0

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
        
    L'exécution s'est arrêtée à la ligne 373 du fichier 'TESTS:\except\test_type_error.py'
    
       371: 
       372:     try:
    -->373:         fn(1)

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
        
    L'exécution s'est arrêtée à la ligne 388 du fichier 'TESTS:\except\test_type_error.py'
    
       386: 
       387:     try:
    -->388:         fn(1)

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
        Je soupçonne que vous aviez un objet du type « un tuple »,
        suivi de ce qui ressemblait à un tuple, '(...) ',
        que Python a pris comme indiquant une invocation de fonction.
        Il est possible que vous ayez oublié d'écrire une virgule avant le tuple.
        
    L'exécution s'est arrêtée à la ligne 400 du fichier 'TESTS:\except\test_type_error.py'
    
       398: def test_type_error15():
       399:     try:
    -->400:         _ = (1, 2)(3, 4)


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
        Je soupçonne que vous aviez un objet du type « une liste ('list') »,
        suivi de ce qui ressemblait à un tuple, '(...) ',
        que Python a pris comme indiquant une invocation de fonction.
        Il est possible que vous ayez oublié d'écrire une virgule avant le tuple.
        
    L'exécution s'est arrêtée à la ligne 412 du fichier 'TESTS:\except\test_type_error.py'
    
       410: def test_type_error15a():
       411:     try:
    -->412:         _ = [1, 2](3, 4)


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
        
    L'exécution s'est arrêtée à la ligne 21 du fichier 'TESTS:\except\test_unbound_local_error.py'
    
       19: 
       20:     try:
    -->21:         outer()

    global outer: <function outer>

    Exception levée à la ligne 12 du fichier 'TESTS:\except\test_unbound_local_error.py'.
    
       10:     def inner():
       11:         c = 3
    -->12:         a = a + b + c

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
    
    L'exécution s'est arrêtée à la ligne 10 du fichier 'TESTS:\except\test_unknown_error.py'
    
        8: def test_unknown_error():
        9:     try:
    -->10:         raise MyException("Some informative message about an unknown exception.")

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
    
    L'exécution s'est arrêtée à la ligne 19 du fichier 'TESTS:\except\test_zero_division_error.py'
    
       17:     zero = 0
       18:     try:
    -->19:         1 % zero

    zero: 0

