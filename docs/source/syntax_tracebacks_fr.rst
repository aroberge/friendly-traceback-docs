
|france| Friendly SyntaxError tracebacks - en Français
======================================================

Le but principal de friendly-traceback est de fournir des rétroactions plus
conviviales que les fameux **tracebacks** de Python lorsqu'une exception survient.
Ci-dessous, on peut voir quelques exemples, uniquement pour les
exceptions de type SyntaxError et des classes dérivées;
les autres sont couvertes dans une autre page.
Le but est de documenter ici tous les exemples possibles
tels qu'interprétés par friendly-traceback.

.. note::

     Le contenu de cette page a été généré par l'exécution de
     trb_syntax_french.py situé dans le répertoire ``tests/``.
     Ceci a besoin d'être fait de manière explicite lorsqu'on veut
     faire des corrections ou des ajouts, avant de faire la mise
     à jour du reste de la documentation avec Sphinx.
     Sous Windows, si Sphinx est installé sur votre ordinateur, il est
     plutôt suggéré d'exécuter make_trb.bat qui est au premier niveau
     du répertoire de fichier. Si vous faites ceci, la documentation pour
     toutes les langues sera automatiquement mise à jour.

Friendly-traceback version: 0.2.34a
Python version: 3.8.4



Using 'and' in import statement
-------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\and_in_import_statement.py", line 1
        from math import sin and cos
                             ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\and_in_import_statement.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: from math import sin and cos
                               ^

    Le mot clé Python `and` ne peut être utilisé que pour les expressions booléennes.
    Peut-être que vous vouliez écrire
    
    `from math import sin , cos`
    

Annotated name cannot be global
-------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\annotated_name_global.py", line 4
        x:int = 1
        ^
    SyntaxError: annotated name 'x' can't be global
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\annotated_name_global.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: # SyntaxError: annotated name 'x' can't be global
       2: def foo():
       3:     global x
    -->4:     x:int = 1
              ^

    L’objet nommé `x` est défini avec une annotation de type
    comme une variable locale. Il ne peut pas être déclaré variable globale.
    

Incorrect use of 'from module import ... as ...
-----------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\as_instead_of_comma_in_import.py", line 2
        from math import (sin, cos) as funcs
                                    ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\as_instead_of_comma_in_import.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: # issue 158
    -->2: from math import (sin, cos) as funcs
                                      ^

    Je suppose que vous essayez d’importer au moins un objet
    à partir du module `math` pour le renommer en utilisant le mot clé Python `as`;
    ce mot clé ne peut être utilisé que pour renommer un objet à la fois
    en utilisant une syntaxe bien définie.
    Je vous suggère de diviser une telle déclaration d’importation avec chaque objet
    renommé sur une ligne séparée comme suit:
    
        from math import objet_1 as nom_1
        from math import objet_2 as nom_2 # si nécessaire
    

Name assigned prior to global declaration
-----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_name_before_global_1.py", line 7
        global p
        ^
    SyntaxError: name 'p' is assigned to before global declaration
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_name_before_global_1.py'
    jusqu'à l'endroit indiqué par ^.
    
       3: 
       4: 
       5: def fn():
       6:     p = 1
    -->7:     global p
              ^

    Vous avez attribué une valeur à la variable `p`
    avant de la déclarer comme une variable globale.
    

Name used prior to global declaration
-------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_name_before_global_2.py", line 7
        global r
        ^
    SyntaxError: name 'r' is used prior to global declaration
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_name_before_global_2.py'
    jusqu'à l'endroit indiqué par ^.
    
       3: 
       4: 
       5: def fn():
       6:     print(r)
    -->7:     global r
              ^

    Vous avez utilisé la variable `r`
    avant de la déclarer comme une variable globale.
    

Name used prior to nonlocal declaration
---------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_name_before_nonlocal_1.py", line 9
        nonlocal q
        ^
    SyntaxError: name 'q' is used prior to nonlocal declaration
    
        Avez-vous oublié d’ajouter `nonlocal` en premier ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_name_before_nonlocal_1.py'
    jusqu'à l'endroit indiqué par ^.
    
        5:     q = 1
        6: 
        7:     def g():
        8:         print(q)
    --> 9:         nonlocal q
                   ^

    Vous avez utilisé la variable `q`
    avant de la déclarer comme variable non locale.
    

Name assigned prior to nonlocal declaration
-------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_name_before_nonlocal_2.py", line 9
        nonlocal s
        ^
    SyntaxError: name 's' is assigned to before nonlocal declaration
    
        Avez-vous oublié d’ajouter `nonlocal` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_name_before_nonlocal_2.py'
    jusqu'à l'endroit indiqué par ^.
    
        5:     s = 1
        6: 
        7:     def g():
        8:         s = 2
    --> 9:         nonlocal s
                   ^

    Vous avez attribué une valeur à la variable `s`
    avant de la déclarer comme variable non locale.
    

Assign to conditional expression
--------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_to_conditional.py", line 3
        a if 1 else b = 1
        ^
    SyntaxError: cannot assign to conditional expression
    
        Vous ne pouvez assigner des objets qu’à des identifiants (noms de variables).
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_to_conditional.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: can't [cannot] assign to conditional expression"""
       2: 
    -->3: a if 1 else b = 1
          ^

    Du côté gauche d'un signe d'égalité, vous avez une
    expression conditionnelle au lieu du nom d'une variable.
    Une expression conditionnelle doit avoir la forme suivante:
    
        variable = objet if condition else autre_objet

Assignment to keyword (__debug__)
---------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_to_debug.py", line 4
        __debug__ = 1
        ^
    SyntaxError: cannot assign to __debug__
    
        Vous ne pouvez pas attribuer une valeur à `__debug__`.
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_to_debug.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: cannot assign to __debug__ in Py 3.8
       2:    and assignment to keyword before."""
       3: 
    -->4: __debug__ = 1
          ^

    `__debug__` est une constante dans python; vous ne pouvez pas lui assigner une valeur.
    
    

Cannot assign to f-string
-------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_to_f_string.py", line 6
        f'{x}' = 42
        ^
    SyntaxError: cannot assign to f-string expression
    
        Vous ne pouvez assigner des objets qu’à des identifiants (noms de variables).
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_to_f_string.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise
       2: Python < 3.8: SyntaxError: can't assign to literal
       3: Python >= 3.8: SyntaxError: cannot assign to f-string expression
       4: """
       5: 
    -->6: f'{x}' = 42
          ^

    Vous avez écrit une expression qui a la chaine de
    caractères formatés `f'{x}'`
    du côté gauche du signe d'égalité.
    Une telle chaîne ne doit apparaître que du côté droit d'un signe d’égalité.
    

Cannot assign to function call: single = sign
---------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_to_function_call_1.py", line 6
        len('a') = 3
        ^
    SyntaxError: cannot assign to function call
    
        Vous ne pouvez assigner des objets qu’à des identifiants (noms de variables).
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_to_function_call_1.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: can't assign to function call
       2: 
       3: Python 3.8: SyntaxError: cannot assign to function call
       4: """
       5: 
    -->6: len('a') = 3
          ^

    Vous avez écrit une expression comme
    
        len('a') = 3
    
    où `len('a')`, à la gauche du signe d'égalité est soit l'invocation
    d'une fonction, ou inclus une telle invocation,
    et n'est pas simplement le nom d'une variable.
    

Cannot assign to function call: two = signs
-------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_to_function_call_2.py", line 6
        func(a, b=3) = 4
        ^
    SyntaxError: cannot assign to function call
    
        Vous ne pouvez assigner des objets qu’à des identifiants (noms de variables).
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_to_function_call_2.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: can't assign to function call
       2: 
       3: Python 3.8: SyntaxError: cannot assign to function call
       4: """
       5: 
    -->6: func(a, b=3) = 4
          ^

    Vous avez écrit une expression comme
    
        func(...) = une certaine valeur
    
    où `func(...)`, du côté gauche du signe d'égalité
    est une fonction et non le nom d’une variable.
    

Assign to generator expression
------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_to_generator.py", line 3
        (x for x in x) = 1
        ^
    SyntaxError: cannot assign to generator expression
    
        Vous ne pouvez assigner des objets qu’à des identifiants (noms de variables).
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_to_generator.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: can't [cannot] assign to generator expression"""
       2: 
    -->3: (x for x in x) = 1
          ^

    Du côté gauche d'un signe d'égalité, vous avez une
    expression génératrice au lieu du nom d'une variable.
    

Cannot assign to literal - 4
----------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_to_literal_dict.py", line 7
        {1 : 2, 2 : 4} = 5
        ^
    SyntaxError: cannot assign to dict display
    
        Vous ne pouvez assigner des objets qu’à des identifiants (noms de variables).
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_to_literal_dict.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError:
       2: Python 3.8: cannot assign to dict display
       3: Python 3.6, 3.7: can't assign to literal
       4: 
       5:  """
       6: 
    -->7: {1 : 2, 2 : 4} = 5
          ^

    Vous avez écrit une expression comme
    
        {1 : 2, 2 : 4} = 5
    où `{1 : 2, 2 : 4}`, du côté gauche du signe d'égalité
    est ou inclut un objet de type `dict`
    et n'est pas simplement le nom d'une variable.
    
    

Cannot assign to literal int
----------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_to_literal_int.py", line 3
        1 = a
        ^
    SyntaxError: cannot assign to literal
    
        Peut-être que vous vouliez plutôt écrire : `a = 1`
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_to_literal_int.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: can't assign to literal"""
       2: 
    -->3: 1 = a
          ^

    Vous avez écrit une expression comme
    
        1 = a
    où `1`, du côté gauche du signe d'égalité
    est ou inclut un objet de type `int`
    et n'est pas simplement le nom d'une variable.
    Peut-être que vous vouliez plutôt écrire :
    
        a = 1
    
    

Cannot assign to literal int - 2
--------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_to_literal_int_2.py", line 3
        1 = 2
        ^
    SyntaxError: cannot assign to literal
    
        Vous ne pouvez assigner des objets qu’à des identifiants (noms de variables).
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_to_literal_int_2.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: can't assign to literal"""
       2: 
    -->3: 1 = 2
          ^

    Vous avez écrit une expression comme
    
        1 = 2
    où `1`, du côté gauche du signe d'égalité
    est ou inclut un objet de type `int`
    et n'est pas simplement le nom d'une variable.
    
    

Cannot assign to literal - 5
----------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_to_literal_int_3.py", line 4
        1 = a = b
        ^
    SyntaxError: cannot assign to literal
    
        Vous ne pouvez assigner des objets qu’à des identifiants (noms de variables).
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_to_literal_int_3.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: can't assign to literal
       2: or (Python 3.8) cannot assign to literal"""
       3: 
    -->4: 1 = a = b
          ^

    Vous avez écrit une expression comme
    
        ... = nom_de_variable
    où `...`, du côté gauche du signe d'égalité
    est ou inclut un objet 
    et n'est pas simplement le nom d'une variable.
    
    

Cannot assign to literal - 3
----------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_to_literal_set.py", line 7
        {1, 2, 3} = 4
        ^
    SyntaxError: cannot assign to set display
    
        Vous ne pouvez assigner des objets qu’à des identifiants (noms de variables).
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_to_literal_set.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError:
       2: Python 3.8: cannot assign to set display
       3: Python 3.6, 3.7: can't assign to literal
       4: 
       5:  """
       6: 
    -->7: {1, 2, 3} = 4
          ^

    Vous avez écrit une expression comme
    
        {1, 2, 3} = 4
    où `{1, 2, 3}`, du côté gauche du signe d'égalité
    est ou inclut un objet de type `set`
    et n'est pas simplement le nom d'une variable.
    
    

Assign to keyword def
---------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_to_keyword_def.py", line 3
        def = 2
            ^
    SyntaxError: invalid syntax
    
        Les mots clés Python ne peuvent pas être utilisés comme identifiants (noms de variables).
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_to_keyword_def.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """ Should raise SyntaxError"""
       2: 
    -->3: def = 2
              ^

    Vous essayiez d’assigner une valeur au mot clé Python `def`.
    Ceci n’est pas permis.
    
    

Assign to keyword else
----------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_to_keyword_else.py", line 3
        else = 1
        ^
    SyntaxError: invalid syntax
    
        Les mots clés Python ne peuvent pas être utilisés comme identifiants (noms de variables).
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_to_keyword_else.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """ Should raise SyntaxError"""
       2: 
    -->3: else = 1
          ^

    Vous essayiez d’assigner une valeur au mot clé Python `else`.
    Ceci n’est pas permis.
    
    

Assignment to keyword (None)
----------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_to_keyword_none.py", line 4
        None = 1
        ^
    SyntaxError: cannot assign to None
    
        Vous ne pouvez pas attribuer une valeur à `None`.
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_to_keyword_none.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: cannot assign to None in Py 3.8
       2:    and can't assign to keyword before."""
       3: 
    -->4: None = 1
          ^

    `None` est une constante dans python; vous ne pouvez pas lui assigner une valeur.
    
    

Assign to math operation
------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\assign_to_operation.py", line 4
        a + 1 = 2
        ^
    SyntaxError: cannot assign to operator
    
        Vous ne pouvez assigner des objets qu’à des identifiants (noms de variables).
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\assign_to_operation.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: can't assign to operator
       2: or (Python 3.8) cannot assign to operator"""
       3: 
    -->4: a + 1 = 2
          ^

    Vous avez écrit une expression qui inclut des opérations mathématiques
    du côté gauche du signe d'égalité; ceci devrait être
    utilisé uniquement pour attribuer une valeur à une variable.
    

Walrus/Named assignment depending on Python version
---------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\augmented_assigment_with_true.py", line 4
        (True := 1)
         ^
    SyntaxError: cannot use assignment expressions with True
    
        Vous ne pouvez pas attribuer une valeur à `True`.
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\augmented_assigment_with_true.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax
       2: or (Python 3.8) cannot use named assignment with True"""
       3: 
    -->4: (True := 1)
           ^

    `True` est une constante dans python; vous ne pouvez pas lui assigner une valeur.
    
    

break outside loop
------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\break_outside_loop.py", line 4
        break
        ^
    SyntaxError: 'break' outside loop
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\break_outside_loop.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: 'break' outside loop"""
       2: 
       3: if True:
    -->4:     break
              ^

    Le mot-clé Python `break` ne peut être utilisé qu'à l'intérieur d'une boucle `for` ou à l'intérieur d'une boucle `while`.
    

Cannot use star operator
------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\cannot_use_star.py", line 3
        *a
        ^
    SyntaxError: can't use starred expression here
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\cannot_use_star.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: can't use starred expression here"""
       2: 
    -->3: *a
          ^

    L’opérateur astérisque `*` est interprété comme signifiant que
    le déballage itérable doit être utilisé pour attribuer un nom
    à chaque élément d’un itérable, ce qui n’a pas de sens ici.
    

Cannot use double star operator
-------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "<fstring>", line 1
        (**k)
         ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    '<fstring>'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: (**k)
           ^

    L’opérateur double astérisque, `**` est probablement interprété comme signifiant
    qu'un déballage de `dict` doit être utilisé ce qui n’a pas de sens ici.
    

Missing () for tuples in comprehension
--------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\comprehension_missing_tuple_paren.py", line 1
        x = [i, i**2 for i in range(10)]
                     ^
    SyntaxError: invalid syntax
    
        Avez-vous oublié d’ajouter des parenthèses ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\comprehension_missing_tuple_paren.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: x = [i, i**2 for i in range(10)]
                       ^

    Je suppose que vous écriviez une compréhension ou une expression génératrice
    et vous avez oublié d’inclure des parenthèses autour des tuples.
    Voici un exemple: au lieu d’écrire
    
        [i, i**2 for i in range(10)]
    
    vous auriez besoin d’écrire
    
        [(i, i**2) for i in range(10)]
    
    

Comprehension with condition (no else)
--------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\comprehension_with_condition_no_else.py", line 1
        a = [f(x) if condition for x in sequence]
                               ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\comprehension_with_condition_no_else.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: a = [f(x) if condition for x in sequence]
                                 ^

    Je suppose que vous écriviez une compréhension ou une expression génératrice
    et avez utiliser le mauvais ordre pour une condition.
    L'ordre correct dépend de la présence ou non d'une clause `else`.
    Par exemple, le bon ordre pour une compréhension de liste avec
    une condition est
    
        [f(x) if condition else autre for x in séquence]  # 'if' avant 'for'
    
    ou, s'il n'y a pas de `else`
    
        [f(x) pour x in séquence si condition]  # 'if' après 'for'
    
    

Comprehension with condition (with else)
----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\comprehension_with_condition_with_else.py", line 1
        a = [f(x) for x in sequence if condition else other]
                                                 ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\comprehension_with_condition_with_else.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: a = [f(x) for x in sequence if condition else other]
                                                   ^

    Je suppose que vous écriviez une compréhension ou une expression génératrice
    et avez utiliser le mauvais ordre pour une condition.
    L'ordre correct dépend de la présence ou non d'une clause `else`.
    Par exemple, le bon ordre pour une compréhension de liste avec
    une condition est
    
        [f(x) if condition else autre for x in séquence]  # 'if' avant 'for'
    
    ou, s'il n'y a pas de `else`
    
        [f(x) pour x in séquence si condition]  # 'if' après 'for'
    
    

continue outside loop
---------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\continue_outside_loop.py", line 4
        continue
        ^
    SyntaxError: 'continue' not properly in loop
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\continue_outside_loop.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: 'continue' outside loop"""
       2: 
       3: if True:
    -->4:     continue
              ^

    Le mot-clé Python `continue` ne peut être utilisé qu'à l'intérieur d'une boucle `for` ou à l'intérieur d'une boucle `while`.
    

Copy/paste from interpreter
---------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\copy_pasted_code.py", line 2
        >>> print("Hello World!")
        ^
    SyntaxError: invalid syntax
    
        Avez-vous utilisé le copier-coller ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\copy_pasted_code.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
    -->2: >>> print("Hello World!")
          ^

    On dirait que vous avez copié-collé le code d’un interprète interactif.
    L’invite Python, `>>>`, ne doit pas être incluse dans votre code.
    

Named arguments must follow bare *
----------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_bare_star_arg.py", line 4
        def f(*):
              ^
    SyntaxError: named arguments must follow bare *
    
        Avez-vous oublié d’ajouter quelque chose après `*` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_bare_star_arg.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: # SyntaxError: named arguments must follow bare *
       2: 
       3: 
    -->4: def f(*):
                ^

    En supposant que vous définissiez une fonction, vous avez besoin
    de remplacer `*` soit par `*arguments` ou
    par `*, argument=valeur`.
    

def: misused as code block
--------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_code_block.py", line 3
        def :
            ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_code_block.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: def :
              ^

    Vous vouliez définir une fonction, mais vous avez fait des erreurs de syntaxe.
    La syntaxe correct est :
    
        def nom ( ... ):
    

def: Keyword arg only once in function definition
-------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_duplicate_arg.py", line 4
        def f(aa=1, aa=2):
        ^
    SyntaxError: duplicate argument 'aa' in function definition
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_duplicate_arg.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: duplicate argument 'aa' in function definition"""
       2: 
       3: 
    -->4: def f(aa=1, aa=2):
          ^

    Vous avez défini une fonction répétant l'argument nommé
    
        aa
    deux fois; chaque argument nommé ne doit apparaître qu'une seule fois dans une définition de fonction.
    

Non-identifier as a function name
---------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_function_name_invalid.py", line 3
        def 2be():
            ^
    SyntaxError: invalid syntax
    
        Vous avez écrit un nom de fonction invalide.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_function_name_invalid.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: 
       2: 
    -->3: def 2be():
              ^

    Le nom d’une fonction doit être un identificateur Python valide,
    c’est-à-dire un nom qui commence par une lettre ou un caractère de soulignement, `_`,
    et qui ne contient que des lettres, des chiffres ou le caractère de soulignement.
    

Using a string as a function name
---------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_function_name_string.py", line 3
        def "function"():
            ^
    SyntaxError: invalid syntax
    
        Le nom d’une fonction doit être un identificateur Python valide,
        c’est-à-dire un nom qui commence par une lettre ou un caractère de soulignement, `_`,
        et qui ne contient que des lettres, des chiffres ou le caractère de soulignement.
        Vous avez essayé d’utiliser une chaîne de caractères comme nom de fonction.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_function_name_string.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: 
       2: 
    -->3: def "function"():
              ^

    Le nom d’une fonction doit être un identificateur Python valide,
    c’est-à-dire un nom qui commence par une lettre ou un caractère de soulignement, `_`,
    et qui ne contient que des lettres, des chiffres ou le caractère de soulignement.
    Vous avez essayé d’utiliser une chaîne de caractères comme nom de fonction.
    

def: keyword cannot be argument in def - 1
------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_keyword_as_arg_1.py", line 5
        def f(None=1):
              ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_keyword_as_arg_1.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax
       2: """
       3: 
       4: 
    -->5: def f(None=1):
                ^

    Vous avez tenté d'utiliser le mot clé Python `None` comme argument
    dans la définition d'une fonction où un identificateur
    (nom de variable) était attendu.
    

def: keyword cannot be argument in def - 2
------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_keyword_as_arg_2.py", line 5
        def f(x, True):
                 ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_keyword_as_arg_2.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax
       2: """
       3: 
       4: 
    -->5: def f(x, True):
                   ^

    Vous avez tenté d'utiliser le mot clé Python `True` comme argument
    dans la définition d'une fonction où un identificateur
    (nom de variable) était attendu.
    

def: keyword cannot be argument in def - 3
------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_keyword_as_arg_3.py", line 5
        def f(*None):
               ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_keyword_as_arg_3.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax
       2: """
       3: 
       4: 
    -->5: def f(*None):
                 ^

    Vous avez tenté d'utiliser le mot clé Python `None` comme argument
    dans la définition d'une fonction où un identificateur
    (nom de variable) était attendu.
    

def: keyword cannot be argument in def - 4
------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_keyword_as_arg_4.py", line 5
        def f(**None):
                ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_keyword_as_arg_4.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax
       2: """
       3: 
       4: 
    -->5: def f(**None):
                  ^

    Vous avez tenté d'utiliser le mot clé Python `None` comme argument
    dans la définition d'une fonction où un identificateur
    (nom de variable) était attendu.
    

def: Python keyword as function name
------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_keyword_as_name.py", line 3
        def pass():
            ^
    SyntaxError: invalid syntax
    
        Vous avez tenté d'utiliser le mot clé Python `{kwd}` comme nom de fonction.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_keyword_as_name.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: def pass():
              ^

    Vous avez tenté d'utiliser le mot clé Python `pass` comme nom de fonction.
    Ceci n’est pas permis.
    
    

def: missing comma between function args
----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_missing_comma.py", line 4
        def a(b, c d):
                   ^
    SyntaxError: invalid syntax
    
        Avez-vous oublié une virgule ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_missing_comma.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
       3: 
    -->4: def a(b, c d):
                     ^

    Python indique que l’erreur est causée par `d` écrit tout juste après `c`.
    Il est également possible que vous ayez oublié une virgule entre les éléments d'un tuple,
    ou entre les arguments d'une fonction, avant la position indiquée par ^.
    Peut-être que vous vouliez plutôt
    
        def a(b, c, d):
    

def: missing parentheses
------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_missing_parens.py", line 3
        def name:
                ^
    SyntaxError: invalid syntax
    
        Avez-vous oublié d’ajouter des parenthèses ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_missing_parens.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: def name:
                  ^

    Vous avez peut-être oublié d’inclure des parenthèses.
    Vous avez peut-être voulu écrire 
    
        def name():
    

def: missing function name
--------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_missing_name.py", line 3
        def ( arg )  :
            ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_missing_name.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: def ( arg )  :
              ^

    Vous avez oublié de nommer votre fonction.
    La syntaxe correct est :
    
        def nom ( ... ):
    

def: name is parameter and global
---------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_name_is_parameter_and_global.py", line 6
        global x
        ^
    SyntaxError: name 'x' is parameter and global
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_name_is_parameter_and_global.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: name 'x' is parameter and global
       2: """
       3: 
       4: 
       5: def f(x):
    -->6:     global x
              ^

    Vous avec inclus l'énoncé
    
            global x
    
    
    indiquant que `x` est une variable définie en dehors d'une fonction.
    Vous utilisez également le même `x` comme un argument pour cette
    fonction; un argument de fonction est une variable locale connue seulement
    à l'intérieur de cette fonction, ce qui est le contraire de ce que `global` sous-entendait.
    

def: non-default argument follows default argument
--------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_non_default_after_default.py", line 5
        def test(a=1, b):
                 ^
    SyntaxError: non-default argument follows default argument
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_non_default_after_default.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: non-default argument follows default argument
       2: """
       3: 
       4: 
    -->5: def test(a=1, b):
                   ^

    Dans Python, vous pouvez définir les fonctions avec seulement des arguments de position
    
        def test(a, b, c): ...
    
    ou seulement des arguments nommés
    
        def test(a=1, b=2, c=3): ...
    
    ou une combinaison des deux
    
        def test(a, b, c=3): ...
    
    mais avec les arguments nommés apparaissant après tous les arguments positionnels.
    Selon Python, vous avez utilisé des arguments positionnels après des arguments nommés.
    

Single number used as arg in function def
-----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_number_as_arg.py", line 1
        def f(1):
              ^
    SyntaxError: invalid syntax
    
        Vous ne pouvez pas utiliser un nombre comme argument de fonction.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_number_as_arg.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: def f(1):
                ^

    Vous avez utilisé un nombre comme argument lors de la définition d’une fonction.
    Vous ne pouvez utiliser que des identificateurs (noms de variables) comme arguments de fonction.
    

def: positional argument follows keyword argument
-------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_positional_after_keyword_arg.py", line 5
        test(a=1, b)
                  ^
    SyntaxError: positional argument follows keyword argument
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_positional_after_keyword_arg.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: positional argument follows keyword argument
       2: """
       3: 
       4: 
    -->5: test(a=1, b)
                    ^

    Dans Python, vous pouvez invoquer les fonctions avec seulement des arguments de position
    
        test(1, 2, 3)
    
    ou seulement des arguments nommés
    
        test (a=1, b=2, c=3)
    
    ou une combinaison des deux
    
        test(1, 2, c=3)
    
    mais avec les arguments nommés apparaissant après tous les arguments positionnels.
    Selon Python, vous avez utilisé des arguments positionnels après des arguments nommés.
    

Single string used as arg in function def
-----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_string_as_arg.py", line 1
        def f("1"):
              ^
    SyntaxError: invalid syntax
    
        Vous ne pouvez pas utiliser les chaînes comme arguments de fonction.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_string_as_arg.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: def f("1"):
                ^

    Vous avez utilisé une chaîne comme argument lors de la définition d’une fonction.
    Vous ne pouvez utiliser que des identificateurs (noms de variables) comme arguments de fonction.
    

def: tuple as function argument
-------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_tuple_as_arg_1.py", line 1
        def test((a, b), c):
                 ^
    SyntaxError: invalid syntax
    
        Vous ne pouvez pas avoir des tuples explicites comme arguments de fonction.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_tuple_as_arg_1.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: def test((a, b), c):
                   ^

    Vous ne pouvez pas avoir des tuples explicites comme arguments de fonction.
    Vous ne pouvez utiliser que des identifiants (noms de variables) comme arguments de fonction.
    Assignez n’importe quel tuple à un paramètre et dépaquetez-le
    dans le corps de la fonction.
    

def: tuple as function argument - 2
-----------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\def_tuple_as_arg_2.py", line 1
        def test(a, (b, c)):
                    ^
    SyntaxError: invalid syntax
    
        Vous ne pouvez pas avoir des tuples explicites comme arguments de fonction.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\def_tuple_as_arg_2.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: def test(a, (b, c)):
                      ^

    Vous ne pouvez pas avoir des tuples explicites comme arguments de fonction.
    Vous ne pouvez utiliser que des identifiants (noms de variables) comme arguments de fonction.
    Assignez n’importe quel tuple à un paramètre et dépaquetez-le
    dans le corps de la fonction.
    

Deleting constant/keyword
-------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\delete_constant_keyword.py", line 1
        del True
            ^
    SyntaxError: cannot delete True
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\delete_constant_keyword.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: del True
              ^

    Vous ne pouvez pas supprimer la constante `True`.
    

Cannot delete function call
---------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\delete_function_call.py", line 5
        del f(a)
            ^
    SyntaxError: cannot delete function call
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\delete_function_call.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: can't or cannot delete function call
       2: """
       3: 
       4: 
    -->5: del f(a)
              ^

    Vous avez tenté de supprimer un appel de fonction
    
        del f(a)
    au lieu de supprimer le nom de la fonction
    
        del f
    

Deleting string literal
-----------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\delete_string_literal.py", line 1
        del "Hello world!"
            ^
    SyntaxError: cannot delete literal
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\delete_string_literal.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: del "Hello world!"
              ^

    Vous ne pouvez pas supprimer le littéral `"Hello world!"`.
    Vous ne pouvez supprimer que les noms d’objets, ou
    des items individuels dans un conteneur.
    

Dot followed by parenthesis
---------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\dot_before_paren.py", line 3
        print(len.('hello'))
                  ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\dot_before_paren.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax
       2: Reported by Hackinscience."""
    -->3: print(len.('hello'))
                    ^

    Vous ne pouvez pas avoir un point `.` suivi de `(`.
    Peut-être que vous devez remplacer le point par une virgule.
    

Write elif, not else if
-----------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\else_if_instead_of_elif.py", line 5
        else if True:
             ^
    SyntaxError: invalid syntax
    
        Peut-être que vous vouliez plutôt `elif`.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\else_if_instead_of_elif.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError"""
       2: 
       3: if False:
       4:     pass
    -->5: else if True:
               ^

    Vous avez écrit `else if`
    au lieu d'utiliser le mot-clé `elif`.
    
    

Write elif, not elseif
----------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\elseif_instead_of_elif.py", line 5
        elseif True:
               ^
    SyntaxError: invalid syntax
    
        Peut-être que vous vouliez plutôt `elif`.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\elseif_instead_of_elif.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError"""
       2: 
       3: if False:
       4:     pass
    -->5: elseif True:
                 ^

    Vous avez écrit `elseif`
    au lieu d'utiliser le mot-clé `elif`.
    
    

EOL while scanning string literal
---------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\eol_string_literal.py", line 3
        alphabet = 'abc
                       ^
    SyntaxError: EOL while scanning string literal
    
        Avez-vous oublié d’ajouter un guillemet ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\eol_string_literal.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: EOL while scanning string literal"""
       2: 
    -->3: alphabet = 'abc
                         ^

    Vous aviez commencé à écrire une chaîne de caractères
    avec un guillemet simple ou double, mais n'avez jamais
    terminé la chaîne avec un autre guillemet sur cette ligne.
    

Used equal sign instead of colon
--------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\equal_sign_instead_of_colon.py", line 4
        ages = {'Alice'=22, 'Bob'=24}
                       ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\equal_sign_instead_of_colon.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax
       2: """
       3: 
    -->4: ages = {'Alice'=22, 'Bob'=24}
                         ^

    Il est possible que vous ayez utilisé un signe d'égalité `=` au lieu de deux points `:`
    pour attribuer des valeurs à une clé d'un dictionnaire
    avant ou exactement à la position indiquée par ^.
    

Parens around multiple exceptions
---------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\except_multiple_exceptions.py", line 3
        except NameError, ValueError as err:
                        ^
    SyntaxError: invalid syntax
    
        Avez-vous oublié d’ajouter des parenthèses ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\except_multiple_exceptions.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: try:
       2:     pass
    -->3: except NameError, ValueError as err:
                          ^

    Je suppose que vous vouliez utiliser un énoncé `except`
    avec plusieurs types d’exception. Si c’est le cas, vous devez
    les entourer de parenthèses.
    
    Si vous utilisez une console Friendly, vous pouvez
    utiliser la fonction `www()` qui ouvrira un navigateur à
    une place pertinente dans la documentation Python.
    

Binary f-string not allowed
---------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\f_string_binary.py", line 1
        greet = bf"Hello {name}"
                  ^
    SyntaxError: invalid syntax
    
        `bf` est un préfixe de chaîne illégal.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\f_string_binary.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: greet = bf"Hello {name}"
                    ^

    Je devine que vous vouliez une chaîne "f-string" binaire;
    ceci n’est pas permis.
    

f-string: unterminated string
-----------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\f_string_unterminated.py", line 4
        print(f"Bob is {age['Bob]} years old.")
              ^
    SyntaxError: f-string: unterminated string
    
        Avez-vous oublié d’ajouter un guillemet ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\f_string_unterminated.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: f-string: unterminated string
       2: """
       3: 
    -->4: print(f"Bob is {age['Bob]} years old.")
                ^

    À l'intérieur de la chaîne `f"Bob is {age['Bob]} years old."`, qui est une chaîne de caractères préfixée de la lettre f,
    vous avez une autre chaîne de caractère qui débute soit avec un apostrophe (')
    ou des guillemets ("), mais n'est pas terminé par un autre caractère semblable.
    

f-string with backslash
-----------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\f_string_with_backslash.py", line 2
        print(f"{'\n'.join(names)}")
              ^
    SyntaxError: f-string expression part cannot include a backslash
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\f_string_with_backslash.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: names = ['a', 'b']
    -->2: print(f"{'\n'.join(names)}")
                ^

    Vous avez écrit une chaîne de caractères formatés dont le contenu `{...}`
    comprend une barre oblique inverse; ce n’est pas permis.
    Peut-être pouvez-vous remplacer la partie qui contient une barre oblique inverse par
    une variable. Par exemple, supposons que vous avez une chaîne comme suit :
    
        f"{... 'bonjour\n'...}"
    
    vous pourriez écrire ceci comme
    
        bonjour = 'bonjour\n'
        f"{... bonjour ...}"
    

Not a chance!
-------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\future_braces.py", line 1
        from __future__ import braces
        ^
    SyntaxError: not a chance
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\future_braces.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: from __future__ import braces
          ^

    Je soupçonne que vous avez écrit `from __future__ import braces`
    suivant une suggestion de quelqu’un d’autre. Ça ne marchera jamais.
    
    Contrairement à d’autres langages de programmation, les blocs de code Python sont définis par
    leur niveau d’indentation, et non pas en utilisant des accolades, comme `{...}`.
    

Do not import * from __future__
-------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\future_import_star.py", line 1
        from __future__ import *
        ^
    SyntaxError: future feature * is not defined
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\future_import_star.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: from __future__ import *
          ^

    Lors de l’utilisation d’un énoncé `from __future__ import`,
    vous devez importer des noms spécifiques.
    
    Les valeurs disponibles sont `nested_scopes,
     generators,
     division,
     absolute_import,
     with_statement,
     print_function,
     unicode_literals,
     barry_as_FLUFL,
     generator_stop,
     annotations`.
    

__future__ at beginning
-----------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\future_must_be_first.py", line 3
        from __future__ import generators
        ^
    SyntaxError: from __future__ imports must occur at the beginning of the file
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\future_must_be_first.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: 
       2: def fn():
    -->3:     from __future__ import generators
              ^

    Une instruction `from __future__ import` change la façon dont Python
    interprète le code dans un fichier.
    Une telle instruction doit apparaître au début du fichier.

Typo in __future__
------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\future_typo.py", line 1
        from __future__ import divisio
        ^
    SyntaxError: future feature divisio is not defined
    
        Vouliez-vous dire `division` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\future_typo.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: from __future__ import divisio
          ^

    Au lieu de `divisio`, peut-être que vous vouliez plutôt importer `division`.
    

Unknown feature in __future__
-----------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\future_unknown.py", line 1
        from __future__ import something
        ^
    SyntaxError: future feature something is not defined
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\future_unknown.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: from __future__ import something
          ^

    `something` n’est pas un attribut valide du module `__future__`.
    
    Les valeurs disponibles sont `nested_scopes,
     generators,
     division,
     absolute_import,
     with_statement,
     print_function,
     unicode_literals,
     barry_as_FLUFL,
     generator_stop,
     annotations`.
    

Parenthesis around generator expression
---------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\generator_expression_parens.py", line 6
        f(x for x in L, 1)
          ^
    SyntaxError: Generator expression must be parenthesized
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\generator_expression_parens.py'
    jusqu'à l'endroit indiqué par ^.
    
       2: def f(it, *varargs, **kwargs):
       3:     return list(it)
       4: 
       5: L = range(10)
    -->6: f(x for x in L, 1)
            ^

    Vous utilisez une expression de générateur, quelque chose de la forme
    
        x for x in objet
    
    Vous devez ajouter des parenthèses qui entourent cette expression.
    

Space between names
-------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\hyphen_instead_of_underscore.py", line 4
        a-b = 2
        ^
    SyntaxError: cannot assign to operator
    
        Vouliez-vous dire `a_b` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\hyphen_instead_of_underscore.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: can't assign to operator
       2: or (Python 3.8) cannot assign to operator"""
       3: 
    -->4: a-b = 2
          ^

    Vous avez écrit une expression qui inclut des opérations mathématiques
    du côté gauche du signe d'égalité; ceci devrait être
    utilisé uniquement pour attribuer une valeur à une variable.
    Peut-être que vous vouliez plutôt écrire `a_b` au lieu de `a-b`.
    

use j instead of i
------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\imaginary_i.py", line 3
        a = 3.0i
               ^
    SyntaxError: invalid syntax
    
        Vouliez-vous dire `3.0j` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\imaginary_i.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: # SyntaxError: invalid syntax
       2: 
    -->3: a = 3.0i
                 ^

    Les noms valides ne peuvent pas commencer par un chiffre.
    Peut-être pensiez-vous que `i` pouvait être utilisé pour représenter
    la racine carrée de `-1`. Dans Python, le symbole utilisé pour ceci est `j`
    et la partie imaginaire d'un nombre complexe a la forme `nombre`
    suivie immédiatement par `j` sans aucun espace entre les deux.
    Peut-être que vous vouliez écrire `3.0j`.
    

Import inversion: import X from Y
---------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\import_from.py", line 3
        import pen from turtle
                   ^
    SyntaxError: invalid syntax
    
        Vouliez-vous dire `from turtle import pen` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\import_from.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: import pen from turtle
                     ^

    Vous avez écrit quelque chose comme
        import pen from turtle
    au lieu de
        from turtle import pen
    
    

IndentationError: expected an indented block
--------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\indentation_error_1.py", line 4
        pass
        ^
    IndentationError: expected an indented block
    
    Une exception de type `IndentationError` se produit lorsqu'une ligne de code
    n'est pas indentée (c'est-à-dire alignée verticalement avec les autres lignes)
    de la façon attendue.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\indentation_error_1.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: '''Should raise IndentationError'''
       2: 
       3: if True:
    -->4: pass
          ^

    La ligne indiquée ci-dessus par --> devrait
    normalement commencer un nouveau bloc de code indenté.
    

IndentationError: unexpected indent
-----------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\indentation_error_2.py", line 4
        pass
       ^
    IndentationError: unexpected indent
    
    Une exception de type `IndentationError` se produit lorsqu'une ligne de code
    n'est pas indentée (c'est-à-dire alignée verticalement avec les autres lignes)
    de la façon attendue.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\indentation_error_2.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: '''Should raise IndentationError'''
       2: if True:
       3:     pass
    -->4:       pass
               ^

    La ligne indiquée ci-dessus par --> est plus indentée que prévu.
    

IndentationError: unindent does not match ...
---------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\indentation_error_3.py", line 5
        pass
            ^
    IndentationError: unindent does not match any outer indentation level
    
    Une exception de type `IndentationError` se produit lorsqu'une ligne de code
    n'est pas indentée (c'est-à-dire alignée verticalement avec les autres lignes)
    de la façon attendue.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\indentation_error_3.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: '''Should raise IndentationError'''
       2: 
       3: if True:
       4:       pass
    -->5:     pass
                  ^

    La ligne indiquée ci-dessus par --> est moins indentée que prévu.
    

IndentationError: missing continuation line
-------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\indentation_error_4.py", line 6
        "c"
       ^
    IndentationError: unexpected indent
    
    Une exception de type `IndentationError` se produit lorsqu'une ligne de code
    n'est pas indentée (c'est-à-dire alignée verticalement avec les autres lignes)
    de la façon attendue.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\indentation_error_4.py'
    jusqu'à l'endroit indiqué par ^.
    
       2: 
       3: def f():
       4:      s = "a"\
       5:          "b"
    -->6:          "c"
                  ^

    La ligne indiquée ci-dessus par --> est plus indentée que prévu.
    
    Toutefois, la ligne 6, qui est identifiée comme ayant un problème,
    se compose d’une seule chaîne, ce qui est également le cas
    pour la ligne précédente.
    Peut-être que vous vouliez inclure un caractère de continuation, '\',
    à la fin de la ligne 5.
    

Forgot 'o' for octal
--------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\integer_with_leading_zero_1.py", line 1
        x = 01
             ^
    SyntaxError: leading zeros in decimal integer literals are not permitted; use an 0o prefix for octal integers
    
        Vouliez-vous dire `0o1` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\integer_with_leading_zero_1.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: x = 01
               ^

    Peut-être que vous vouliez écrire le nombre octal `0o1`
    et oublié la lettre 'o', ou peut-être vous vouliez écrire
    un entier décimal et ne saviez pas qu’il ne pouvait pas commencer par des zéros.
    

Integer with leading zeros
--------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\integer_with_leading_zero_2.py", line 1
        x = 000_123_456
                      ^
    SyntaxError: leading zeros in decimal integer literals are not permitted; use an 0o prefix for octal integers
    
        Vouliez-vous dire `123_456` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\integer_with_leading_zero_2.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: x = 000_123_456
                        ^

    Peut-être que vous vouliez écrire l'entier décimal `123_456`
    et ne saviez pas qu’il ne pouvait pas commencer par des zéros.
    

Invalid character in identifier
-------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\invalid_character_in_identifier.py", line 6
        🤖 = 'Reeborg'
        ^
    SyntaxError: invalid character in identifier
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\invalid_character_in_identifier.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid character in identifier
       2: """
       3: 
       4: # Robot-face character below
       5: 
    -->6: 🤖 = 'Reeborg'
          ^

    Python indique que vous avez utilisé le caractère unicode `🤖`
    ce qui n’est pas permis.
    

Invalid hexadecimal number
--------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\invalid_hexadecimal.py", line 3
        a = 0x123g4
                 ^
    SyntaxError: invalid syntax
    
        Avez-vous fait une erreur en écrivant un entier hexadécimal ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\invalid_hexadecimal.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: a = 0x123g4
                   ^

    On dirait que vous avez utilisé un caractère invalide ('g') dans un nombre hexadecimal.
    
    Les nombres hexadécimaux sont des entiers en base 16 qui utilisent les symboles `0` à `9`
    pour représenter les valeurs 0 à 9, et les lettres `a` à `f` (ou `A` à `F`)
    pour représenter les valeurs 10 à 15.
    Dans Python, les nombres hexadécimaux commencent par `0x` ou `0X`,
    suivi des caractères utilisés pour représenter la valeur du nombre.
    

Valid names cannot begin with a number
--------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\invalid_identifier.py", line 3
        36abc = 3
          ^
    SyntaxError: invalid syntax
    
        Les noms valides ne peuvent pas commencer par un chiffre.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\invalid_identifier.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: 36abc = 3
            ^

    Les noms valides ne peuvent pas commencer par un chiffre.
    

Forgot a multiplication operator
--------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\invalid_identifier_2.py", line 3
        tau = 2pi
               ^
    SyntaxError: invalid syntax
    
        Peut-être avez-vous oublié un opérateur de multiplication, `2 * pi`.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\invalid_identifier_2.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: tau = 2pi
                 ^

    Les noms valides ne peuvent pas commencer par un chiffre.
    Peut-être avez-vous oublié un opérateur de multiplication, `2 * pi`.
    
    

Keyword can't be an expression
------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\invalid_keyword_argument.py", line 7
        a = dict('key'=1)
                 ^
    SyntaxError: expression cannot contain assignment, perhaps you meant "=="?
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\invalid_keyword_argument.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise
       2: Python < 3.8: SyntaxError: keyword can't be an expression
       3: Python 3.8:  expression cannot contain assignment, perhaps you meant "=="?
       4: """
       5: 
       6: 
    -->7: a = dict('key'=1)
                   ^

    L'une des deux possibilités suivantes pourrait être la cause:
    
    1. Vous vouliez faire une comparaison avec `==` et vous avez écrit `=` à sa place.
    2. Vous avez invoqué une fonction avec un argument nommé:
    
            une_fonction (invalide=...)
    
    où `invalide` n'est pas un identifiant (nom de variable) valide dans Python
    soit parce qu'il commence par un chiffre, soit qu'il est une chaîne,
    ou qu'il contient un point, etc.
    
    

Invalid octal number
--------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\invalid_octal.py", line 3
        b = 0O1876
               ^
    SyntaxError: invalid digit '8' in octal literal
    
        Avez-vous fait une erreur en écrivant un entier octal ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\invalid_octal.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: 
       2: 
    -->3: b = 0O1876
                 ^

    On dirait que vous avez utilisé un caractère invalide ('8') dans un nombre octal.
    
    Les nombres octaux sont des entiers de base 8 qui n’utilisent que les symboles `0` à `7`
    pour représenter les valeurs.
    Dans Python, les nombres octaux commencent par `0o` ou `0O`,
    (le chiffre zéro suivi de la lettre `o`)
    suivi des caractères utilisés pour représenter la valeur de cet entier.
    

Keyword arg only once in function call
--------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\keyword_arg_repeated.py", line 4
        f(ad=1, ad=2)
                ^
    SyntaxError: keyword argument repeated
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\keyword_arg_repeated.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError:  keyword argument repeated"""
       2: 
       3: 
    -->4: f(ad=1, ad=2)
                  ^

    Vous avez invoqué une fonction en répétant le même argument nommé (`ad`).
    Chaque argument de ce type ne peut apparaître qu'une seule fois.
    

Keyword as attribute
--------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\keyword_as_attribute.py", line 12
        a.pass = 2
          ^
    SyntaxError: invalid syntax
    
        `pass` ne peut pas être utilisé comme n attribut.
        
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\keyword_as_attribute.py'
    jusqu'à l'endroit indiqué par ^.
    
        8: 
        9: a = A()
       10: 
       11: a.x = 1
    -->12: a.pass = 2
             ^

    Vous avez tenté d'utiliser le mot clé Python `pass` comme attribut.
    Ceci n’est pas permis.
    
    

lambda with parentheses around arguments
----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\lambda_with_parens.py", line 2
        x = lambda (a, b): a + b
                   ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\lambda_with_parens.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: 
    -->2: x = lambda (a, b): a + b
                     ^

    `lambda` ne permet pas de parenthèses autour de ses arguments.
    Cela était permis dans Python 2, mais il ne l'est plus dans Python 3.
    

lambda with tuple as argument
-----------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\lambda_with_tuple_argument.py", line 2
        x = lambda a, (b, c): a + b + b
                      ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\lambda_with_tuple_argument.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: 
    -->2: x = lambda a, (b, c): a + b + b
                        ^

    Vous ne pouvez pas avoir des tuples explicites comme arguments.
    Attribuez n’importe quel tuple à un paramètre et dépaquetez-le
    dans le corps de la fonction.
    

IndentationError/SyntaxError depending on version
-------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\missing_code_block.py", line 4
    SyntaxError: unexpected EOF while parsing
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\missing_code_block.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: '''Should raise SyntaxError: unexpected EOF while parsing'''
       2: 
       3: for i in range(10):
    -->4: 
          ^

    Python nous dit qu'il a atteint la fin du fichier
    et s'attendait à plus de contenu.
    
    

Missing colon - if
------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\missing_colon_if.py", line 3
        if True
               ^
    SyntaxError: invalid syntax
    
        Avez-vous oublié d’ajouter les deux points `:` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\missing_colon_if.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: if True
                 ^

    Vous avez écrit un énoncé débutant avec
    `if` mais vous avez oublié d’ajouter deux points `:` à la fin.
    
    

Missing colon - while
---------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\missing_colon_while.py", line 3
        while True  # a comment
                    ^
    SyntaxError: invalid syntax
    
        Avez-vous oublié d’ajouter les deux points `:` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\missing_colon_while.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: while True  # a comment
                      ^

    Vous vouliez débuter une boucle `while`
    mais vous avez oublié d’ajouter deux points `:` à la fin.
    
    

Missing comma in a dict
-----------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\missing_comma_in_dict.py", line 5
        'c': 3,
        ^
    SyntaxError: invalid syntax
    
        Avez-vous oublié une virgule ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\missing_comma_in_dict.py'
    jusqu'à l'endroit indiqué par ^.
    
       2: 
       3: a = {'a': 1,
       4:      'b': 2
    -->5:      'c': 3,
               ^
       6: }

    Python indique que l’erreur est causée par `'c'` écrit tout juste après `2`.
    Il est également possible que vous ayez oublié une virgule entre les éléments d'un ensemble (set)
    ou un dict avant la position indiquée par ^.
    Peut-être que vous vouliez plutôt
    
        a = {'a': 1,
     'b': 2,
     'c': 3,
    }
    

Missing comma in a list
-----------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\missing_comma_in_list.py", line 3
        a = [1, 2  3]
                   ^
    SyntaxError: invalid syntax
    
        Avez-vous oublié quelque chose entre `2` et `3` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\missing_comma_in_list.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: a = [1, 2  3]
                     ^

    Python indique que l’erreur est causée par `3` écrit tout juste après `2`.
    Il est également possible que vous ayez oublié une virgule entre les éléments d'une liste
    avant la position indiquée par ^.
    Peut-être que vous vouliez insérer un opérateur comme `+, -, *`
    entre `2` et `3`.
    Les lignes de code suivantes ne causeraient pas des `SyntaxError :
    
        a = [1, 2,  3]
        a = [1, 2 +  3]
        a = [1, 2 -  3]
        a = [1, 2 *  3]
    Remarque : ce ne sont là que quelques-uns des choix possibles et
    certains d’entre eux pourraient soulever d’autres types d’exceptions.
    

Missing comma in a set
----------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\missing_comma_in_set.py", line 3
        a = {1, 2  3}
                   ^
    SyntaxError: invalid syntax
    
        Avez-vous oublié quelque chose entre `2` et `3` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\missing_comma_in_set.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: a = {1, 2  3}
                     ^

    Python indique que l’erreur est causée par `3` écrit tout juste après `2`.
    Il est également possible que vous ayez oublié une virgule entre les éléments d'un ensemble (set)
    ou un dict avant la position indiquée par ^.
    Peut-être que vous vouliez insérer un opérateur comme `+, -, *`
    entre `2` et `3`.
    Les lignes de code suivantes ne causeraient pas des `SyntaxError :
    
        a = {1, 2,  3}
        a = {1, 2 +  3}
        a = {1, 2 -  3}
        a = {1, 2 *  3}
    Remarque : ce ne sont là que quelques-uns des choix possibles et
    certains d’entre eux pourraient soulever d’autres types d’exceptions.
    

Missing comma in a tuple
------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\missing_comma_in_tuple.py", line 3
        a = (1, 2  3)
                   ^
    SyntaxError: invalid syntax
    
        Avez-vous oublié quelque chose entre `2` et `3` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\missing_comma_in_tuple.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: a = (1, 2  3)
                     ^

    Python indique que l’erreur est causée par `3` écrit tout juste après `2`.
    Il est également possible que vous ayez oublié une virgule entre les éléments d'un tuple,
    ou entre les arguments d'une fonction, avant la position indiquée par ^.
    Peut-être que vous vouliez insérer un opérateur comme `+, -, *`
    entre `2` et `3`.
    Les lignes de code suivantes ne causeraient pas des `SyntaxError :
    
        a = (1, 2,  3)
        a = (1, 2 +  3)
        a = (1, 2 -  3)
        a = (1, 2 *  3)
    Remarque : ce ne sont là que quelques-uns des choix possibles et
    certains d’entre eux pourraient soulever d’autres types d’exceptions.
    

Name is global and nonlocal
---------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\name_is_global_and_nonlocal.py", line 7
        global xy
        ^
    SyntaxError: name 'xy' is nonlocal and global
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\name_is_global_and_nonlocal.py'
    jusqu'à l'endroit indiqué par ^.
    
       3: xy = 1
       4: 
       5: 
       6: def f():
    -->7:     global xy
              ^

    Vous avez utilisé `xy` comme étant une variable non locale et globale.
    Une variable peut être d'un seul type à la fois: soit globale, soit non locale, ou soit locale.
    

Name is parameter and nonlocal
------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\name_is_param_and_nonlocal.py", line 5
        nonlocal x
        ^
    SyntaxError: name 'x' is parameter and nonlocal
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\name_is_param_and_nonlocal.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: name 'x' is parameter and nonlocal"""
       2: 
       3: 
       4: def f(x):
    -->5:     nonlocal x
              ^

    Vous avez utilisé `x` comme paramètre pour une fonction
    avant de la déclarer également comme une variable non locale :
    `x` ne peut pas être les deux en même temps.
    

nonlocal variable not found
---------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\no_binding_for_nonlocal.py", line 5
        nonlocal ab
        ^
    SyntaxError: no binding for nonlocal 'ab' found
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\no_binding_for_nonlocal.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: no binding for nonlocal 'ab' found"""
       2: 
       3: 
       4: def f():
    -->5:     nonlocal ab
              ^

    Vous avez déclaré la variable `ab` comme non locale
    mais elle n'existe pas ailleurs.
    

nonlocal variable not found at module level
-------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\nonlocal_at_module.py", line 4
        nonlocal cd
        ^
    SyntaxError: nonlocal declaration not allowed at module level
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\nonlocal_at_module.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError:  nonlocal declaration not allowed at module level"""
       2: 
       3: 
    -->4: nonlocal cd
          ^

    Vous avez utilisé le mot clé nonlocal au niveau d'un module.
    Le mot clé nonlocal fait référence à une variable à l'intérieur d'une fonction
    qui a une valeur attribuée à l'extérieur de cette fonction.

Using pip from interpreter
--------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\pip_install_1.py", line 2
        pip install friendly
            ^
    SyntaxError: invalid syntax
    
        Pip ne peut pas être utilisé dans un interprète Python.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\pip_install_1.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
    -->2: pip install friendly
              ^

    Il semble que vous essayez d’utiliser pip pour installer un module.
    `pip` est une commande qui doit être invoquée dans un terminal,
    pas dans un interprète Python.
    

Using pip from interpreter 2
----------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\pip_install_2.py", line 2
        python -m pip install friendly
                  ^
    SyntaxError: invalid syntax
    
        Pip ne peut pas être utilisé dans un interprète Python.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\pip_install_2.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
    -->2: python -m pip install friendly
                    ^

    Il semble que vous essayez d’utiliser pip pour installer un module.
    `pip` est une commande qui doit être invoquée dans un terminal,
    pas dans un interprète Python.
    

print is a function
-------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\print_is_a_function.py", line 2
        print 'hello'
              ^
    SyntaxError: Missing parentheses in call to 'print'. Did you mean print('hello')?
    
        Vouliez-vous dire `print('hello')` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\print_is_a_function.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: Missing parentheses in call to 'print' ..."""
    -->2: print 'hello'
                ^

    Peut-être que vous avez besoin d'écrire
    
         print('hello')
    
    Dans l'ancienne version de Python, `print` était un mot clé.
    Maintenant, `print` est une fonction; vous devez utiliser des parenthèses pour l'invoquer.
    

print is a function 2
---------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\print_is_a_function_2.py", line 2
        print len('hello')
              ^
    SyntaxError: invalid syntax
    
        Vouliez-vous dire `print(len('hello'))` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\print_is_a_function_2.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
    -->2: print len('hello')
                ^

    Dans l'ancienne version de Python, `print` était un mot clé.
    Maintenant, `print` est une fonction; vous devez utiliser des parenthèses pour l'invoquer.
    

Quote inside a string
---------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\quote_inside_string.py", line 3
        message = 'don't'
                       ^
    SyntaxError: invalid syntax
    
        Vous avez peut-être un guillemet écrit au mauvais endroit.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\quote_inside_string.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: message = 'don't'
                         ^

    Il semble y avoir un identificateur Python (nom de variable)
    immédiatement après une chaîne.
    Je soupçonne que vous essayiez d'utiliser un apostrophe ou un guillemet
    à l'intérieur d'une chaîne qui était délimitée par ces mêmes caractères.
    

Raising multiple exceptions
---------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\raise_multiple_exceptions.py", line 2
        raise X, Y
               ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_multiple_exceptions.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
    -->2: raise X, Y
                 ^

    Je crois que vous essayez de lever une exception en utilisant la syntaxe de Python 2.
    

Cannot use return outside function
----------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\return_outside_function.py", line 3
        return
        ^
    SyntaxError: 'return' outside function
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\return_outside_function.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: 'return' outside function"""
       2: 
    -->3: return
          ^

    Vous ne pouvez utiliser un énoncé `return` qu'à l’intérieur d’une fonction ou d’une méthode.
    

Single = instead of double == with if
-------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\single_equal_with_if.py", line 3
        if i % 2 = 0:
                 ^
    SyntaxError: invalid syntax
    
        Peut-être que vous aviez besoin de `==` ou `:=` au lieu de `=`.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\single_equal_with_if.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: for i in range(101):
    -->3:     if i % 2 = 0:
                       ^

    Vous avez utilisé un opérateur d’affectation `=`; vous vouliez peut-être utiliser 
    un opérateur d'égalité, `==`, ou l'opérateur `:=`.
    

Single = instead of double == with elif
---------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\single_equal_with_elif.py", line 5
        elif i % 2 = 0:
                   ^
    SyntaxError: invalid syntax
    
        Peut-être que vous aviez besoin de `==` ou `:=` au lieu de `=`.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\single_equal_with_elif.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: for i in range(101):
       3:     if False:
       4:         pass
    -->5:     elif i % 2 = 0:
                         ^

    Vous avez utilisé un opérateur d’affectation `=`; vous vouliez peut-être utiliser 
    un opérateur d'égalité, `==`, ou l'opérateur `:=`.
    

Single = instead of double == with while
----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\single_equal_with_while.py", line 4
        while a = 1:
                ^
    SyntaxError: invalid syntax
    
        Peut-être que vous aviez besoin de `==` ou `:=` au lieu de `=`.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\single_equal_with_while.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: a = 1
       3: 
    -->4: while a = 1:
                  ^

    Vous avez utilisé un opérateur d’affectation `=`; vous vouliez peut-être utiliser 
    un opérateur d'égalité, `==`, ou l'opérateur `:=`.
    

Too many nested blocks
----------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "None", line None
    SyntaxError: too many statically nested blocks
    
        Sérieusement ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Vous n'êtes pas sérieux !
    
    Dans le cas où il s’agit d’une erreur dans un vrai programme, s’il vous plaît
    songez à réduire le nombre de blocs de code imbriqués.
    

Triple-equal sign
-----------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\triple_equal.py", line 3
        x = y === z
                ^
    SyntaxError: invalid syntax
    
        Voulez-vous utiliser `is` au lieu de `===`?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\triple_equal.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: 
       2: 
    -->3: x = y === z
                  ^

    Vous avez écrit trois signes égaux de suite ce qui est utilisé dans certains
    langages de programmation, mais pas en Python. Pour vérifier si deux objets
    sont égaux, utilisent deux signes d'égalité, `==`; pour voir si deux noms représentent
    exactement le même objet, utilisez l’opérateur `is`.
    

Unclosed bracket
----------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\unclosed_bracket.py", line 7
        print(foo())
        ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\unclosed_bracket.py'
    jusqu'à l'endroit indiqué par ^.
    
        3: 
        4: def foo():
        5:     return [1, 2, 3
        6: 
    --> 7: print(foo())
           ^

    Le symbole crochet `[` à la ligne 5 n'est pas fermé par le symbole correspondant.
    
        5:     return [1, 2, 3
                      ^
    

Unclosed parenthesis - 1
------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\unclosed_paren_1.py", line 3
        if x == 1:
                 ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\unclosed_paren_1.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: x = int('1'
    -->3: if x == 1:
                   ^

    Le symbole parenthèse `(` à la ligne 2 n'est pas fermé par le symbole correspondant.
    
        2: x = int('1'
                  ^
    

Unclosed parenthesis - 2
------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\unclosed_paren_2.py", line 3
        d = a*a
        ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\unclosed_paren_2.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: a = (b+c
    -->3: d = a*a
          ^

    Le symbole parenthèse `(` à la ligne 2 n'est pas fermé par le symbole correspondant.
    
        2: a = (b+c
               ^
    

Unclosed parenthesis - 3
------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\unclosed_paren_3.py", line 7
        if 2:
            ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\unclosed_paren_3.py'
    jusqu'à l'endroit indiqué par ^.
    
       3: if 3:
       4:     if 1:
       5:         print(((123))
       6: 
    -->7: if 2:
              ^

    Le symbole parenthèse `(` à la ligne 5 n'est pas fermé par le symbole correspondant.
    
        5:         print(((123))
                        ^
    

Content passed continuation line character
------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\unexpected_after_continuation_character.py", line 5
        print(\t)
                 ^
    SyntaxError: unexpected character after line continuation character
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\unexpected_after_continuation_character.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise
       2: SyntaxError: unexpected character after line continuation character
       3: """
       4: 
    -->5: print(\t)
                   ^

    Vous utilisez le caractère de continuation `\` en dehors d'une chaîne de caractères,
    et il est suivi par au moins un autre caractère.
    Je suppose que vous avez oublié de terminer la chaîne par un guillemet
    ou un apostrophe.
    
    

Unexpected EOF while parsing
----------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\unexpected_eof.py", line 8
    SyntaxError: unexpected EOF while parsing
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\unexpected_eof.py'
    jusqu'à l'endroit indiqué par ^.
    
        3: 
        4: def foo():
        5:     return [1, 2, 3,
        6: 
        7: print(foo())
    --> 8: 
           ^

    Python nous dit qu'il a atteint la fin du fichier
    et s'attendait à plus de contenu.
    
    Je vais essayer de donner un peu plus d'informations.
    
    
    Le symbole crochet `[` à la ligne 5 n'est pas fermé par le symbole correspondant.
    
        5:     return [1, 2, 3,
                      ^
    

Invalid character (unicode quote)
---------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\unicode_quote.py", line 3
        a = « hello »
            ^
    SyntaxError: invalid character in identifier
    
        Vouliez vous utiliser un guillemet normal, `'` ou `"` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\unicode_quote.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid character in identifier for Python <=3.8
       2:    and  SyntaxError: invalid character '«' (U+00AB) in Python 3.9"""
    -->3: a = « hello »
              ^

    Avez-vous utilisé le copier-coller ?
    Python indique que vous avez utilisé le caractère unicode `«`
    ce qui n’est pas permis.
    Je soupçonne que vous avez utilisé un guillemet unicode
    au lieu d'un guillemet normal (simple ou double) pour une chaîne de caractères.
    

Unmatched closing parenthesis
-----------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\unmatched_closing_paren.py", line 6
        3, 4,))
              ^
    SyntaxError: unmatched ')'
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\unmatched_closing_paren.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax for Python < 3.8
       2:    otherwise, SyntaxError: unmatched ')'
       3: """
       4: a = (1,
       5:     2,
    -->6:     3, 4,))
                    ^

    Le symbole parenthèse `)` à la ligne 6 n'a pas de symbole ouvrant qui lui correspond.
    

Mismatched brackets - 1
-----------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\unmatched_closing_bracket_1.py", line 2
        x = (1, 2, 3]
                    ^
    SyntaxError: closing parenthesis ']' does not match opening parenthesis '('
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\unmatched_closing_bracket_1.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
    -->2: x = (1, 2, 3]
                      ^

    Python nous dit que la parenthèse de droite `]` ne correspond pas
    à la parenthèse de gauche `(`.
    
    Je vais essayer de donner un peu plus d'informations.
    
    
    Le symbole crochet `]` à la ligne 2 ne correspond pas au symbole parenthèse `(` à la ligne 2.
    
        2: x = (1, 2, 3]
               ^       ^
    

Mismatched brackets - 2
-----------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\unmatched_closing_bracket_2.py", line 4
        3]
         ^
    SyntaxError: closing parenthesis ']' does not match opening parenthesis '(' on line 2
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\unmatched_closing_bracket_2.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: x = (1,
       3:      2,
    -->4:      3]
                ^

    Python nous dit que la parenthèse de droite `]` sur la dernière ligne
    ne correspond pas à la parenthèse de gauche `(` sur la ligne 2.
    
    Je vais essayer de donner un peu plus d'informations.
    
    
    Le symbole crochet `]` à la ligne 4 ne correspond pas au symbole parenthèse `(` à la ligne 2.
    
        2: x = (1,
               ^
        4:      3]
                 ^
    

Unterminated triple quoted string
---------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\unterminated_triple_quote_string.py", line 4
        some_text = """In a land
    populated by weird animals,
    a ...
                                                                   ^
    SyntaxError: EOF while scanning triple-quoted string literal
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python ne peut pas comprendre le code du fichier
    'TESTS:\syntax\unterminated_triple_quote_string.py'
    pour une raison non spécifiée.
    
       1: some_text =

    Vous avez commencé à écrire une chaîne débutant avec des triples guillemets,
    sans inclure les triples guillemets nécessaires pour mettre fin à la chaîne.
    

TabError
--------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\tab_error.py", line 7
        pass
            ^
    TabError: inconsistent use of tabs and spaces in indentation
    
    Une exception de type `TabError` indique que vous avez utilisé des espaces
    ainsi que des caractères de tabulation pour indenter votre code.
    Cela n’est pas autorisé dans Python.
    L’indentation de votre code signifie que le bloc de codes est aligné
    verticalement en insérant des espaces ou des tabulations au début des lignes.
    La recommandation de Python est de toujours utiliser des espaces
    pour indenter votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\tab_error.py'
    jusqu'à l'endroit indiqué par ^.
    
       3: 
       4: 
       5: def test_tab_error():
       6:     if True:
    -->7: 	pass
               ^

EOL unescaped backslash
-----------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\unescaped_backslash.py", line 1
        a = "abc\"
                  ^
    SyntaxError: EOL while scanning string literal
    
        Avez-vous oublié d’échapper un caractère barre oblique inverse ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\unescaped_backslash.py'
    jusqu'à l'endroit indiqué par ^.
    
    -->1: a = "abc\"
                    ^

    Vous aviez commencé à écrire une chaîne de caractères
    avec un guillemet simple ou double, mais n'avez jamais
    terminé la chaîne avec un autre guillemet sur cette ligne.
    Peut-être que vous vouliez écrire une barre oblique inverse, `\`
    comme le dernier caractère de la chaîne et vous oublié que vous
    deviez en écrire deux `\` d’affilée.
    

Using the backquote character
-----------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\use_backquote.py", line 3
        a = `1`
            ^
    SyntaxError: invalid syntax
    
        Vous ne devez pas utiliser le caractère accent grave.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\use_backquote.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: a = `1`
              ^

    Vous utilisez le charactère d'accent grave.
    Soit que vous vouliez utiliser un apostrophe, ',
    ou que vous avez copié du code de Python 2;
    dans ce dernier cas, utilisez la fonction `repr(x)`.

Would-be variable declaration
-----------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\would_be_type_declaration_1.py", line 3
        if var start := begin < end:
               ^
    SyntaxError: invalid syntax
    
        Vous n’avez pas besoin de déclarer des variables dans Python.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\would_be_type_declaration_1.py'
    jusqu'à l'endroit indiqué par ^.
    
       1: begin, end = 1, 2
       2: 
    -->3: if var start := begin < end:
                 ^

    Il semble que vous essayiez de déclarer que `start` est
    une variable utilisant le mot `var`.
    Si vous supprimez `var`, vous aurez une instruction Python valide.
    

Would-be variable declaration - 2
---------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 42, in create_tracebacks
        __import__(name)
      File "TESTS:\syntax\would_be_type_declaration_2.py", line 5
        var start := begin < end
            ^
    SyntaxError: invalid syntax
    
        Vous n’avez pas besoin de déclarer des variables dans Python.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\would_be_type_declaration_2.py'
    jusqu'à l'endroit indiqué par ^.
    
       2: end = 4
       3: 
       4: if (
    -->5:     var start := begin < end
                  ^
       6:    ):

    Il semble que vous essayiez de déclarer que `start` est
    une variable utilisant le mot `var`.
    Si vous supprimez `var`, vous aurez une instruction Python valide.
    
