
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

Friendly-traceback version: 0.0.10a
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
        où <1>, sur le côté gauche du signe égal, est ce que Python
        appelle un 'literal', c'est-à-dire soit une chaîne de caractères ou un nombre,
        et non le nom d’une variable.  Peut-être que vous vouliez plutôt écrire :
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
        où <1>, sur le côté gauche du signe égal, est ce que Python
        appelle un 'literal', c'est-à-dire soit une chaîne de caractères ou un nombre,
        et non le nom d’une variable.
        
        

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
        Le symbole parenthèse ')' à la ligne 6 n'a pas de symbole ouvrant qui lui correspond.
        

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
        Le symbole parenthèse '(' à la ligne 2 n'est pas fermé par le symbole correspondant.
        

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
        Le symbole parenthèse '(' à la ligne 2 n'est pas fermé par le symbole correspondant.
        

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
        Le symbole crochet ']' à la ligne 2 ne correspond pas au symbole parenthèse '(' à la ligne 2.
        

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
        
