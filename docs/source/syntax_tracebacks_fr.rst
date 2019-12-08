
Friendly SyntaxError tracebacks - en Français
=============================================

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

Friendly-traceback version: 0.0.19a
Python version: 3.7.3



IndentationError - 1: expected an indented block
------------------------------------------------

.. code-block:: none


    Exception Python:
        IndentationError: expected an indented block
        
    Une exception de type IndentationError se produit lorsqu'une ligne de code
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

    Cause probable basée sur les informations données par Python :
        Dans ce cas-ci, la ligne indiquée ci-dessus par --> devrait
        normalement commencer un nouveau bloc de code indenté.
        

IndentationError - 2: unexpected indent
---------------------------------------

.. code-block:: none


    Exception Python:
        IndentationError: unexpected indent
        
    Une exception de type IndentationError se produit lorsqu'une ligne de code
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

    Cause probable basée sur les informations données par Python :
        Dans ce cas-ci, la ligne indiquée ci-dessus par -->
        est plus indentée que ce qui était attendu et ne
        correspond pas à l'indentation de la ligne précédente.
        

IndentationError - 3: unindent does not match ...
-------------------------------------------------

.. code-block:: none


    Exception Python:
        IndentationError: unindent does not match any outer indentation level
        
    Une exception de type IndentationError se produit lorsqu'une ligne de code
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

    Cause probable basée sur les informations données par Python :
        Dans ce cas-ci, la ligne indiquée ci-dessus par -->
        est moins indentée que la ligne précédente
        et n’est pas alignée verticalement avec un autre bloc de code.
        

TabError
--------

.. code-block:: none


    Exception Python:
        TabError: inconsistent use of tabs and spaces in indentation
        
    Une exception de type TabError indique que vous avez utilisé des espaces
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


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error1.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """ Should raise SyntaxError"""
       2: 
    -->3: def = 2
              ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous essayiez d’assigner une valeur au mot clé Python 'def'.
        Ceci n’est pas permis.
        
        

SyntaxError - Missing colon 1
-----------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error2.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: if True
                 ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous avez écrit un énoncé débutant avec
        'if' mais vous avez oublié d’ajouter deux points ':' à la fin.
        
        

SyntaxError - Missing colon 2
-----------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error3.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: while True  # a comment
                                 ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous vouliez débuter une boucle 'while'
        mais vous avez oublié d’ajouter deux points ':' à la fin.
        
        

SyntaxError - elif, not else if
-------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error4.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: 
       3: if False:
       4:     pass
    -->5: else if True:
                ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous avez écrit 'else if'
        au lieu d'utiliser le mot-clé 'elif'.
        
        

SyntaxError - elif, not elseif
------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error5.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: 
       3: if False:
       4:     pass
    -->5: elseif True:
                    ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous avez écrit 'elseif'
        au lieu d'utiliser le mot-clé 'elif'.
        
        

SyntaxError - malformed def statment - 1
----------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error6.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: def :
              ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous vouliez définir une fonction ou une méthode,
        mais vous avez fait des erreurs de syntaxe.
        La syntaxe correcte est:
            def nom ( arguments_optionnels ):
        
        

SyntaxError - malformed def statment - 2
----------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error7.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: def name  :
                    ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous vouliez définir une fonction ou une méthode,
        mais vous avez fait des erreurs de syntaxe.
        La syntaxe correcte est:
            def nom ( arguments_optionnels ):
        
        

SyntaxError - malformed def statment - 3
----------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error8.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: def ( arg )  :
              ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous vouliez définir une fonction ou une méthode,
        mais vous avez fait des erreurs de syntaxe.
        La syntaxe correcte est:
            def nom ( arguments_optionnels ):
        
        

SyntaxError - can't assign to literal
-------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: can't assign to literal
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error9.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: can't assign to literal"""
       2: 
    -->3: 1 = a
         ^

    Cause probable basée sur les informations données par Python :
        Vous avez écrit une expression comme
            1 =  a
        où <1>, sur le côté gauche du signe égal, est soit ce que Python
        appelle un 'literal', c'est-à-dire soit une chaîne de caractères ou un nombre,
        ou soit inclus un tel 'literal', et n'est pas un simple nom d’une variable.  Peut-être que vous vouliez plutôt écrire :
            a = 1
        
        

SyntaxError - can't assign to literal - 2
-----------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: can't assign to literal
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error10.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: can't assign to literal"""
       2: 
    -->3: 1 = 2
         ^

    Cause probable basée sur les informations données par Python :
        Vous avez écrit une expression comme
            1 =  2
        où <1>, sur le côté gauche du signe égal, est soit ce que Python
        appelle un 'literal', c'est-à-dire soit une chaîne de caractères ou un nombre,
        ou soit inclus un tel 'literal', et n'est pas un simple nom d’une variable.
        

SyntaxError - import X from Y
-----------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error11.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: import pen from turtle
                        ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous avez écrit quelque chose comme
            import pen from turtle
        au lieu de
            from turtle import pen
        
        
        

SyntaxError - EOL while scanning string literal
-----------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: EOL while scanning string literal
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error12.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: EOL while scanning string literal"""
       2: 
    -->3: alphabet = 'abc
                         ^

    Cause probable basée sur les informations données par Python :
        Vous aviez commencé à écrire une chaîne de caractères
        avec un guillemet simple ou double, mais n'avez jamais
        terminé la chaîne avec un autre guillemet sur cette ligne.
        

SyntaxError - assignment to keyword (None)
------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: can't assign to keyword
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error13.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: cannot assign to None in Py 3.8
       2:    and can't assign to keyword before."""
       3: 
    -->4: None = 1
         ^

    Cause probable basée sur les informations données par Python :
        None est une constante dans python; vous ne pouvez pas lui assigner une valeur.
        
        

SyntaxError - assignment to keyword (__debug__)
-----------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: assignment to keyword
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error14.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: cannot assign to __debug__ in Py 3.8
       2:    and assignment to keyword before."""
       3: 
    -->4: __debug__ = 1
         ^

    Cause probable basée sur les informations données par Python :
        __debug__ est une constante dans python; vous ne pouvez pas lui assigner une valeur.
        
        

SyntaxError - unmatched closing parenthesis
-------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error15.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       3: """
       4: a = (1,
       5:     2,
    -->6:     3, 4,))
                    ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Le symbole parenthèse ')' à la ligne 6 n'a pas de symbole ouvrant qui lui correspond.
        
            6:     3, 4,))
                         ^
        

SyntaxError - unclosed parenthesis
----------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error16.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: x = int('1'
    -->3: if x == 1:
                   ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Le symbole parenthèse '(' à la ligne 2 n'est pas fermé par le symbole correspondant.
        
            2: x = int('1'
                      ^
        

SyntaxError - unclosed parenthesis - 2
--------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error17.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: a = (b+c
    -->3: d = a*a
          ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Le symbole parenthèse '(' à la ligne 2 n'est pas fermé par le symbole correspondant.
        
            2: a = (b+c
                   ^
        

SyntaxError - mismatched brackets
---------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error18.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
    -->2: x = (1, 2, 3]
                      ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Le symbole crochet ']' à la ligne 2 ne correspond pas au symbole parenthèse '(' à la ligne 2.
        
            2: x = (1, 2, 3]
                   ^       ^
        

SyntaxError - mismatched brackets - 2
-------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error19.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: x = (1,
       3:      2,
    -->4:      3]
                ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Le symbole crochet ']' à la ligne 4 ne correspond pas au symbole parenthèse '(' à la ligne 2.
        
            2: x = (1,
                   ^
            4:      3]
                     ^
        

SyntaxError - print is a function
---------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: Missing parentheses in call to 'print'. Did you mean print('hello')?
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error20.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: Missing parentheses in call to 'print' ..."""
    -->2: print 'hello'
                      ^

    Cause probable basée sur les informations données par Python :
        Peut-être que vous avez besoin d'écrire print('hello') ?
        
        Dans l'ancienne version de Python, «print» était un mot clé.
        Maintenant, «print» est une fonction; vous devez utiliser des parenthèses pour l'invoquer.
        

SyntaxError - Python keyword as function name
---------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error21.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: def pass():
                 ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous avez tenté d'utiliser le mot clé Python 'pass' comme nom de fonction.
        Ceci n’est pas permis.
        
        

SyntaxError - break outside loop
--------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: 'break' outside loop
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error22.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: 'break' outside loop"""
       2: 
       3: if True:
    -->4:     break
             ^

    Cause probable basée sur les informations données par Python :
        Le mot-clé Python 'break' ne peut être utilisé qu'à l'intérieur d'une boucle 'for' ou à l'intérieur d'une boucle 'while'.
        

SyntaxError - continue outside loop
-----------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: 'continue' not properly in loop
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error23.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: 'continue' outside loop"""
       2: 
       3: if True:
    -->4:     continue
             ^

    Cause probable basée sur les informations données par Python :
        Le mot-clé Python 'continue' ne peut être utilisé qu'à l'intérieur d'une boucle 'for' ou à l'intérieur d'une boucle 'while'.
        

SyntaxError - quote inside a string
-----------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error24.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: message = 'don't'
                         ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Il semble y avoir un identificateur Python (nom de variable)
        immédiatement après une chaîne.
        Je soupçonne que vous essayiez d'utiliser un apostrophe ou un guillemet
        à l'intérieur d'une chaîne qui était délimitée par ces mêmes caractères.
        

SyntaxError - missing comma in a dict
-------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error25.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: 
       3: a = {'a': 1,
       4:      'b': 2
    -->5:      'c': 3,
                 ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Il est possible que vous ayez oublié une virgule entre les éléments d'un ensemble (set)
        ou un dict avant la position indiquée par --> et ^.
        

SyntaxError - missing comma in a set
------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error26.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: a = {1, 2  3}
                     ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Il est possible que vous ayez oublié une virgule entre les éléments d'un ensemble (set)
        ou un dict avant la position indiquée par --> et ^.
        

SyntaxError - missing comma in a list
-------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error27.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: a = [1, 2  3]
                     ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Il est possible que vous ayez oublié une virgule entre les éléments d'une liste
        avant la position indiquée par --> et ^.
        

SyntaxError - missing comma in a tuple
--------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error28.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: a = (1, 2  3)
                     ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Il est possible que vous ayez oublié une virgule entre les éléments d'un tuple,
        ou entre les arguments d'une fonction, avant la position indiquée par --> et ^.
        

SyntaxError - missing comma between function args
-------------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error29.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
       3: 
    -->4: def a(b, c d):
                     ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Il est possible que vous ayez oublié une virgule entre les éléments d'un tuple,
        ou entre les arguments d'une fonction, avant la position indiquée par --> et ^.
        

SyntaxError - can't assign to function call - 1
-----------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: can't assign to function call
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error30.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       3: Python 3.8: SyntaxError: cannot assign to function call
       4: """
       5: 
    -->6: len('a') = 3
         ^

    Cause probable basée sur les informations données par Python :
        Vous avez écrit une expression comme
            len('a') =  3
        où len('a'), à la gauche du signe d'égalité est soit l'invocation
        d'une fonction, ou inclus une telle invocation,
        et n'est pas simplement le nom d'une variable.
        

SyntaxError - can't assign to function call - 2
-----------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: can't assign to function call
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error31.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       3: Python 3.8: SyntaxError: cannot assign to function call
       4: """
       5: 
    -->6: func(a, b=3) = 4
         ^

    Cause probable basée sur les informations données par Python :
        Vous avez écrit une expression comme
            ma_fonction(…) =  une certaine valeur
        où ma_fonction(…), du côté gauche du signe d'égalité
        est une fonction et non le nom d’une variable.
        

SyntaxError - used equal sign instead of colon
----------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error32.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax
       2: """
       3: 
    -->4: ages = {'Alice'=22, 'Bob'=24}
                         ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Il est possible que vous ayez utilisé un signe d'égalité (=) au lieu de deux points (:)
        pour attribuer des valeurs à une clé d'un dictionnaire
        avant ou exactement à la position indiquée par --> et ^.
        

SyntaxError - non-default argument follows default argument
-----------------------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: non-default argument follows default argument
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error33.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: """
       3: 
       4: 
    -->5: def test(a=1, b):
                  ^

    Cause probable basée sur les informations données par Python :
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


    Exception Python:
        SyntaxError: positional argument follows keyword argument
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error34.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: """
       3: 
       4: 
    -->5: test(a=1, b)
                   ^

    Cause probable basée sur les informations données par Python :
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


    Exception Python:
        SyntaxError: f-string: unterminated string
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error35.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: f-string: unterminated string
       2: """
       3: 
    -->4: print(f"Bob is {age['Bob]} years old.")
               ^

    Cause probable basée sur les informations données par Python :
        À l'intérieur d'une "f-string", qui est une chaîne de caractères préfixée de la lettre f,
        vous avez une autre chaîne de caractère qui débute soit avec un apostrophe (')
        ou des guillemets ("), mais n'est pas terminé par un autre caractère semblable.
        

SyntaxError - unclosed bracket
------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error36.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
        4: def foo():
        5:     return [1, 2, 3
        6: 
    --> 7: print(foo())
               ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Le symbole crochet '[' à la ligne 5 n'est pas fermé par le symbole correspondant.
        
            5:     return [1, 2, 3
                          ^
        

SyntaxError - unexpected EOF while parsing
------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: unexpected EOF while parsing
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python ne peut pas comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error37.py'.
    La fin du fichier a été atteinte et Python s'attendait à voir plus de code.
    
    
        5:     return [1, 2, 3,
        6: 
        7: print(foo())

    Cause probable basée sur les informations données par Python :
        Python nous dit que le il a atteint la fin du fichier
        et s'attendait à plus de contenu.
        
        Je vais essayer de donner un peu plus d'informations.
        
        Le symbole crochet '[' à la ligne 5 n'est pas fermé par le symbole correspondant.
        
            5:     return [1, 2, 3,
                          ^
        

SyntaxError - name is parameter and global
------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: name 'x' is parameter and global
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error38.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       3: 
       4: 
       5: def f(x):
    -->6:     global x
             ^

    Cause probable basée sur les informations données par Python :
        Vous avec inclus l'énoncé
        
                global x
        
        indiquant que 'x' est une variable définie en dehors d'une fonction.
        Vous utilisez également le même 'x' comme un argument pour cette
        fonction; un argument de fonction est une variable locale connue seulement
        à l'intérieur de cette fonction, ce qui est le contraire de ce que «global» sous-entendait.
        

SyntaxError - keyword as attribute
----------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error39.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
        9: a = A()
       10: 
       11: a.x = 1
    -->12: a.pass = 2
                ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous avez tenté d'utiliser le mot clé Python 'pass' comme attribut.
        Ceci n’est pas permis.
        
        

SyntaxError - content passed continuation line character
--------------------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: unexpected character after line continuation character
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error40.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: SyntaxError: unexpected character after line continuation character
       3: """
       4: 
    -->5: print(\t)
                   ^

    Cause probable basée sur les informations données par Python :
        Vous utilisez le caractère de continuation '\' en dehors d'une chaîne de caractères,
        et il est suivi par au moins un autre caractère.
        Je suppose que vous avez oublié de terminer la chaîne par un guillemet
        ou un apostrophe.
        
        

SyntaxError - keyword can't be an expression
--------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: keyword can't be an expression
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error41.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
        4: """
        5: 
        6: 
    --> 7: a = dict('key'=1)
                   ^

    Cause probable basée sur les informations données par Python :
        Vous avez probablement appelé une fonction avec un argument :
        
            une_fonction (invalide=quelque_chose)
        
        où «invalide» n'est pas un nom de variable valide dans Python
        soit parce qu'il commence par un nombre, soit est une chaîne,
        ou contenir un point, etc.
        
        

SyntaxError - invalid character in identifier
---------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid character in identifier
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error42.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       3: 
       4: # Robot-face character below
       5: 
    -->6: 🤖 = 'Reeborg'
          ^

    Cause probable basée sur les informations données par Python :
        Vous avez probablement utilisé un caractère unicode qui n'est pas autorisé
        dans le nom d'une variable dans Python.
        Cela comprend de nombreux emojis.
        
        

SyntaxError - keyword cannot be argument in def - 1
---------------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error43.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: """
       3: 
       4: 
    -->5: def f(None=1):
                   ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous avez tenté d'utiliser le mot clé Python 'None' comme argument
        dans la définition d'une fonction.
        Ceci n’est pas permis.
        
        

SyntaxError - keyword cannot be argument in def - 2
---------------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error44.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: """
       3: 
       4: 
    -->5: def f(x, True):
                      ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous avez tenté d'utiliser le mot clé Python 'True' comme argument
        dans la définition d'une fonction.
        Ceci n’est pas permis.
        
        

SyntaxError - keyword cannot be argument in def - 3
---------------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error45.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: """
       3: 
       4: 
    -->5: def f(*None):
                    ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous avez tenté d'utiliser le mot clé Python 'None' comme argument
        dans la définition d'une fonction.
        Ceci n’est pas permis.
        
        

SyntaxError - keyword cannot be argument in def - 4
---------------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error46.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: """
       3: 
       4: 
    -->5: def f(**None):
                     ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous avez tenté d'utiliser le mot clé Python 'None' comme argument
        dans la définition d'une fonction.
        Ceci n’est pas permis.
        
        

SyntaxError - delete function call
----------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: can't delete function call
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error47.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: """
       3: 
       4: 
    -->5: del f(a)
             ^

    Cause probable basée sur les informations données par Python :
        Vous avez tenté de supprimer un appel de fonction
            del f(a)
        au lieu de supprimer le nom de la fonction
            del f
        

Walrus operator does not exist - yet
------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque Python ne peut pas comprendre votre code.
    
    Python peut seulement comprendre le code du fichier
    'TESTS:\syntax\raise_syntax_error_walrus.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Prior to Python 3.8, this should raise SyntaxError: invalid syntax"""
       2: 
    -->3: print(walrus := True)
                       ^

    Je n'ai pas assez d'informations de Python:
        Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous semblez utiliser l'opérateur :=, parfois appelé l'opérateur morse
        (walrus operator, en anglais). Cet opérateur nécessite l'utilisation de
        Python 3.8 ou une version plus récente. Vous utilisez la version  3.7.
        
        
