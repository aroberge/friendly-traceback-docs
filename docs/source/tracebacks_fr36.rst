
Friendly tracebacks - in French (Python 3.6)
===============================================

Nous incluons seulement les cas pour lesquels l'information
donnée par Python 3.6 diffère de celle donnée par Python 3.7.

Friendly-traceback version: 0.0.8a
Python version: 3.6.8



ImportError
-----------

.. code-block:: none


    Exception Python:
        ImportError: cannot import name 'Pi'
        
    Cette exception indique qu’un certain objet n’a pas pu
    être importé à partir d’un module ou d’un paquet. Très souvent, c’est
    parce que le nom de l’objet n’est pas écrit correctement.
    
    Cause probable :
        L’objet qui n’a pas pu être importé est' Pi '.
        
    L'exécution s'est arrêtée à la ligne 6 du fichier 'TESTS:\test_import_error.py'
    
       4: def test_import_error():
       5:     try:
    -->6:         from math import Pi
       7:     except Exception:


TypeError - 1: must be str, not int
-----------------------------------

.. code-block:: none


    Exception Python:
        TypeError: must be str, not int
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.
    
    Cause probable :
        Vous avez essayé de concaténer (additionner) deux types d’objets différents:
        une chaîne de caractères ('str') et un entier ('int')
        
    L'exécution s'est arrêtée à la ligne 8 du fichier 'TESTS:\test_type_error.py'
    
        6:         a = "a"
        7:         one = 1
    --> 8:         result = a + one
        9:     except Exception:

    a: 'a'
    one: 1


TypeError - 1a: must be str, not list
-------------------------------------

.. code-block:: none


    Exception Python:
        TypeError: must be str, not list
        
    Une exception TypeError est généralement causée une tentative
    de combiner deux types d’objets incompatibles,
    ou en invoquant une fonction avec le mauvais type d’objet.
    
    Cause probable :
        Vous avez essayé de concaténer (additionner) deux types d’objets différents:
        une chaîne de caractères ('str') et une liste ('list')
        
    L'exécution s'est arrêtée à la ligne 22 du fichier 'TESTS:\test_type_error.py'
    
       20:         a = "a"
       21:         a_list = [1, 2, 3]
    -->22:         result = a + a_list
       23:     except Exception:

    a: 'a'
    a_list: [1, 2, 3]

