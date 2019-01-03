---
title: INF135 - Fonctions et tests
author: Hugo Leblanc
date: Cours 3
pandocomatic_:
  use-template: 
  - presentation
  - presentation-handout
...

# Fonctions
* Les fonctions sont des séries d'instructions contenues dans un ensemble pouvant être facilement re-utilisé. Par convention, la fonction doit faire une tâche simple et précise;
* Les fonctions peuvents demandés des paramètres (ou arguments) d'entrées. Ce sont des informations préalables aux calculs de la fonction;
* Les fonctions peuvent émettrent des réponses que l'on appel retour.

# Présentation d'une fonction minimale
~~~MATLAB
function nomFonction
    instructions
end
~~~

* Une fonction est dans un fichier de fonctions qui porte le même nom que le nom de la fonction;
* La fonction peut ensuite être appellé par son nom de d'autre programme.

# Paramètres d'entrées
* Une fonction peut demander des paramètres d'entrées;
* Ceux-ci seront dans un liste après le nom de la fonctions entre parenthèses délimités par une virgule;
* Le paramètres d'entrées seront fournies par l'appelant de la fonction et peuvent donc être utilisé à l'intérieur des instruction de la fonctions sans être assigné préalablement.

~~~MATLAB
function fcnAvecIn(var1, var2)
    fprintf('%g', var1 * var2)
end
~~~

# Retours
* La fonction peut retourner un résultat qui sera utilisable par l'appelant de la fonction.
* Le retour se retrouvé à gauche du nom de la fonction entre braquette carrés suivi d'une assignation.
* Le retour élabore une variable de retour dans laquelle la "réponse" de la fonction est assigné.
* Une fonction qui ne contient pas de retour est aussi nommée une procédure.

~~~MATLAB
function [monRetour] = fcnAvecRetour
    monRetour = ...
end
~~~

# Exercice 1
* Écrivez une fonction qui trouve l’aire d’un triangle à partir de sa base et sa hauteur.
* Écrivez une fonction qui détermine si un nombre est impaire. Indice : utilisez la fonction mod.

# Multiple retours
* Il est possible d'avoir plusieurs retours à une fonction. La création de la fonctions garde les mêmes règles, plusieurs valeurs de retours délimité par un virgule seront désigné et ensuite assigné durant la fonction.
* L'appel d'une fonction à multi-retours demande de faire une multi-assignation.
~~~MATLAB
function [retour1, retour2] = fcnMultiRetour
    retour1 = ...
    retour2 = ...
end

% L'appel de la fonction utilise la multi-assignation
[a, b] = fcnMultiRetour
~~~

# Présentation de l'en-tête d'une fonction
~~~MATLAB
function [retour1] = nomFonction(arg1, arg2)
% Description générale de la fonction
%
% Args:
%   arg1 (double) - Description de l'arg1
%   arg2 (logical) - Description de l'arg2
% Returns:
%   double: Description de retour1
% Example:
%   >> nomFonction(4,6)
%       ans = 
%       34

instructions
end
~~~

# Portée des fonctions
* Une fonction qui est la première dans son document `.m` est considérée à portée globale. Tous programmes et scripts pourront l’utiliser.
* Une fonction qui n'est pas la première dans son document `.m` est considérée à portée locale. Seul les sous-programmes dans le même fichier pourront l’utiliser.

# Durée de vies des variables
* Tout ce qui se passe à l'intérieur des fonctions est détruit après l'appel de la fonction;
* Toutes déclaration de variables à l'intérieur d'une fonction est détruite après l'appel de la fonction;
* Seule la valeur de retour est renvoyée.

# Passage par valeurs
* Les paramètres et les retours sont renommé pour la durée de la fonction;
* Seul leur valeurs seront transféré entre la fonction et l'appelant;
* Les noms des paramètres et des retours n'ont aucune incidence;
* L'ordre des paramètre et des retours est ce qui sera considéré.

# Exercice 2
* Quel est le résultat de l'affichage du script `passageParValeurTest.m`

~~~MATLAB
% passageParValeurTest.m
x = 4;
z = 8;
y = 6;
x = passageParValeur(y,x);
fprintf('La valeur de x,y et z sont : %g %g %g\n', x, y, z);
~~~

~~~MATLAB
% passageParValeur.m
function  [z] = passageParValeur(x, y)
    x = x + 2;
    y = y - 2;
    z = x - y + 2;
end
~~~

# Variables globales
* Une variable global permet de lié une variable de l’espace de travail normal à l’espace de travail d’une fonction;
* La variable doit être indiquer comme globale dans l’espace de travail dans les deux endroit avec la command `global nomVar` pour être lié;
* Sauf avis contraire, l’utilisation de variable globale est **interdite** dans le cours.

# Tests
* Pour assurer la bonne opérations de nos fonctions, des tests seront implémentés;
* Un test est un script qui, par convention, utilise le nom du programme à tester suivie du mot `Test`;
* La fonction `assert` teste une condition. La fonction ne fait rien si la condition est vrai et génère une erreur si la condition est fausse
* Le script de tests utilise la fonction `assert` pour faire des appels de la fonctions à tester avec des paramètres d'entéres arbitraire;
* Les fonction de tests n'ont pas de commentaires.

# Exemple de tests
~~~MATLAB
% Tests pour la fonctions mod
assert(mod(5, 3) == 2)
assert(mod(23, 1) == 0)
assert(mod(4, 12) == 4)
~~~

# Exercice 3
* Écrivez des scripts de tests pour les fonctions de calcul d'aire et de détection de nombre impaire.

# Tests de valeurs fractionnaires
* Les valeurs fractionnaires sont plus difficiles à tester car la comparaisont de valeurs fractionnaires est assez difficile;
* Pour tester des valeurs fractionnaires, des valeurs différentielles absolues seront utilisées pour faire le test.

~~~MATLAB
% Tests de la fonction sin
assert(abs(sin(1) - 0.8415) < 0.0001)
assert(abs(sin(2) - 0.9093) < 0.0001)
assert(abs(sin(1.5) - 0.9975) < 0.0001)
~~~
