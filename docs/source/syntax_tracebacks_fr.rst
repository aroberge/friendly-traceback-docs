
Friendly SyntaxError tracebacks - en Français
=============================================

Le but principal de friendly-traceback est de fournir des rétroactions plus
conviviales que les fameux **tracebacks** de Python lorsqu'une exception survient.
Ci-dessous, on peut voir quelques exemples, uniquement pour les
exceptions de type SyntaxError; les autres sont couvertes dans une autre page.
Le but éventuel est de documenter
ici tous les exemples possibles tels qu'interprétés par friendly-traceback.

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

Friendly-traceback version: 0.0.18a
Python version: 3.7.3



SyntaxError - Assign to keyword
-------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error1.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """ Should raise SyntaxError"""
       2: 
    -->3: def = 2
              ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous essayiez d’assigner une valeur au mot clé Python 'def'.
        Ceci n’est pas permis.
        
        

SyntaxError - Missing colon 1
-----------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error2.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: if True
                 ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous avez écrit un énoncé débutant avec
        'if' mais vous avez oublié d’ajouter deux points ':' à la fin.
        
        

SyntaxError - Missing colon 2
-----------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error3.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: while True  # a comment
                                 ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous vouliez débuter une boucle 'while'
        mais vous avez oublié d’ajouter deux points ':' à la fin.
        
        

SyntaxError - elif, not else if
-------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error4.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: 
       3: if False:
       4:     pass
    -->5: else if True:
                ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous avez écrit 'else if'
        au lieu d'utiliser le mot-clé 'elif'.
        
        

SyntaxError - elif, not elseif
------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error5.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: 
       3: if False:
       4:     pass
    -->5: elseif True:
                    ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous avez écrit 'elseif'
        au lieu d'utiliser le mot-clé 'elif'.
        
        

SyntaxError - malformed def statment - 1
----------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error6.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: def :
              ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
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
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error7.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: def name  :
                    ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
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
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error8.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError"""
       2: 
    -->3: def ( arg )  :
              ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
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
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error9.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: can't assign to literal"""
       2: 
    -->3: 1 = a
         ^

    Ma meilleure hypothèse :
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
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error9a.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: can't assign to literal"""
       2: 
    -->3: 1 = 2
         ^

    Ma meilleure hypothèse :
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
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error10.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: import pen from turtle
                        ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
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
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error11.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: EOL while scanning string literal"""
       2: 
    -->3: alphabet = 'abc
                         ^

    Ma meilleure hypothèse :
        Vous aviez commencé à écrire une chaîne de caractères
        avec un guillemet simple ou double, mais n'avez jamais
        terminé la chaîne avec un autre guillemet sur cette ligne.
        

SyntaxError - assignment to keyword (None)
------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: can't assign to keyword
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error12.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: cannot assign to None in Py 3.8
       2:    and can't assign to keyword before."""
       3: 
    -->4: None = 1
         ^

    Ma meilleure hypothèse :
        None est une constante dans python; vous ne pouvez pas lui assigner une valeur.
        
        

SyntaxError - assignment to keyword (__debug__)
-----------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: assignment to keyword
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error13.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: cannot assign to __debug__ in Py 3.8
       2:    and assignment to keyword before."""
       3: 
    -->4: __debug__ = 1
         ^

    Ma meilleure hypothèse :
        __debug__ est une constante dans python; vous ne pouvez pas lui assigner une valeur.
        
        

SyntaxError - unmatched closing parenthesis
-------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error14.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       3: """
       4: a = (1,
       5:     2,
    -->6:     3, 4,))
                    ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Le symbole parenthèse ')' à la ligne 6 n'a pas de symbole ouvrant qui lui correspond.
        
            6:     3, 4,))
        
        

SyntaxError - unclosed parenthesis
----------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error15.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: x = int('1'
    -->3: if x == 1:
                   ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Le symbole parenthèse '(' à la ligne 2 n'est pas fermé par le symbole correspondant.
        
            2: x = int('1'
        
        

SyntaxError - unclosed parenthesis - 2
--------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error15a.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: a = (b+c
    -->3: d = a*a
          ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Le symbole parenthèse '(' à la ligne 2 n'est pas fermé par le symbole correspondant.
        
            2: a = (b+c
        
        

SyntaxError - mismatched brackets
---------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error16.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
    -->2: x = (1, 2, 3]
                      ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Le symbole crochet ']' à la ligne 2 ne correspond pas au symbole parenthèse '(' à la ligne 2.
        
            2: x = (1, 2, 3]
        

SyntaxError - mismatched brackets - 2
-------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error16a.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: x = (1,
       3:      2,
    -->4:      3]
                ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Le symbole crochet ']' à la ligne 4 ne correspond pas au symbole parenthèse '(' à la ligne 2.
        
            2: x = (1,
        
            4:      3]
        

SyntaxError - print is a function
---------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: Missing parentheses in call to 'print'. Did you mean print('hello')?
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error17.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: Missing parentheses in call to 'print' ..."""
    -->2: print 'hello'
                      ^

    Ma meilleure hypothèse :
        Peut-être que vous avez besoin d'écrire print('hello') ?
        
        Dans l'ancienne version de Python, «print» était un mot clé.
        Maintenant, «print» est une fonction; vous devez utiliser des parenthèses pour l'invoquer.
        

SyntaxError - Python keyword as function name
---------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error18.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: def pass():
                 ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Vous avez tenté d'utiliser le mot clé Python 'pass' comme nom de fonction.
        Ceci n’est pas permis.
        
        

SyntaxError - break outside loop
--------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: 'break' outside loop
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error19.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: 'break' outside loop"""
       2: 
       3: if True:
    -->4:     break
             ^

    Ma meilleure hypothèse :
        Le mot-clé Python 'break' ne peut être utilisé qu'à l'intérieur d'une boucle 'for' ou à l'intérieur d'une boucle 'while'.
        

SyntaxError - continue outside loop
-----------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: 'continue' not properly in loop
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error20.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: 'continue' outside loop"""
       2: 
       3: if True:
    -->4:     continue
             ^

    Ma meilleure hypothèse :
        Le mot-clé Python 'continue' ne peut être utilisé qu'à l'intérieur d'une boucle 'for' ou à l'intérieur d'une boucle 'while'.
        

SyntaxError - quote inside a string
-----------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error21.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: message = 'don't'
                         ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
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
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error22.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: 
       3: a = {'a': 1,
       4:      'b': 2
    -->5:      'c': 3,
                 ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Il est possible que vous ayez oublié une virgule entre les éléments d'un ensemble (set)
        ou un dict avant la position indiquée par --> et ^.
        

SyntaxError - missing comma in a set
------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error23.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: a = {1, 2  3}
                     ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Il est possible que vous ayez oublié une virgule entre les éléments d'un ensemble (set)
        ou un dict avant la position indiquée par --> et ^.
        

SyntaxError - missing comma in a list
-------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error24.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: a = [1, 2  3]
                     ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Il est possible que vous ayez oublié une virgule entre les éléments d'une liste
        avant la position indiquée par --> et ^.
        

SyntaxError - missing comma in a tuple
--------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error25.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
    -->3: a = (1, 2  3)
                     ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Il est possible que vous ayez oublié une virgule entre les éléments d'un tuple,
        ou entre les arguments d'une fonction, avant la position indiquée par --> et ^.
        

SyntaxError - missing comma between function args
-------------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error26.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax"""
       2: 
       3: 
    -->4: def a(b, c d):
                     ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Il est possible que vous ayez oublié une virgule entre les éléments d'un tuple,
        ou entre les arguments d'une fonction, avant la position indiquée par --> et ^.
        

SyntaxError - can't assign to function call - 1
-----------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: can't assign to function call
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error27.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       3: Python 3.8: SyntaxError: cannot assign to function call
       4: """
       5: 
    -->6: len('a') = 3
         ^

    Ma meilleure hypothèse :
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
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error28.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       3: Python 3.8: SyntaxError: cannot assign to function call
       4: """
       5: 
    -->6: func(a, b=3) = 4
         ^

    Ma meilleure hypothèse :
        Vous avez écrit une expression comme
            ma_fonction(…) =  une certaine valeur
        où ma_fonction(…), du côté gauche du signe d'égalité
        est une fonction et non le nom d’une variable.
        

SyntaxError - used equal sign instead of colon
----------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error29.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: invalid syntax
       2: """
       3: 
    -->4: ages = {'Alice'=22, 'Bob'=24}
                         ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Il est possible que vous ayez utilisé un signe d'égalité (=) au lieu de deux points (:)
        pour attribuer des valeurs à une clé d'un dictionnaire
        avant ou exactement à la position indiquée par --> et ^.
        

SyntaxError - non-default argument follows default argument
-----------------------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: non-default argument follows default argument
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error30.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: """
       3: 
       4: 
    -->5: def test(a=1, b):
                  ^

    Ma meilleure hypothèse :
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
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error31.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       2: """
       3: 
       4: 
    -->5: test(a=1, b)
                   ^

    Ma meilleure hypothèse :
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
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error32.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       1: """Should raise SyntaxError: f-string: unterminated string
       2: """
       3: 
    -->4: print(f"Bob is {age['Bob]} years old.")
               ^

    Ma meilleure hypothèse :
        À l'intérieur d'une "f-string", qui est une chaîne de caractères préfixée de la lettre f,
        vous avez une autre chaîne de caractère qui débute soit avec un apostrophe (')
        ou des guillemets ("), mais n'est pas terminé par un autre caractère semblable.
        

SyntaxError - unclosed bracket
------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: invalid syntax
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error33.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
        4: def foo():
        5:     return [1, 2, 3
        6: 
    --> 7: print(foo())
               ^

    Ma meilleure hypothèse :
        Important: Python ne nous a pas donné beaucoup d'informations concernant
        la cause de l'erreur. Nous faisons un effort ci-dessous pour deviner ce que
        a mal tourné, mais nous pourrions deviner incorrectement.
        
        Le symbole crochet '[' à la ligne 5 n'est pas fermé par le symbole correspondant.
        
            5:     return [1, 2, 3
        
        

SyntaxError - unexpected EOF while parsing
------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: unexpected EOF while parsing
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python ne peut pas analyser correctement le fichier 'TESTS:\syntax\raise_syntax_error34.py'.
    La fin du fichier a été atteinte et Python s'attendait à voir plus de code.
    
    
        5:     return [1, 2, 3,
        6: 
        7: print(foo())

    Ma meilleure hypothèse :
        Important: Python nous a donné le message d'information suivant
        sur la cause possible de l'erreur :
        
            unexpected EOF while parsing
        
        Cependant, nous ne reconnaissons pas cette information.
        Nous allons tenter ce deviner la cause de l'erreur
        mais il est possible que nous allons deviner incorrectement.
        Le symbole crochet '[' à la ligne 5 n'est pas fermé par le symbole correspondant.
        
            5:     return [1, 2, 3,
        
        

SyntaxError - name is parameter and global
------------------------------------------

.. code-block:: none


    Exception Python:
        SyntaxError: name 'x' is parameter and global
        
    Une exception de type SyntaxError se produit lorsque python ne peut pas comprendre votre code.
    
    Python peut seulement analyser le fichier 'TESTS:\syntax\raise_syntax_error35.py'
    jusqu'à l'endroit indiqué par --> et ^.
    
       3: 
       4: 
       5: def f(x):
    -->6:     global x
             ^

    Ma meilleure hypothèse :
        Vous avec inclus l'énoncé
        
                global x
        
        indiquant que 'x' est une variable définie en dehors d'une fonction.
        Vous utilisez également le même 'x' comme un argument pour cette
        fonction; un argument de fonction est une variable locale connue seulement
        à l'intérieur de cette fonction, ce qui est le contraire de ce que «global» sous-entendait.
        
