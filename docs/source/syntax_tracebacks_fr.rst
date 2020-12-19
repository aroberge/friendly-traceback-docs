
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

Friendly-traceback version: 0.2.8a
Python version: 3.8.4



IndentationError - 1: expected an indented block
------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_indentation_error1.py", line 4
        pass
        ^
    IndentationError: expected an indented block
    
    Une exception de type `IndentationError` se produit lorsqu'une ligne de code
    n'est pas indentée (c'est-à-dire alignée verticalement avec les autres lignes)
    de la façon attendue.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_indentation_error1.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: '''Should raise IndentationError'''
       2: 
       3: if True:
    -->4: pass
          ^

        Dans ce cas-ci, la ligne indiquée ci-dessus par --> devrait
        normalement commencer un nouveau bloc de code indenté.
        

IndentationError - 2: unexpected indent
---------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_indentation_error2.py", line 4
        pass
       ^
    IndentationError: unexpected indent
    
    Une exception de type `IndentationError` se produit lorsqu'une ligne de code
    n'est pas indentée (c'est-à-dire alignée verticalement avec les autres lignes)
    de la façon attendue.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_indentation_error2.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: '''Should raise IndentationError'''
       2: if True:
       3:     pass
    -->4:       pass
               ^

        Dans ce cas-ci, la ligne indiquée ci-dessus par -->
        est plus indentée que ce qui était attendu et ne
        correspond pas à l'indentation de la ligne précédente.
        

IndentationError - 3: unindent does not match ...
-------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_indentation_error3.py", line 4
        pass
            ^
    IndentationError: unindent does not match any outer indentation level
    
    Une exception de type `IndentationError` se produit lorsqu'une ligne de code
    n'est pas indentée (c'est-à-dire alignée verticalement avec les autres lignes)
    de la façon attendue.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_indentation_error3.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: '''Should raise IndentationError'''
       2: if True:
       3:       pass
    -->4:     pass
                  ^

        Dans ce cas-ci, la ligne indiquée ci-dessus par -->
        est moins indentée que la ligne précédente
        et n’est pas alignée verticalement avec un autre bloc de code.
        

TabError
--------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_tab_error.py", line 7
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
    'TESTS:\syntax\raise_tab_error.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
        4: 
        5: def test_tab_error():
        6:     if True:
    --> 7: 	pass
                ^

SyntaxError - Assign to keyword
-------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error1.py", line 3
        def = 2
            ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error1.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """ Should raise SyntaxError"""
       2: 
    -->3: def = 2
              ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous essayiez d’assigner une valeur au mot clé Python `def`.
        Ceci n’est pas permis.
        
        

SyntaxError - Missing colon - 1
-------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error2.py", line 3
        if True
               ^
    SyntaxError: invalid syntax
    
        Vous avez peut-être oublié les deux points, `:`.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error2.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: if True
                 ^
       4:     pass

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous avez écrit un énoncé débutant avec
        `if` mais vous avez oublié d’ajouter deux points `:` à la fin.
        
        

SyntaxError - Missing colon - 2
-------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error3.py", line 3
        while True  # a comment
                    ^
    SyntaxError: invalid syntax
    
        Vous avez peut-être oublié les deux points, `:`.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error3.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: while True  # a comment
                      ^
       4:     pass

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous vouliez débuter une boucle `while`
        mais vous avez oublié d’ajouter deux points `:` à la fin.
        
        

SyntaxError - elif, not else if
-------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error4.py", line 5
        else if True:
             ^
    SyntaxError: invalid syntax
    
        Peut-être que vous vouliez plutôt `elif`.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error4.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: 
       3: if False:
       4:     pass
    -->5: else if True:
               ^
       6:     print('ok')

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous avez écrit `else if`
        au lieu d'utiliser le mot-clé `elif`.
        
        

SyntaxError - elif, not elseif
------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error5.py", line 5
        elseif True:
               ^
    SyntaxError: invalid syntax
    
        Peut-être que vous vouliez plutôt `elif`.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error5.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: 
       3: if False:
       4:     pass
    -->5: elseif True:
                 ^
       6:     print('ok')

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous avez écrit `elseif`
        au lieu d'utiliser le mot-clé `elif`.
        
        

SyntaxError - malformed def statment - 1
----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error6.py", line 3
        def :
            ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error6.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: def :
              ^
       4:     pass

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous vouliez définir une fonction ou une méthode,
        mais vous avez fait des erreurs de syntaxe.
        La syntaxe correcte est:
        
            def nom ( arguments_optionnels ):
        
        

SyntaxError - malformed def statment - 2
----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error7.py", line 3
        def name  :
                  ^
    SyntaxError: invalid syntax
    
        Vous avez peut-être oublié d'écrire des parenthèses.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error7.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: def name  :
                    ^
       4:     pass

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous vouliez définir une fonction ou une méthode,
        mais vous avez fait des erreurs de syntaxe.
        La syntaxe correcte est:
        
            def nom ( arguments_optionnels ):
        
        

SyntaxError - malformed def statment - 3
----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error8.py", line 3
        def ( arg )  :
            ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error8.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: def ( arg )  :
              ^
       4:     pass

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous vouliez définir une fonction ou une méthode,
        mais vous avez fait des erreurs de syntaxe.
        La syntaxe correcte est:
        
            def nom ( arguments_optionnels ):
        
        

SyntaxError - can't assign to literal - 1
-----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error9.py", line 3
        1 = a
        ^
    SyntaxError: cannot assign to literal
    
        Peut-être que vous vouliez plutôt écrire : `a = 1`
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error9.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: can't assign to literal"""
       2: 
    -->3: 1 = a
          ^

        Vous avez écrit une expression comme
        
            1 = a
        où `1`, du côté gauche du signe d'égalité
        est ou inclut un objet de type `int`
        et n'est pas simplement le nom d'une variable.  Peut-être que vous vouliez plutôt écrire :
        
            a = 1
        
        

SyntaxError - can't assign to literal - 2
-----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error10.py", line 3
        1 = 2
        ^
    SyntaxError: cannot assign to literal
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error10.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: can't assign to literal"""
       2: 
    -->3: 1 = 2
          ^

        Vous avez écrit une expression comme
        
            1 = 2
        où `1`, du côté gauche du signe d'égalité
        est ou inclut un objet de type `int`
        et n'est pas simplement le nom d'une variable.
        

SyntaxError - can't assign to literal - 3
-----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error52.py", line 7
        {1, 2, 3} = 4
        ^
    SyntaxError: cannot assign to set display
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error52.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
        4: 
        5:  """
        6: 
    --> 7: {1, 2, 3} = 4
           ^

        Vous avez écrit une expression comme
        
            {1, 2, 3} = 4
        où `{1, 2, 3}`, du côté gauche du signe d'égalité
        est ou inclut un objet de type `set`
        et n'est pas simplement le nom d'une variable.
        

SyntaxError - can't assign to literal - 4
-----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error53.py", line 7
        {1 : 2, 2 : 4} = 5
        ^
    SyntaxError: cannot assign to dict display
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error53.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
        4: 
        5:  """
        6: 
    --> 7: {1 : 2, 2 : 4} = 5
           ^

        Vous avez écrit une expression comme
        
            {1 : 2, 2 : 4} = 5
        où `{1 : 2, 2 : 4}`, du côté gauche du signe d'égalité
        est ou inclut un objet de type `dict`
        et n'est pas simplement le nom d'une variable.
        

SyntaxError - can't assign to literal - 5
-----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error54.py", line 4
        1 = a = b
        ^
    SyntaxError: cannot assign to literal
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error54.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
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
        

SyntaxError - import X from Y
-----------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error11.py", line 3
        import pen from turtle
                   ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error11.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: import pen from turtle
                     ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous avez écrit quelque chose comme
            import pen from turtle
        au lieu de
            from turtle import pen
        
        

SyntaxError - EOL while scanning string literal
-----------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error12.py", line 3
        alphabet = 'abc
                       ^
    SyntaxError: EOL while scanning string literal
    
        Avez-vous oublié d’ajouter un guillemet ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error12.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: EOL while scanning string literal"""
       2: 
    -->3: alphabet = 'abc
                         ^

        Vous aviez commencé à écrire une chaîne de caractères
        avec un guillemet simple ou double, mais n'avez jamais
        terminé la chaîne avec un autre guillemet sur cette ligne.
        

SyntaxError - assignment to keyword (None)
------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error13.py", line 4
        None = 1
        ^
    SyntaxError: cannot assign to None
    
        Vous ne pouvez pas attribuer une valeur à `None`.
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error13.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: cannot assign to None in Py 3.8
       2:    and can't assign to keyword before."""
       3: 
    -->4: None = 1
          ^

        `None` est une constante dans python; vous ne pouvez pas lui assigner une valeur.
        
        

SyntaxError - assignment to keyword (__debug__)
-----------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error14.py", line 4
        __debug__ = 1
        ^
    SyntaxError: cannot assign to __debug__
    
        Vous ne pouvez pas attribuer une valeur à `__debug__`.
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error14.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: cannot assign to __debug__ in Py 3.8
       2:    and assignment to keyword before."""
       3: 
    -->4: __debug__ = 1
          ^

        `__debug__` est une constante dans python; vous ne pouvez pas lui assigner une valeur.
        
        

SyntaxError - unmatched closing parenthesis
-------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error15.py", line 6
        3, 4,))
              ^
    SyntaxError: unmatched ')'
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error15.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       3: """
       4: a = (1,
       5:     2,
    -->6:     3, 4,))
                    ^
       7: b = 3

        Le symbole parenthèse `)` à la ligne 6 n'a pas de symbole ouvrant qui lui correspond.
        

SyntaxError - unclosed parenthesis- 1
-------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error16.py", line 3
        if x == 1:
                 ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error16.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: x = int('1'
    -->3: if x == 1:
                   ^
       4:     print('yes')

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Le symbole parenthèse `(` à la ligne 2 n'est pas fermé par le symbole correspondant.
        
            2: x = int('1'
                      |
        

SyntaxError - unclosed parenthesis - 2
--------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error17.py", line 3
        d = a*a
        ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error17.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: a = (b+c
    -->3: d = a*a
          ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Le symbole parenthèse `(` à la ligne 2 n'est pas fermé par le symbole correspondant.
        
            2: a = (b+c
                   |
        Il est également possible que vous ayez oublié une virgule entre les éléments d'un tuple,
        ou entre les arguments d'une fonction, avant la position indiquée par --> et ^.
        

SyntaxError - mismatched brackets
---------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error18.py", line 2
        x = (1, 2, 3]
                    ^
    SyntaxError: closing parenthesis ']' does not match opening parenthesis '('
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error18.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
    -->2: x = (1, 2, 3]
                      ^

        Python nous dit que la parenthèse de droite `]` ne correspond pas
        à la parenthèse de gauche `(`.
        
        Je vais essayer de donner un peu plus d'informations.
        
        
        Le symbole crochet `]` à la ligne 2 ne correspond pas au symbole parenthèse `(` à la ligne 2.
        
            2: x = (1, 2, 3]
                   ^       ^
        

SyntaxError - mismatched brackets - 2
-------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error19.py", line 4
        3]
         ^
    SyntaxError: closing parenthesis ']' does not match opening parenthesis '(' on line 2
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error19.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
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
        

SyntaxError - print is a function
---------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error20.py", line 2
        print 'hello'
              ^
    SyntaxError: Missing parentheses in call to 'print'. Did you mean print('hello')?
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error20.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: Missing parentheses in call to 'print' ..."""
    -->2: print 'hello'
                ^

        Peut-être que vous avez besoin d'écrire
        
             print('hello')
        
        Dans l'ancienne version de Python, `print` était un mot clé.
        Maintenant, `print` est une fonction; vous devez utiliser des parenthèses pour l'invoquer.
        

SyntaxError - Python keyword as function name
---------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error21.py", line 3
        def pass():
            ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error21.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: def pass():
              ^
       4:     print("keyword as function name!")

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous avez tenté d'utiliser le mot clé Python `pass` comme nom de fonction.
        Ceci n’est pas permis.
        
        

SyntaxError - break outside loop
--------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error22.py", line 4
        break
        ^
    SyntaxError: 'break' outside loop
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error22.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: 'break' outside loop"""
       2: 
       3: if True:
    -->4:     break
              ^

        Le mot-clé Python `break` ne peut être utilisé qu'à l'intérieur d'une boucle `for` ou à l'intérieur d'une boucle `while`.
        

SyntaxError - continue outside loop
-----------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error23.py", line 4
        continue
        ^
    SyntaxError: 'continue' not properly in loop
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error23.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: 'continue' outside loop"""
       2: 
       3: if True:
    -->4:     continue
              ^

        Le mot-clé Python `continue` ne peut être utilisé qu'à l'intérieur d'une boucle `for` ou à l'intérieur d'une boucle `while`.
        

SyntaxError - quote inside a string
-----------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error24.py", line 3
        message = 'don't'
                       ^
    SyntaxError: invalid syntax
    
        Vous avez peut-être un guillemet écrit au mauvais endroit.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error24.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: message = 'don't'
                         ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Il semble y avoir un identificateur Python (nom de variable)
        immédiatement après une chaîne.
        Je soupçonne que vous essayiez d'utiliser un apostrophe ou un guillemet
        à l'intérieur d'une chaîne qui était délimitée par ces mêmes caractères.
        

SyntaxError - missing comma in a dict
-------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error25.py", line 5
        'c': 3,
        ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error25.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: 
       3: a = {'a': 1,
       4:      'b': 2
    -->5:      'c': 3,
               ^
       6:      }

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Le symbole accolade `{` à la ligne 3 n'est pas fermé par le symbole correspondant.
        
            3: a = {'a': 1,
                   |
        Il est également possible que vous ayez oublié une virgule entre les éléments d'un ensemble (set)
        ou un dict avant la position indiquée par --> et ^.
        

SyntaxError - missing comma in a set
------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error26.py", line 3
        a = {1, 2  3}
                   ^
    SyntaxError: invalid syntax
    
        Avez-vous oublié quelque chose entre `2` et `3` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error26.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: a = {1, 2  3}
                     ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Python indique que l’erreur est causée par `3` écrit tout juste après `2`.
        Peut-être avez-vous oublié une virgule ou un opérateur, comme '+', '*', etc., entre `2` et `3`.

SyntaxError - missing comma in a list
-------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error27.py", line 3
        a = [1, 2  3]
                   ^
    SyntaxError: invalid syntax
    
        Avez-vous oublié quelque chose entre `2` et `3` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error27.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: a = [1, 2  3]
                     ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Python indique que l’erreur est causée par `3` écrit tout juste après `2`.
        Peut-être avez-vous oublié une virgule ou un opérateur, comme '+', '*', etc., entre `2` et `3`.

SyntaxError - missing comma in a tuple
--------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error28.py", line 3
        a = (1, 2  3)
                   ^
    SyntaxError: invalid syntax
    
        Avez-vous oublié quelque chose entre `2` et `3` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error28.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: a = (1, 2  3)
                     ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Python indique que l’erreur est causée par `3` écrit tout juste après `2`.
        Peut-être avez-vous oublié une virgule ou un opérateur, comme '+', '*', etc., entre `2` et `3`.

SyntaxError - missing comma between function args
-------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error29.py", line 4
        def a(b, c d):
                   ^
    SyntaxError: invalid syntax
    
        Avez-vous oublié quelque chose entre `c` et `d` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error29.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
       3: 
    -->4: def a(b, c d):
                     ^
       5:     pass

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Python indique que l’erreur est causée par `d` écrit tout juste après `c`.
        Peut-être avez-vous oublié une virgule ou un opérateur, comme '+', '*', etc., entre `c` et `d`.

SyntaxError - can't assign to function call - 1
-----------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error30.py", line 6
        len('a') = 3
        ^
    SyntaxError: cannot assign to function call
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error30.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
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
        

SyntaxError - can't assign to function call - 2
-----------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error31.py", line 6
        func(a, b=3) = 4
        ^
    SyntaxError: cannot assign to function call
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error31.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       3: Python 3.8: SyntaxError: cannot assign to function call
       4: """
       5: 
    -->6: func(a, b=3) = 4
          ^

        Vous avez écrit une expression comme
        
            ma_fonction(…) = une certaine valeur
        
        où `ma_fonction(…)`, du côté gauche du signe d'égalité
        est une fonction et non le nom d’une variable.
        

SyntaxError - used equal sign instead of colon
----------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error32.py", line 4
        ages = {'Alice'=22, 'Bob'=24}
                       ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error32.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax
       2: """
       3: 
    -->4: ages = {'Alice'=22, 'Bob'=24}
                         ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Il est possible que vous ayez utilisé un signe d'égalité `=` au lieu de deux points `:`
        pour attribuer des valeurs à une clé d'un dictionnaire
        avant ou exactement à la position indiquée par --> et ^.
        

SyntaxError - non-default argument follows default argument
-----------------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error33.py", line 5
        def test(a=1, b):
                 ^
    SyntaxError: non-default argument follows default argument
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error33.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: """
       3: 
       4: 
    -->5: def test(a=1, b):
                   ^
       6:     return a + b

        Dans Python, vous pouvez définir les fonctions avec seulement des arguments de position
        
            def test(a, b, c): ...
        
        ou seulement des arguments nommés
        
            def test(a=1, b=2, c=3): ...
        
        ou une combinaison des deux
        
            def test(a, b, c=3): ...
        
        mais avec les arguments nommés apparaissant après tous les arguments positionnels.
        Selon Python, vous avez utilisé des arguments positionnels après des arguments nommés.
        

SyntaxError - positional argument follows keyword argument
----------------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error34.py", line 5
        test(a=1, b)
                  ^
    SyntaxError: positional argument follows keyword argument
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error34.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
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
        

SyntaxError - f-string: unterminated string
-------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error35.py", line 4
        print(f"Bob is {age['Bob]} years old.")
              ^
    SyntaxError: f-string: unterminated string
    
        Avez-vous oublié d’ajouter un guillemet ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error35.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: f-string: unterminated string
       2: """
       3: 
    -->4: print(f"Bob is {age['Bob]} years old.")
                ^

        À l'intérieur d'une "f-string", qui est une chaîne de caractères préfixée de la lettre f,
        vous avez une autre chaîne de caractère qui débute soit avec un apostrophe (')
        ou des guillemets ("), mais n'est pas terminé par un autre caractère semblable.
        

SyntaxError - unclosed bracket
------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error36.py", line 7
        print(foo())
        ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error36.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
        4: def foo():
        5:     return [1, 2, 3
        6: 
    --> 7: print(foo())
           ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Le symbole crochet `[` à la ligne 5 n'est pas fermé par le symbole correspondant.
        
            5:     return [1, 2, 3
                          |
        Il est également possible que vous ayez oublié une virgule entre les éléments d'une liste
        avant la position indiquée par --> et ^.
        

SyntaxError - unexpected EOF while parsing
------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error37.py", line 8
    SyntaxError: unexpected EOF while parsing
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error37.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
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
                          |
        

SyntaxError - name is parameter and global
------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error38.py", line 6
        global x
        ^
    SyntaxError: name 'x' is parameter and global
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error38.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       3: 
       4: 
       5: def f(x):
    -->6:     global x
              ^

        Vous avec inclus l'énoncé
        
            `    global x`
        
        indiquant que `x` est une variable définie en dehors d'une fonction.
        Vous utilisez également le même `x` comme un argument pour cette
        fonction; un argument de fonction est une variable locale connue seulement
        à l'intérieur de cette fonction, ce qui est le contraire de ce que `global` sous-entendait.
        

SyntaxError - keyword as attribute
----------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error39.py", line 12
        a.pass = 2
          ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error39.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
        9: a = A()
       10: 
       11: a.x = 1
    -->12: a.pass = 2
             ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous avez tenté d'utiliser le mot clé Python `pass` comme attribut.
        Ceci n’est pas permis.
        
        

SyntaxError - content passed continuation line character
--------------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error40.py", line 5
        print(\t)
                 ^
    SyntaxError: unexpected character after line continuation character
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error40.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: SyntaxError: unexpected character after line continuation character
       3: """
       4: 
    -->5: print(\t)
                   ^

        Vous utilisez le caractère de continuation `\` en dehors d'une chaîne de caractères,
        et il est suivi par au moins un autre caractère.
        Je suppose que vous avez oublié de terminer la chaîne par un guillemet
        ou un apostrophe.
        
        

SyntaxError - keyword can't be an expression
--------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error41.py", line 7
        a = dict('key'=1)
                 ^
    SyntaxError: expression cannot contain assignment, perhaps you meant "=="?
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error41.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
        4: """
        5: 
        6: 
    --> 7: a = dict('key'=1)
                    ^

        L'une des deux possibilités suivantes pourrait être la cause:
        1. Vous vouliez faire une comparaison avec `==` et vous avez écrit `=` à sa place.
        2. Vous avez invoqué une fonction avec un argument nommé:
        
                une_fonction (invalide=quelque_chose)
        
        où `invalide` n'est pas un nom de variable valide dans Python
        soit parce qu'il commence par un nombre, soit qu'il est une chaîne,
        ou contient un point, etc.
        
        

SyntaxError - invalid character in identifier
---------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error42.py", line 6
        🤖 = 'Reeborg'
        ^
    SyntaxError: invalid character in identifier
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error42.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       3: 
       4: # Robot-face character below
       5: 
    -->6: 🤖 = 'Reeborg'
          ^

        Vous avez probablement utilisé un caractère unicode qui n'est pas autorisé
        dans le nom d'une variable dans Python.
        Cela comprend de nombreux emojis.
        
        

SyntaxError - keyword cannot be argument in def - 1
---------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error43.py", line 5
        def f(None=1):
              ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error43.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: """
       3: 
       4: 
    -->5: def f(None=1):
                ^
       6:     pass

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous avez tenté d'utiliser le mot clé Python `None` comme argument
        dans la définition d'une fonction.
        Ceci n’est pas permis.
        
        

SyntaxError - keyword cannot be argument in def - 2
---------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error44.py", line 5
        def f(x, True):
                 ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error44.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: """
       3: 
       4: 
    -->5: def f(x, True):
                   ^
       6:     pass

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous avez tenté d'utiliser le mot clé Python `True` comme argument
        dans la définition d'une fonction.
        Ceci n’est pas permis.
        
        

SyntaxError - keyword cannot be argument in def - 3
---------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error45.py", line 5
        def f(*None):
               ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error45.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: """
       3: 
       4: 
    -->5: def f(*None):
                 ^
       6:     pass

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous avez tenté d'utiliser le mot clé Python `None` comme argument
        dans la définition d'une fonction.
        Ceci n’est pas permis.
        
        

SyntaxError - keyword cannot be argument in def - 4
---------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error46.py", line 5
        def f(**None):
                ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error46.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: """
       3: 
       4: 
    -->5: def f(**None):
                  ^
       6:     pass

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous avez tenté d'utiliser le mot clé Python `None` comme argument
        dans la définition d'une fonction.
        Ceci n’est pas permis.
        
        

SyntaxError - delete function call
----------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error47.py", line 5
        del f(a)
            ^
    SyntaxError: cannot delete function call
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error47.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: """
       3: 
       4: 
    -->5: del f(a)
              ^

        Vous avez tenté de supprimer un appel de fonction
        
            del f(a)
        au lieu de supprimer le nom de la fonction
        
            del f
        

SyntaxError - assigned prior to global declaration
--------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error48.py", line 7
        global p
        ^
    SyntaxError: name 'p' is assigned to before global declaration
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error48.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
        4: 
        5: def fn():
        6:     p = 1
    --> 7:     global p
               ^

        Vous avez attribué une valeur à la variable `p`
        avant de la déclarer comme une variable globale.
        

SyntaxError - used prior to global declaration
----------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error49.py", line 7
        global r
        ^
    SyntaxError: name 'r' is used prior to global declaration
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error49.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
        4: 
        5: def fn():
        6:     print(r)
    --> 7:     global r
               ^

        Vous avez utilisé la variable `r`
        avant de la déclarer comme une variable globale.
        

SyntaxError - assigned prior to nonlocal declaration
----------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error50.py", line 9
        nonlocal q
        ^
    SyntaxError: name 'q' is used prior to nonlocal declaration
    
        Avez-vous oublié d’ajouter `nonlocal` en premier ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error50.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
        6: 
        7:     def g():
        8:         print(q)
    --> 9:         nonlocal q
                   ^

        Vous avez utilisé la variable `q`
        avant de la déclarer comme variable non locale.
        

SyntaxError - used prior to nonlocal declaration
------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error51.py", line 9
        nonlocal s
        ^
    SyntaxError: name 's' is assigned to before nonlocal declaration
    
        Avez-vous oublié d’ajouter `nonlocal` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error51.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
        6: 
        7:     def g():
        8:         s = 2
    --> 9:         nonlocal s
                   ^

        Vous avez attribué une valeur à la variable `s`
        avant de la déclarer comme variable non locale.
        

SyntaxError - named assignment with Python constant
---------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error55.py", line 4
        (True := 1)
         ^
    SyntaxError: cannot use assignment expressions with True
    
        Vous ne pouvez pas attribuer une valeur à `True`.
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error55.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax
       2: or (Python 3.8) cannot use named assignment with True"""
       3: 
    -->4: (True := 1)
           ^

        `True` est une constante dans python; vous ne pouvez pas lui assigner une valeur.
        
        

SyntaxError - assignment to operator
------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error56.py", line 4
        a + 1 = 2
        ^
    SyntaxError: cannot assign to operator
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error56.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: can't assign to operator
       2: or (Python 3.8) cannot assign to operator"""
       3: 
    -->4: a + 1 = 2
          ^

        Vous avez écrit une expression qui inclut des opérations mathématiques
        du côté gauche du signe d'égalité; ceci devrait être
        utilisé uniquement pour attribuer une valeur à une variable.

SyntaxError - using the backquote character
-------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error57.py", line 3
        a = `1`
            ^
    SyntaxError: invalid syntax
    
        Vous ne devez pas utiliser le caractère accent grave.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error57.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: a = `1`
              ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous utilisez le charactère d'accent grave.
        Soit que vous vouliez utiliser un apostrophe, ',
        ou que vous avez copié du code de Python 2;
        dans ce dernier cas, utilisez la fonction `repr(x)`.

SyntaxError - assign to generator expression
--------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error58.py", line 3
        (x for x in x) = 1
        ^
    SyntaxError: cannot assign to generator expression
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error58.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: can't [cannot] assign to generator expression"""
       2: 
    -->3: (x for x in x) = 1
          ^

        Du côté gauche d'un signe d'égalité, vous avez une
        expression génératrice au lieu du nom d'une variable.
        

SyntaxError - assign to conditional expression
----------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error59.py", line 3
        a if 1 else b = 1
        ^
    SyntaxError: cannot assign to conditional expression
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error59.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: can't [cannot] assign to conditional expression"""
       2: 
    -->3: a if 1 else b = 1
          ^

        Du côté gauche d'un signe d'égalité, vous avez une
        expression conditionnelle au lieu du nom d'une variable.
        Une expression conditionnelle doit avoir la forme suivante:
        
            variable = objet if condition else autre_objet

SyntaxError - name is parameter and nonlocal
--------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error60.py", line 5
        nonlocal x
        ^
    SyntaxError: name 'x' is parameter and nonlocal
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error60.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: 
       3: 
       4: def f(x):
    -->5:     nonlocal x
              ^

        Vous avez utilisé `x` comme paramètre pour une fonction
        avant de la déclarer également comme une variable non locale :
        `x` ne peut pas être les deux en même temps.
        

SyntaxError - name is global and nonlocal
-----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error61.py", line 7
        global xy
        ^
    SyntaxError: name 'xy' is nonlocal and global
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error61.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
        4: 
        5: 
        6: def f():
    --> 7:     global xy
               ^
        8:     nonlocal xy

        Vous avez utilisé `xy` comme étant une variable non locale et globale.
        Une variable peut être d'un seul type à la fois: soit globale, soit non locale, ou soit locale.
        

SyntaxError - nonlocal variable not found
-----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error62.py", line 5
        nonlocal ab
        ^
    SyntaxError: no binding for nonlocal 'ab' found
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error62.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: 
       3: 
       4: def f():
    -->5:     nonlocal ab
              ^

        Vous avez déclaré la variable `ab` comme non locale
        mais elle n'existe pas ailleurs.
        

SyntaxError - nonlocal variable not found at module level
---------------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error63.py", line 4
        nonlocal cd
        ^
    SyntaxError: nonlocal declaration not allowed at module level
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error63.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError:  nonlocal declaration not allowed at module level"""
       2: 
       3: 
    -->4: nonlocal cd
          ^

        Vous avez utilisé le mot clé nonlocal au niveau d'un module.
        Le mot clé nonlocal fait référence à une variable à l'intérieur d'une fonction
        qui a une valeur attribuée à l'extérieur de cette fonction.

SyntaxError - keyword arg only once in function definition
----------------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error64.py", line 4
        def f(aa=1, aa=2):
        ^
    SyntaxError: duplicate argument 'aa' in function definition
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error64.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: duplicate argument 'aa' in function definition"""
       2: 
       3: 
    -->4: def f(aa=1, aa=2):
          ^
       5:     pass

        Vous avez défini une fonction répétant l'argument nommé
        
            aa
        deux fois; chaque argument nommé ne doit apparaître qu'une seule fois dans une définition de fonction.
        

SyntaxError - keyword arg only once in function call
----------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error65.py", line 4
        f(ad=1, ad=2)
                ^
    SyntaxError: keyword argument repeated
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error65.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError:  keyword argument repeated"""
       2: 
       3: 
    -->4: f(ad=1, ad=2)
                  ^

        Vous avez invoqué une fonction en répétant le même argument nommé.
        Chaque argument de ce type ne peut apparaître qu'une seule fois.
        

SyntaxError - unexpected EOF while parsing 2
--------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error66.py", line 4
    SyntaxError: unexpected EOF while parsing
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error66.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: '''Should raise SyntaxError: unexpected EOF while parsing'''
       2: 
       3: for i in range(10):
    -->4: 
          ^

        Python nous dit qu'il a atteint la fin du fichier
        et s'attendait à plus de contenu.
        
        

SyntaxError - print is a function 2
-----------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error67.py", line 2
        print len('hello')
              ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error67.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
    -->2: print len('hello')
                ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Dans l'ancienne version de Python, `print` était un mot clé.
        Maintenant, `print` est une fonction; vous devez utiliser des parenthèses pour l'invoquer.
        

SyntaxError - copy/paste from interpreter
-----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error68.py", line 2
        >>> print("Hello World!")
        ^
    SyntaxError: invalid syntax
    
        Avez-vous utilisé copier-coller ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error68.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
    -->2: >>> print("Hello World!")
          ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        On dirait que vous avez copié-collé le code d’un interprète interactif.
        L’invite Python, `>>>`, ne doit pas être incluse dans votre code.
        

SyntaxError - Using pip from interpreter
----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error69.py", line 2
        pip install friendly
            ^
    SyntaxError: invalid syntax
    
        Pip ne peut pas être utilisé dans un interprète Python.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error69.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
    -->2: pip install friendly
              ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Il semble que vous essayez d’utiliser pip pour installer un module.
        `pip` est une commande qui doit être invoquée dans un terminal,
        pas dans un interprète Python.
        

SyntaxError - Using pip from interpreter 2
------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error70.py", line 2
        python -m pip install friendly
                  ^
    SyntaxError: invalid syntax
    
        Pip ne peut pas être utilisé dans un interprète Python.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error70.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
    -->2: python -m pip install friendly
                    ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Il semble que vous essayez d’utiliser pip pour installer un module.
        `pip` est une commande qui doit être invoquée dans un terminal,
        pas dans un interprète Python.
        

SyntaxError - dot followed by parenthesis
-----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error71.py", line 2
        print(len.('hello'))
                  ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error71.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
    -->2: print(len.('hello'))
                    ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous ne pouvez pas avoir un point `.` suivi de `(`.
        

SyntaxError - cannot assign to f-string
---------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error72.py", line 6
        f'{x}' = 42
        ^
    SyntaxError: cannot assign to f-string expression
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error72.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       3: Python >= 3.8: SyntaxError: cannot assign to f-string expression
       4: """
       5: 
    -->6: f'{x}' = 42
          ^

        Vous avez écrit une expression qui a une chaine de
        caractères formatés (aussi appelé f-string)
        sur le côté gauche du signe d'égalité.
        Une f-string ne doit apparaître que sur le côté droit du signe d’égalité.
        

SyntaxError - raising multiple exceptions
-----------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error73.py", line 2
        raise X, Y
               ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error73.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
    -->2: raise X, Y
                 ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Je crois que vous essayez de lever une exception en utilisant la syntaxe de Python 2.
        

SyntaxError - parenthesis around generator expression
-----------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error74.py", line 6
        f(x for x in L, 1)
          ^
    SyntaxError: Generator expression must be parenthesized
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error74.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       3:     return list(it)
       4: 
       5: L = range(10)
    -->6: f(x for x in L, 1)
            ^

        Vous utilisez une expression de générateur, quelque chose de la forme
            `x for x in objet`
        Vous devez ajouter des parenthèses qui entourent cette expression.
        

SyntaxError - invalid character (bad quote)
-------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error75.py", line 3
        a = « hello »
            ^
    SyntaxError: invalid character in identifier
    
        Vouliez vous utiliser un guillemet normal, `'` ou `"` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error75.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid character in identifier for Python <=3.8
       2:    and  SyntaxError: invalid character '«' (U+00AB) in Python 3.9"""
    -->3: a = « hello »
              ^

        Python indique que vous avez utilisé des caractères unicode non permis
        comme étant partie d’un nom de variable; cela inclut de nombreux emojis.
        Cependant, je soupçonne que vous avez utilisé un guillemet unicode 
        au lieu d’un guillemet normal (simple ou double) pour une chaîne de caractères.
        Cela peut se produire si vous utilisez du copier-coller.
        
        

SyntaxError - single = instead of double == with if
---------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error76.py", line 3
        if i % 2 = 0:
                 ^
    SyntaxError: invalid syntax
    
        Peut-être que vous aviez besoin de `==` au lieu de `=`.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error76.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: for i in range(101):
    -->3:     if i % 2 = 0:
                       ^
       4:         print(i)

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous avez utilisé un opérateur d’affectation `=` au lieu d’un opérateur d'égalité `==` 
        avec un énoncé `if`.
        

SyntaxError - single = instead of double == with elif
-----------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error77.py", line 5
        elif i % 2 = 0:
                   ^
    SyntaxError: invalid syntax
    
        Peut-être que vous aviez besoin de `==` au lieu de `=`.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error77.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: for i in range(101):
       3:     if False:
       4:         pass
    -->5:     elif i % 2 = 0:
                         ^
       6:         print(i)

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous avez utilisé un opérateur d’affectation `=` au lieu d’un opérateur d'égalité `==` 
        avec un énoncé `elif`.
        

SyntaxError - single = instead of double == with while
------------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error78.py", line 4
        while a = 1:
                ^
    SyntaxError: invalid syntax
    
        Peut-être que vous aviez besoin de `==` ou `:=` au lieu de `=`.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error78.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: a = 1
       3: 
    -->4: while a = 1:
                  ^
       5:     a = 2

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Vous avez utilisé un opérateur d’affectation `=`; vous vouliez peut-être utiliser 
        un opérateur d'égalité, `==`, ou l'opérateur `:=`.
        

SyntaxError - forgot a comma in an f-string
-------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "<fstring>", line 1
        (x y)
           ^
    SyntaxError: invalid syntax
    
        Avez-vous oublié quelque chose entre `x` et `y` ?
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    '<fstring>'
    jusqu'à l'endroit indiqué par --> et ^.
    
    -->1: (x y)
             ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Python indique que l’erreur est causée par `y` écrit tout juste après `x`.
        Peut-être avez-vous oublié une virgule ou un opérateur, comme '+', '*', etc., entre `x` et `y`.

SyntaxError - Valid names cannot begin with a number
----------------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error80.py", line 3
        36abc = 3
          ^
    SyntaxError: invalid syntax
    
        Les noms valides ne peuvent pas commencer par un chiffre.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error80.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: 36abc = 3
            ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Les noms valides ne peuvent pas commencer par un chiffre.
        

SyntaxError - unclosed parenthesis - 3
--------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error81.py", line 7
        if 2:
            ^
    SyntaxError: invalid syntax
    
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error81.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
        4:     if 1:
        5:         print(((123))
        6: 
    --> 7: if 2:
               ^
        8:     print(123))

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Le symbole parenthèse `(` à la ligne 5 n'est pas fermé par le symbole correspondant.
        
            5:         print(((123))
                            |
        

SyntaxError - forgot a multiplication operator
----------------------------------------------

.. code-block:: none


    Traceback (most recent call last):
      File "TESTS:\trb_syntax_common.py", line 138, in create_tracebacks
        mod = __import__(name)
      File "TESTS:\syntax\raise_syntax_error82.py", line 3
        tau = 2pi
               ^
    SyntaxError: invalid syntax
    
        Peut-être avez-vous oublié un opérateur de multiplication, `2 * pi`.
        
    Une exception de type `SyntaxError` se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error82.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: tau = 2pi
                 ^

        Ci-dessous, je tente de deviner ce que a mal tourné, mais je pourrais me tromper.
        
        Les noms valides ne peuvent pas commencer par un chiffre.
        Peut-être avez-vous oublié un opérateur de multiplication, `2 * pi`.
        
