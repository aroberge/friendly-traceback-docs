
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
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_arithmetic_error' from 'C:\\Use...>
    function: 'test_arithmetic_error'

    Exception levée à la ligne 14 du fichier 'TESTS:\except\test_arithmetic_error.py'.
    
       12:     result = friendly_traceback.get_output()
       13:     assert "ArithmeticError" in result
    -->14:     assert "ArithmeticError is the base class" in result
       15:     return result

    result: "\n    Exception Python:\n        ArithmeticE..."  | len(result): 605

FileNotFoundError
-----------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_file_not_found_error' from 'C:\...>
    function: 'test_file_not_found_error'

    Exception levée à la ligne 14 du fichier 'TESTS:\except\test_file_not_found_error.py'.
    
       12:         in result
       13:     )
    -->14:     assert "that cannot be found is 'does_not_exist'." in result
       15:     return result

    result: '\n    Exception Python:\n        FileNotFoun...'  | len(result): 739

ImportError
-----------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_import_error' from 'C:\\Users\\...>
    function: 'test_import_error'

    Exception levée à la ligne 11 du fichier 'TESTS:\except\test_import_error.py'.
    
        9:     result = friendly_traceback.get_output()
       10:     assert "ImportError: cannot import name 'Pi'" in result
    -->11:     assert "The object that could not be imported is 'Pi'." in result
       12:     return result

    result: "\n    Exception Python:\n        ImportError..."  | len(result): 729

KeyError
--------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_key_error' from 'C:\\Users\\and...>
    function: 'test_key_error'

    Exception levée à la ligne 12 du fichier 'TESTS:\except\test_key_error.py'.
    
       10:     result = friendly_traceback.get_output()
       11:     assert "KeyError: 'c'" in result
    -->12:     assert "that cannot be found is 'c'." in result
       13:     return result

    result: "\n    Exception Python:\n        KeyError: '..."  | len(result): 555

LookupError
-----------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_lookup_error' from 'C:\\Users\\...>
    function: 'test_lookup_error'

    Exception levée à la ligne 15 du fichier 'TESTS:\except\test_lookup_error.py'.
    
       13:     result = friendly_traceback.get_output()
       14:     assert "LookupError" in result
    -->15:     assert "LookupError is the base class for" in result
       16:     return result

    result: "\n    Exception Python:\n        LookupError..."  | len(result): 605

IndexError - short tuple
------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_index_error' from 'C:\\Users\\a...>
    function: 'test_index_error1'

    Exception levée à la ligne 13 du fichier 'TESTS:\except\test_index_error.py'.
    
       11:     result = friendly_traceback.get_output()
       12:     assert "IndexError: tuple index out of range" in result
    -->13:     assert "In this case, the sequence is a tuple." in result
       14:     return result

    result: "\n    Exception Python:\n        IndexError:..."  | len(result): 799

IndexError - long list
----------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_index_error' from 'C:\\Users\\a...>
    function: 'test_index_error2'

    Exception levée à la ligne 26 du fichier 'TESTS:\except\test_index_error.py'.
    
       24:     result = friendly_traceback.get_output()
       25:     assert "IndexError: list index out of range" in result
    -->26:     assert "In this case, the sequence is a list." in result
       27:     return result

    result: "\n    Exception Python:\n        IndexError:..."  | len(result): 916

ModuleNotFoundError
-------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_module_not_found_error' from 'C...>
    function: 'test_module_not_found_error'

    Exception levée à la ligne 11 du fichier 'TESTS:\except\test_module_not_found_error.py'.
    
        9:     result = friendly_traceback.get_output()
       10:     assert "ModuleNotFoundError: No module named 'does_not_exist'" in result
    -->11:     assert "module that cannot be found is 'does_not_exist'." in result
       12:     return result

    result: "\n    Exception Python:\n        ModuleNotFo..."  | len(result): 779

NameError
---------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_name_error' from 'C:\\Users\\an...>
    function: 'test_name_error'

    Exception levée à la ligne 11 du fichier 'TESTS:\except\test_name_error.py'.
    
        9:     result = friendly_traceback.get_output()
       10:     assert "NameError: name 'c' is not defined" in result
    -->11:     assert "In your program, the unknown name is 'c'." in result
       12:     return result

    result: "\n    Exception Python:\n        NameError: ..."  | len(result): 706

OverflowError
-------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_overflow_error' from 'C:\\Users...>
    function: 'test_overflow_error'

    Exception levée à la ligne 11 du fichier 'TESTS:\except\test_overflow_error.py'.
    
        9:     result = friendly_traceback.get_output()
       10:     assert "OverflowError: (34, 'Result too large')" in result
    -->11:     assert "OverflowError is raised when the result" in result
       12:     return result

    result: "\n    Exception Python:\n        OverflowErr..."  | len(result): 472

TypeError - 1: concatenate two different types
----------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error1'

    Exception levée à la ligne 15 du fichier 'TESTS:\except\test_type_error.py'.
    
       13:     py36 = "must be str, not int" in result
       14:     assert py37 or py36
    -->15:     assert "a string ('str') and an integer ('int')" in result
       16:     return result

    result: '\n    Exception Python:\n        TypeError: ...'  | len(result): 823

TypeError - 1a: concatenate two different types
-----------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error1a'

    Exception levée à la ligne 30 du fichier 'TESTS:\except\test_type_error.py'.
    
       28:     py36 = "must be str, not list" in result
       29:     assert py37 or py36
    -->30:     assert "a string ('str') and a list" in result
       31:     return result

    result: '\n    Exception Python:\n        TypeError: ...'  | len(result): 851

TypeError - 1b: concatenate two different types
-----------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error1b'

    Exception levée à la ligne 43 du fichier 'TESTS:\except\test_type_error.py'.
    
       41:     result = friendly_traceback.get_output()
       42:     assert "TypeError: can only concatenate" in result
    -->43:     assert "a tuple and a list" in result
       44:     return result

    result: '\n    Exception Python:\n        TypeError: ...'  | len(result): 861

TypeError - 2: unsupported operand type(s) for +
------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error2'

    Exception levée à la ligne 56 du fichier 'TESTS:\except\test_type_error.py'.
    
       54:     result = friendly_traceback.get_output()
       55:     assert "TypeError: unsupported operand type(s) for +:" in result
    -->56:     assert "an integer ('int') and a variable equal to None ('NoneType')" in result
       57:     return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 846

TypeError - 2a: unsupported operand type(s) for +=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error2a'

    Exception levée à la ligne 69 du fichier 'TESTS:\except\test_type_error.py'.
    
       67:     result = friendly_traceback.get_output()
       68:     assert "TypeError: unsupported operand type(s) for +=:" in result
    -->69:     assert "an integer ('int') and a string ('str')" in result
       70:     return result

    result: '\n    Exception Python:\n        TypeError: ...'  | len(result): 823

TypeError - 3: unsupported operand type(s) for -
------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error3'

    Exception levée à la ligne 82 du fichier 'TESTS:\except\test_type_error.py'.
    
       80:     result = friendly_traceback.get_output()
       81:     assert "TypeError: unsupported operand type(s) for -:" in result
    -->82:     assert "a tuple and a list" in result
       83:     return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 809

TypeError - 3a: unsupported operand type(s) for -=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error3a'

    Exception levée à la ligne 95 du fichier 'TESTS:\except\test_type_error.py'.
    
       93:     result = friendly_traceback.get_output()
       94:     assert "TypeError: unsupported operand type(s) for -=:" in result
    -->95:     assert "a list and a tuple" in result
       96:     return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 802

TypeError - 4: unsupported operand type(s) for *
------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error4'

    Exception levée à la ligne 108 du fichier 'TESTS:\except\test_type_error.py'.
    
       106:     result = friendly_traceback.get_output()
       107:     assert "TypeError: unsupported operand type(s) for *:" in result
    -->108:     assert "a complex number and a set" in result
       109:     return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 828

TypeError - 4a: unsupported operand type(s) for ``*=``
------------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error4a'

    Exception levée à la ligne 121 du fichier 'TESTS:\except\test_type_error.py'.
    
       119:     result = friendly_traceback.get_output()
       120:     assert "TypeError: unsupported operand type(s) for *=:" in result
    -->121:     assert "a set and a complex number" in result
       122:     return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 821

TypeError - 5: unsupported operand type(s) for /
------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error5'

    Exception levée à la ligne 134 du fichier 'TESTS:\except\test_type_error.py'.
    
       132:     result = friendly_traceback.get_output()
       133:     assert "TypeError: unsupported operand type(s) for /:" in result
    -->134:     assert "a dictionary ('dict') and a number ('float')" in result
       135:     return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 838

TypeError - 5a: unsupported operand type(s) for /=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error5a'

    Exception levée à la ligne 147 du fichier 'TESTS:\except\test_type_error.py'.
    
       145:     result = friendly_traceback.get_output()
       146:     assert "TypeError: unsupported operand type(s) for /=:" in result
    -->147:     assert "a number ('float') and a dictionary ('dict')" in result
       148:     return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 831

TypeError - 5b: unsupported operand type(s) for //
--------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error5b'

    Exception levée à la ligne 160 du fichier 'TESTS:\except\test_type_error.py'.
    
       158:     result = friendly_traceback.get_output()
       159:     assert "TypeError: unsupported operand type(s) for //:" in result
    -->160:     assert "a dictionary ('dict') and an integer ('int')" in result
       161:     return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 826

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
        
    L'exécution s'est arrêtée à la ligne 168 du fichier 'TESTS:\except\test_type_error.py'
    
       166:         a = {1: 1, 2: 2}
       167:         b = 3.1416
    -->168:         b //= a
       169:     except Exception:

    b: 3.1416
    a: {1: 1, 2: 2}


TypeError - 6: unsupported operand type(s) for &
------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error6'

    Exception levée à la ligne 186 du fichier 'TESTS:\except\test_type_error.py'.
    
       184:     result = friendly_traceback.get_output()
       185:     assert "TypeError: unsupported operand type(s) for &:" in result
    -->186:     assert "a string ('str') and an integer ('int')" in result
       187:     return result

    result: '\n    Exception Python:\n        TypeError: ...'  | len(result): 861

TypeError - 6a: unsupported operand type(s) for &=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error6a'

    Exception levée à la ligne 199 du fichier 'TESTS:\except\test_type_error.py'.
    
       197:     result = friendly_traceback.get_output()
       198:     assert "TypeError: unsupported operand type(s) for &=:" in result
    -->199:     assert "an integer ('int') and a string ('str')" in result
       200:     return result

    result: '\n    Exception Python:\n        TypeError: ...'  | len(result): 855

TypeError - 7: unsupported operand type(s) for **
-------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error7'

    Exception levée à la ligne 212 du fichier 'TESTS:\except\test_type_error.py'.
    
       210:     result = friendly_traceback.get_output()
       211:     assert "TypeError: unsupported operand type(s) for ** or pow():" in result
    -->212:     assert "You tried to exponentiate (raise to a power)" in result
       213:     return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 887

TypeError - 7a: unsupported operand type(s) for ``**=``
-------------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error7a'

    Exception levée à la ligne 225 du fichier 'TESTS:\except\test_type_error.py'.
    
       223:     result = friendly_traceback.get_output()
       224:     assert "TypeError: unsupported operand type(s) for ** or pow():" in result
    -->225:     assert "You tried to exponentiate (raise to a power)" in result
       226:     return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 879

TypeError - 8: unsupported operand type(s) for >>
-------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error8'

    Exception levée à la ligne 238 du fichier 'TESTS:\except\test_type_error.py'.
    
       236:     result = friendly_traceback.get_output()
       237:     assert "TypeError: unsupported operand type(s) for >>:" in result
    -->238:     assert "You tried to perform the bit shifting operation >>" in result
       239:     return result

    result: '\n    Exception Python:\n        TypeError: ...'  | len(result): 860

TypeError - 8a: unsupported operand type(s) for >>=
---------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error8a'

    Exception levée à la ligne 251 du fichier 'TESTS:\except\test_type_error.py'.
    
       249:     result = friendly_traceback.get_output()
       250:     assert "TypeError: unsupported operand type(s) for >>=:" in result
    -->251:     assert "You tried to perform the bit shifting operation >>" in result
       252:     return result

    result: '\n    Exception Python:\n        TypeError: ...'  | len(result): 854

TypeError - 9: unsupported operand type(s) for @
------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error9'

    Exception levée à la ligne 264 du fichier 'TESTS:\except\test_type_error.py'.
    
       262:     result = friendly_traceback.get_output()
       263:     assert "TypeError: unsupported operand type(s) for @:" in result
    -->264:     assert "You tried to use the operator @" in result
       265:     return result

    result: '\n    Exception Python:\n        TypeError: ...'  | len(result): 953

TypeError - 9a: unsupported operand type(s) for @=
--------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error9a'

    Exception levée à la ligne 277 du fichier 'TESTS:\except\test_type_error.py'.
    
       275:     result = friendly_traceback.get_output()
       276:     assert "TypeError: unsupported operand type(s) for @=:" in result
    -->277:     assert "You tried to use the operator @" in result
       278:     return result

    result: '\n    Exception Python:\n        TypeError: ...'  | len(result): 947

TypeError - 10: comparison between incompatible types
-----------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error10'

    Exception levée à la ligne 290 du fichier 'TESTS:\except\test_type_error.py'.
    
       288:     result = friendly_traceback.get_output()
       289:     assert "TypeError: '<' not supported between instances of 'int' and 'str'" in result
    -->290:     assert "You tried to do an order comparison (<)" in result
       291:     return result

    result: '\n    Exception Python:\n        TypeError: ...'  | len(result): 837

TypeError - 11: bad operand type for unary +
--------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error11'

    Exception levée à la ligne 302 du fichier 'TESTS:\except\test_type_error.py'.
    
       300:     result = friendly_traceback.get_output()
       301:     assert "TypeError: bad operand type for unary +: 'str'" in result
    -->302:     assert "You tried to use the unary operator '+'" in result
       303:     return result

    result: '\n    Exception Python:\n        TypeError: ...'  | len(result): 837

TypeError - 11a: bad operand type for unary -
---------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error11a'

    Exception levée à la ligne 314 du fichier 'TESTS:\except\test_type_error.py'.
    
       312:     result = friendly_traceback.get_output()
       313:     assert "TypeError: bad operand type for unary -: 'list'" in result
    -->314:     assert "You tried to use the unary operator '-'" in result
       315:     return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 830

TypeError - 11b: bad operand type for unary ~
---------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error11b'

    Exception levée à la ligne 326 du fichier 'TESTS:\except\test_type_error.py'.
    
       324:     result = friendly_traceback.get_output()
       325:     assert "TypeError: bad operand type for unary ~: 'tuple'" in result
    -->326:     assert "You tried to use the unary operator '~'" in result
       327:     return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 821

TypeError - 12: object does not support item assignment
-------------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error12'

    Exception levée à la ligne 338 du fichier 'TESTS:\except\test_type_error.py'.
    
       336:     result = friendly_traceback.get_output()
       337:     assert "TypeError: 'tuple' object does not support item assignment" in result
    -->338:     assert "In Python, some objects are known as immutable:" in result
       339:     return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 944

TypeError - 13: wrong number of positional arguments
----------------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error13'

    Exception levée à la ligne 351 du fichier 'TESTS:\except\test_type_error.py'.
    
       349:         result = friendly_traceback.get_output()
       350:         assert "TypeError: fn() takes 0 positional arguments but 1 was given" in result
    -->351:         assert "1 positional argument while it requires 0" in result
       352:         return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 818

TypeError - 14: missing positional arguments
--------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error14'

    Exception levée à la ligne 364 du fichier 'TESTS:\except\test_type_error.py'.
    
       362:         result = friendly_traceback.get_output()
       363:         assert "TypeError: fn() missing 2 required positional argument" in result
    -->364:         assert "fewer positional arguments than it requires (2 missing)." in result
       365:         return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833

TypeError - 15: tuple object is not callable
--------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error15'

    Exception levée à la ligne 375 du fichier 'TESTS:\except\test_type_error.py'.
    
       373:         result = friendly_traceback.get_output()
       374:         assert "TypeError: 'tuple' object is not callable" in result
    -->375:         assert "I suspect that you had an object of this type, <a tuple>," in result
       376:         return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 923

TypeError - 15a: list object is not callable
--------------------------------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_type_error' from 'C:\\Users\\an...>
    function: 'test_type_error15a'

    Exception levée à la ligne 386 du fichier 'TESTS:\except\test_type_error.py'.
    
       384:         result = friendly_traceback.get_output()
       385:         assert "TypeError: 'list' object is not callable" in result
    -->386:         assert "I suspect that you had an object of this type, <a list>," in result
       387:         return result

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 933

UnboundLocalError
-----------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_unbound_local_error' from 'C:\\...>
    function: 'test_unbound_local_error'

    Exception levée à la ligne 25 du fichier 'TESTS:\except\test_unbound_local_error.py'.
    
       23:     result = friendly_traceback.get_output()
       24:     assert "UnboundLocalError: local variable 'a' referenced" in result
    -->25:     assert "The variable that appears to cause the problem is 'a'." in result
       26:     return result

    result: "\n    Exception Python:\n        UnboundLoca..."  | len(result): 1476

Unknown exception
-----------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_unknown_error' from 'C:\\Users\...>
    function: 'test_unknown_error'

    Exception levée à la ligne 15 du fichier 'TESTS:\except\test_unknown_error.py'.
    
       13:     result = friendly_traceback.get_output()
       14:     assert "Some informative message" in result
    -->15:     assert "Please report this example" in result
       16:     return result

    result: '\n    Exception Python:\n        MyException...'  | len(result): 561

ZeroDivisionError - 1
---------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_zero_division_error' from 'C:\\...>
    function: 'test_zero_division_error'

    Exception levée à la ligne 11 du fichier 'TESTS:\except\test_zero_division_error.py'.
    
        9:     result = friendly_traceback.get_output()
       10:     assert "ZeroDivisionError: division by zero" in result
    -->11:     assert "A ZeroDivisionError occurs when" in result
       12:     return result

    result: "\n    Exception Python:\n        ZeroDivisio..."  | len(result): 599

ZeroDivisionError - 2
---------------------

.. code-block:: none


    Exception Python:
        AssertionError: 
        
    Aucune information n’est connue à propos de cette exception.
    Veuillez signaler cet exemple à
    https://github.com/aroberge/friendly-traceback/issues
    
    L'exécution s'est arrêtée à la ligne 191 du fichier 'TESTS:\trb_common.py'
    
       189:                     mod = __import__(name)
       190:                     if function is not None:
    -->191:                         result = getattr(mod, function)()
       192:                         write(result)

    result: "\n    Exception Python:\n        TypeError: ..."  | len(result): 833
    mod: <module 'test_zero_division_error' from 'C:\\...>
    function: 'test_zero_division_error2'

    Exception levée à la ligne 23 du fichier 'TESTS:\except\test_zero_division_error.py'.
    
       21:     result = friendly_traceback.get_output()
       22:     assert "ZeroDivisionError: integer division or modulo by zero" in result
    -->23:     assert "A ZeroDivisionError occurs when" in result
       24:     return result

    result: "\n    Exception Python:\n        ZeroDivisio..."  | len(result): 619
