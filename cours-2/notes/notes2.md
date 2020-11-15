---
title: Structures itératives
author: Hugo Leblanc
date: Cours 2
pandocomatic_:
  use-template: 
  - handout
...

# Structure de contrôle itérative^[Le terme boucle est synonyme]
Les structures de contrôle^[[Loop Control Statements](https://www.mathworks.com/help/matlab/matlab_prog/loop-control-statements.html)] permet de répétés une série d'instructions sous une condition ou la configuration d'un compteur. Cela nous évites à avoir à répété les mêmes instructions dans nos programmes.

## `while`
La boucle `while`^[[while](https://www.mathworks.com/help/matlab/ref/while.html)] répette une série d'instruction tant qu'une condition est respectés. 

~~~ {title="Structure du while"}
while ¬\mlplaceholder{condition}¬
    ¬\mlplaceholder{instructions}¬
end
~~~
~~~ {title="Exemple du while"}
while x > 5
    fprintf('%g plus grand que 5.', x)
    x = x - 1
end
~~~

La boucle `while` ressemble beacoup à la conditionnelles `if`. La différence fondamentale est, qu'après l'exécution des instructions de la structure de contrôle, le programme remonte au début de la boucle `while` et réévalue la condition et exécute le bloc d'instruction tant que^[while en anglais est "tant que"] la condition est vrai^[Chaque "tour" de la boucle est nommé un itération de la boucle].

Une attention particulière doit être apporté avec la relation entre la condition et les instruction de la boucle. Il faut toujours avoir une méthode de 'briser' la boucle. Habituellement en modifiant la valeur d'une des variables utiilsé dans la condition durant les instructions de la boucle.

## Somme cumulative et accumulation
Un concept très souvent utiilsé est le concept d'accumulation à l'intérieur d'une variable dans un boucle. Le principe est d'avoir l'assignation d'une variabla qui reçoit le contenu d'elle-même avec d'autres informations.

Le cas le plus simple, mais grandement utilisé est l'incrémentation d'une variable. L'incrémentation est l'ajout de la valeur 1 à une variable à répétition. L'incrémentation est souvent utilisé pour avoir un compteur  

~~~ {title="Incrémentation d'une variable"}
x = 4
while x < 10
    x = x + 1
    fprintf('x = %g', x)
end
~~~

## `for`
La boucle `for`^[[for](https://www.mathworks.com/help/matlab/ref/for.html)] permet de configuer un compteur qui gère le nombre d'itérations de la boucle. La configuration du compteur à beaucoup d'option et donne beaucoup de possibilités au programmeur.

Dans sa version la plus simple, le compteur incrémente de 1^[L'incrémentation est l'ajout d'une valeur à la valeur déjà existante dans la variable.] à chaque itération de la boucle et va de la valeur de début jusqu'à la valeur de fin.

~~~ {title="Structure du for"}
for ¬\mlplaceholder{compteur}¬ = ¬\mlplaceholder{début}¬:¬\mlplaceholder{fin}¬
    ¬\mlplaceholder{instructions}¬
end
~~~
~~~ {title="Exemple du for"}
for i = 1:5
    fprintf('%g est la valeur de i.\n', i)
end
~~~

Les informations de début et de fin sont des expressions, on peut donc facilement configurer avec l'utilisation de variable comme élément de début et de fin.

~~~ {title="Exemple du for avec une fin dynamique"}
nTour = input('Le nombre de tours à faire dans la boucle')
for iTour = 1:nTour
    fprintf('Tour no %g.\n', iTour)
end
~~~

Par conventtion, l'identificateur du compteur est la variable `i` pour un compteur sans contexte ou le contexte préfixé du `i`. Cela nous permet de 

Il est aussi possible de configuer le saut entre les itérations de la boucle. On ajoute le saut^[Le saut est aussi une expression comme le début et la fin.] en ajoutant ça valeur entre le début et la fin dans la configuration du compteur.


~~~ {title="Structure du for avec saut"}
for ¬\mlplaceholder{compteur}¬ = ¬\mlplaceholder{début}¬:¬\mlplaceholder{saut}¬:¬\mlplaceholder{fin}¬
    ¬\mlplaceholder{instructions}¬
end
~~~
~~~ {title="Exemple du for"}
for i = 1:5
    fprintf('%g est la valeur de i.\n', i)
end
~~~
~~~ {title="Exemple du for avec un saut"}
for i = 2:2:10
    fprintf('%g est la valeur de i.\n', i)
end
~~~

## Différence entre `while` et `for`
À la base, toutes les boucles peuvent être des `while`, le `for` apporte seulement de l'automatisation dans la configuration du compteur.

La différence majeure est donc de voir si l'on peut se faciliter la vie en utilisant le `for`. Nous allons utiliser le `for` quand nous sommes capable de déterminer ou calculer le nombres d'itérations requises^[Un bon indice est l'utilisation d'une variable compteur qui incrémente à chaque itération.] quand le programme arrive à la boucle. Si il est impossible de déterminer le nombre d'itérations, nous utiliserons le `while`

# Opérateurs logiques
Les opérations logique^[[Logical Operations](https://www.mathworks.com/help/matlab/logical-operations.html)] sont des opérations qui travaillent sur des opérandes^[Un opérande est les valeurs utilisées avec une opération. Dans 3+4, une opération d'addition, les opérandes sont 3 et 4 avec l'opérateur +.] logiques.

Nous utiliserons les opérateurs logiques pour combiner plusieurs comparaisons logiques ensemble.

Les opérateurs logiques peuvent être indroduites dans tous les types d'expressions, leur priorité d'opération^[[Operator Precedence](https://www.mathworks.com/help/matlab/matlab_prog/operator-precedence.html)] s'ajoute après les opérateurs relationnels.

## Opérations ET `&&`, OU `||`
Les deux opérations logique ET^[[and, &](https://www.mathworks.com/help/matlab/ref/and.html)] et OU^[[or, |](https://www.mathworks.com/help/matlab/ref/or.html)] sont utilisé pour combiné deux résultats logiques. Puisque les opérandes sont logiques, seules quatre possibilités sont à étudier. Le ET logique^[Aussi appellé conjonction.] permet d'avoir un résultat vrai si et seulement si les deux opérandes sont vrais. Le OU logique^[Aussi appellé la disjonction.] permet d'avoir un résultat vrai si au moins un des deux opérandes est vrais. Nous somme capable de représenté ses différents cas dans une table de vérité.

`A` | `B` |   | `A && B` | `A || B`
----|-----|---|:--------:|:-------:
0   | 0   |   | 0        | 0
0   | 1   |   | 0        | 1
1   | 0   |   | 0        | 1
1   | 1   |   | 1        | 1

~~~ {title="Exemple de détection d'une valeur x entre 5 et 10"}
if x >= 5 && x <= 10
    fprintf('x est entre 5 et 10.\n')
end
~~~

~~~ {title="Exemple de condition pour x ou y plus grand que 0"}
if x > 0 || y > 10
    fprintf('x ou y plus grand que 0.\n')
end
~~~

Il faut faire attention avec les priorités d'opérations, les opérations logiques demandes d'avoir des opérations relationnels complète comme opérande^[Par exemple, on ne peut pas écrire x > 5 && < 10].

## Négation NOT `~`
La négration NOT^[[not, ~](https://www.mathworks.com/help/matlab/ref/not.html)] est une opération unitaire^[L'opération unitaire à qu'un seul opérande.] qui inverse le contenu logique.

`A` | `~A`
----|:---:
0   | 1
1   | 0

~~~ {title="Exemple de détection de x qui n'est pas entre 5 et 10"}
if ~(x >= 5 && x <= 10)
    fprintf('x est entre 5 et 10.\n')
end
~~~

## Court-circuitage `&&` et `||`
Il est possible d'utiliser les opérateur `&` et `|` avec un ou deux opérateurs consécutivement. Pour des raisons d'efficacités, nous utiliserons les doubles opérateurs qui incluent un mécanique de court-circuitage^[[Logical Operators: Short-Circuit && ||](https://www.mathworks.com/help/matlab/ref/logicaloperatorsshortcircuit.html)]. Le court-circtuigage permet à MATLAB de ne pas avoir à évalué les deux côtés de l'opération si la réponse peut être trouvé en regardant le premier opérande.


# Appel et utilisation de fonctions
MATLAB comporte des milliers de fonctions prête à réglé plusieurs problème de bases. Une fonction est un bloc de code pouvant réponde à une tâche simple et précise. Toutes les fonctions utilisent les même modalités d'utilisation. L'utilisation d'une fonction est appellé "L'appel d'une fonction"^[[Calling Functions](https://www.mathworks.com/help/matlab/learn_matlab/calling-functions.html)].

L'appel de fonction de base utilise le nom de la fonction dans une instruction pour invoquer. Le programme va exécuter le contenue complet de la fonction appellé et ensuite retourner à son exécution normale.

~~~ {title="Exemple d'appel de fonction avec leurs noms."}
clear
clc
~~~

Les deux modalités des appels sont:

* Les paramètres d'entrées;
* Le retour de la fonction.

## Paramètres d'entrés
Les paramètres d'entrés sont les éléments préalables qu'une fonction à besoin pour être exécuté. Les paramètres d'entrés sont envoyés en utilisant une paire de parenthèses après le nom de la fonction dans l'instruction. Il est possible d'avoir plus qu'un paramètre en les délimitant avec une virgule.

Chaque paramètre est une expression qui sera évalué avant d'être envoyé à la fonction. Cela nous permet donc d'utilisé des équations ou des variables comme paramètre d'entré.

~~~ {title="Exemple d'appel de fonction avec des paramètres."}
% Affiche Bonjour valeur 35.
fprintf('Bonjour valeur %g\n', 15 + 20)
clear('x')
~~~

## Retour de fonction
Les fonctions ont la capacité d'envoyé un retour^[Cela s'apparente à la "réponse" de la fonction]. Le retour peut ensuite être utilisé dans notre programme.

L'utilisation d'une fonction avec un retour dans un expression entraîne le retour de la fonction à remplacé l'appel à l'intérieur de la fonction appellé. Nous pouvons donc utilisé le retour d'une fonction comme résultat d'assignation ou même comme paramètre d'entrée d'une autre fonction.

~~~ {title="Exemple d'appel de fonction avec des retours."}
x = sin(0.3)
% Utilisation d'un retour dans les paramètres d'une autre fonction.
fprintf('Le restant entre %g et %g est %g, 45, 17, mod(45,17))
~~~