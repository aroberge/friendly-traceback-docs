
Friendly tracebacks - in English (Python 3.6)
===============================================

Cases for which the information given by Python 3.6 differs from that
given by Python 3.7

Friendly-traceback version: 0.0.6alpha
Python version: 3.6.8



ImportError
-----------

.. code-block:: none


    Python exception: 
        ImportError: cannot import name 'Pi'
    
    This exception indicates that a certain object could not
    be imported from a module or package. Most often, this is
    because the name of the object is not spelled correctly.
    
    Likely cause:
        The object that could not be imported is 'Pi'.
        
    Execution stopped on line 7 of file 'TESTS:\test_import_error.py'.
    
       5: def test_import_error():
       6:     try:
    -->7:         from math import Pi
       8:     except Exception:

TypeError - 1: must be str, not int
-----------------------------------

.. code-block:: none


    Python exception: 
        TypeError: must be str, not int
    
    A TypeError is usually caused by trying
    to combine two incompatible types of objects,
    or by calling a function with the wrong type of object.
    
    Likely cause:
        You tried to concatenate (add) two different types of objects:
        a string ('str') and an integer ('int')
        
    Execution stopped on line 9 of file 'TESTS:\test_type_error.py'.
    
        7:         a = "a"
        8:         one = 1
    --> 9:         result = a + one
       10:     except Exception:
    a: 'a'
    one: 1


TypeError - 1a: must be str, not list
-------------------------------------

.. code-block:: none


    Python exception: 
        TypeError: must be str, not list
    
    A TypeError is usually caused by trying
    to combine two incompatible types of objects,
    or by calling a function with the wrong type of object.
    
    Likely cause:
        You tried to concatenate (add) two different types of objects:
        a string ('str') and a list
        
    Execution stopped on line 23 of file 'TESTS:\test_type_error.py'.
    
       21:         a = "a"
       22:         a_list = [1, 2, 3]
    -->23:         result = a + a_list
       24:     except Exception:
    a: 'a'
    a_list: [1, 2, 3]

