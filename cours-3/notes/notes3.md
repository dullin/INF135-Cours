---
title: Fonctions et tests
author: Hugo Leblanc
date: Cours 3
pandocomatic_:
  use-template: 
  - handout
...

# Fonctions
Les fonctions sont des séries d'instructions contenues dans une ensemble pouvant être facilement re-utilisé. La fonction à un nom avec lequel on peux l'exécuté^[L'exécution d'une fonction est définie comme étant "L'appel de la fonction".] à l'intérieur d'autres instructions.

Le but des fonctions est multiple. Un premier est de facilité la réutilisation de code. Un deuxième est de modularisé un problème pour être plus accessible. Pour arriver à ces buts, les fonctions se veulent remplir une tâche simple et précise. Si ce n'est pas le cas, la fonction devrait être divisé en fonction plus simple.

## Modalités d'utilisation
Les fonctions ont deux mécanismes reliés à leur utilisation:

* Les paramètres d'entrées qui permettent à la fonction de recevoir des informations de l'extérieur.
* Les retours qui envoient les réponses généré à l'intérieur de la fonction.

Les paramètres se veulent des informations préalables à l'utilisation de la fonction. Celle-ci devrait être incapable d'être complété si les paramètres ne sont pas fourni^[À ne pas confondre avec des variables additionneles possibles durant le création de la fonction.].

Contrairement aux scripts, il n'y aura pas de saisit avec `input` ni d'affichage avec `fprintf` dans les fonctions^[Il reste possible d'avoir des saisit et affichage si expressément demandé dans la fonction.]. Les mécanismes de paramètres d'entrées et de retours seront nos méthodes de communication avec la fonction.

# Création de fonctions
Les fonctions^[[Create Functions in Files](https://www.mathworks.com/help/matlab/matlab_prog/create-functions-in-files.html)] se retrouveront dans un nouveau fichier qui se vera cotoyé nos scripts dèjà existant. Les fichiers de fonctions auront l'extension `.m` comme les scripts, ils seront différencié par leur contenu.

## Fonction minimale
À son plus simple, la fonction^[[function](https://www.mathworks.com/help/matlab/ref/function.html)] doit contenir trois éléments:

* La première instruction doit être la mot `function`^[La première ligne est appellé la 'déclaration de la fonction'];
* Suivant le mot-clé `function` on a le nom de la fonction^[Le nom de la fonction doit être le même que celle du fichier. Il faut uitiliser les reègles des identificateurs.];
* Le mot clé `end` à la fin du fichier.

Les instructions de la fonctions se retrouve à l'intérieur de ces deux bornes. Elle seront exécutés de manière séquentielle comme un script mais nous verrons qu'il existe des différences fondamentales entre les deux.

~~~ {title="Fonction minimale"}
function maFonction
  % Instructions
end
~~~

Une attention importante doit être apporté au nom que l'on donne à nos fonctions pour ne pas remplacer des fonctions déjà existante de MATALB. Si tel est le cas, MATLAB va prendre priorité sur nos fonctions^[[Function Precedence Order](https://www.mathworks.com/help/matlab/matlab_prog/function-precedence-order.html)] ce qui peut causer des troubles majeurs dans nos programmes.

# Configuration de la fonction

## Paramètres d'entrés
Les paramètres d'entrées sont les informations préalables que la fonction à besoin pour réussir ses tâches. Les informations sont donnés par l'appelant et utilisé à l'intérieur de la fonction comme si les informations étaient déjà déclaré en remplis. La liste de paramètres d'entrés^[Le paramètres d'entrés sont des identificateurs et utilisent les mêmes règles de nommages.] se situe sur la première ligne de notre fonction, entre parenthèse, après le nom de la fonction.

~~~ {title="Fonction avec paramètres"}
function fcnAvecParam(param1, param2)
  fprintf('Première valeur: %g deuxième %g', ...
    param1, param2)
end

% Instruction d'appel de la fonction.
% À être utiilsé dans la fenêtre de commande.
fcnAvecParam(34, 56)
~~~

Dans l'exmple plus haut, les valeurs 34 et 56 sont envoyés à la fonction. Ces valeurs seront donc assignés aux deux paramètres dans l'ordre de paramètres donnes. La valeur 34 sera donc assigné à `param1` et 56 à `param2`. Cela permet ensuite l'utilisation de ses paramètres dans des expressions sans erreurs.

À l'intérieur de la fonction, les paramètres d'entrées peuvent être modifiés au besoin mais il faut faire attention à la durée de vie des variables (voir section ci-dessous).

## Retours
Le but de la majorité des fonctions est de retourné une "réponse". Pour accomplir cette tâche, un retour doit être configurer dans la création de la fonciton. L'utilisation du retour se faire en deux étapes:

* Indique le nom d'une variable de retour dans le prototype. Le nom se situe à gauche du nom de la fonction, entre braquettes carrés
* Assigne une variable à la valeur de retour durant les instructions de la fonction.

L'indication d'une variable dans la déclaration est un contrat avec la fonction. On indique à MATLAB qu'une variable avec le nom de la variable de retour sera assigné durant les instructions de la fonction.

~~~ {title="Fonction avec un retour"}
function [mult] = multiplication(a, b)
mult = a * b;
end
~~~

Il est possible d'avoir comme retour un paramètre d'entré. Ce genre de fonction est utiilsé pour "mettre à jours" une variable donné comme paramètre d'entré.

~~~ {title="Fonction avec le paramètre d'entré comme retour"}
function [a] = ajoute(a, b)
a = a + b;
end
~~~

## Multiple retours
Il est possible d'avoir plusieurs retours de la même fonction. Pour ce faire, on indique une liste de variables de retours dans la déclaration de la fonction. Il nous est donc du de remplir chacune des variables de retours durant les instructions de la fonction.

Pour recevoir des multiple retours, il faut utilisé une mutli-assignation. L'utilisation de la même syntaxe que la déclaration avec les braquette carré permet de faire une instruction de multi-assignation des retours d'une fonction^[Si la mutli-assignation n'est pas utilisé, seul le premier retour est reçu.]. L'ordre des retours est la priorité durant l'assignation. Il est possible d'ignorer^[[Ignore Function Outputs](https://www.mathworks.com/help/matlab/matlab_prog/ignore-function-outputs.html)] certains retours inutilisés, on remplace la variable d'assignation par un tilde `~`.

~~~ {title="Fonction à mutli-retours et instruciton d'assignation"}
function [a, b] = addSub(x, y)
a = x + y;
b = x - y;
end

% Exemple d'appel avec multi-assignation.
[un, deux] = addSub(15, 56)
% Ignore le premier retour.
[~, deux] = addSub(15, 56)
~~~

# Concepts d'utilisation des fonctions

## Fonction locale
Les fonctions créés dans des fichiers séparés qui portent le même que la fonctions sont à portées globales. La portée globale indique que n'importe qui peut faire appel à la fonction tant que celle-ci est visible à MATALB^[Habituellement, la visibilité est atteinte en ayant la fonction dans le dossier courant.].

Il est possible d'avoir des fonctions à portée locale. Pour se faire, la fonction doit être ajouté à un fichier de fonction ou un script déjà existant. La fonction aura une portée locale; seulement le fichier courant pourra faire appel à la fonction locale.

## Contexte et durée de vies des variables
La création de variable est séparé entre contexte à l'utilisation de fonction. De base, il existe un contexte^[MATALB nomme les contextes "workspace".] dans lequel les scripts et la fenêtre de commande peuvent créer des variables. Quand une fonction est appellé^[[Base and Function Workspaces](https://www.mathworks.com/help/matlab/matlab_prog/base-and-function-workspaces.html)], ce contexte est mis de côté et un nouveau contexte est créé pour la durée de l'exécution de la fonction. Cela implique deux éléments majeurs à l'utilisation de fonctions :

* Seules les variables déclaré à l'intérieur d'une fonction sont disponible durant son exécution. Cea implique inversement que les variable du contexte de base ne sont pas disponible durant l'exécution d'une fonction.
* Les variables créées durant une fonctions sont détruite à la fin de l'exécution de la dite fonctions. Les seules informations qui peuvent entrés et sortir des contextes de fonctions sont les paramètres d'entrés et les retours.

## Passage par valeurs
À l'appel de fonction, les informations passées^[[Share Data Between Workspaces](https://www.mathworks.com/help/matlab/matlab_prog/share-data-between-workspaces.html)] à la fonction sont seulement les valeurs utilisé dans l'appel. Les distinction entre l'appel et la déclaration de la fonction sont les suivantes:

* Les paramètres utilisé durant l'appel, nommé paramètres effectifs, sont évalués en valeur avant d'être envoyé à la fonction. Il nous est donc possible d'avoir des expressions avec des opérations voir d'autres appel de fonction comme paramètres effectifs durant l'appel d'une fonction.
* Les valeurs envoyés par l'appel de la fonction sont assigné au paramètres formels, les identificateurs créés à la déclaration de la fonction. Les valeurs reçus sont assigné avant la première instruction et les variables de paramètres d'entrés sont donc disponible pour utilisation durant la fonction.
* Puisque seulement les valeurs sont transféré, c'est l'ordre des paramètres qui va dictés ou se transfert les valeurs entre les paramètres formels et les paramètres effectifs.

L'utilisation des retours utilisent le même mécanisme. Seul la valeur dans la variable de retour est renvoyé à l'appelant d'une fonction. Il nous est donc possible de faire appel à une fonction sans savoir quel est le nom de la variable de retour.

# Variable globale
La variable globable^[[global](https://www.mathworks.com/help/matlab/ref/global.html)] permet de contourné le mécanisme de partage d'information habituelle des paramètres et des retours. Il est possible de lié deux variables du même nom à un espace de travail "globale" qui peut persister après l'éxécution de fonction.

Pour utiliser une variable globale, il faut l'indiquer au début du fichier avec le mot clé `global` suivit du nom de la variable globale. Cette instruction indique que toute intéraction avec cette variable devrait se faire dans le contexte globale et non dans le contexte du script ou de la fonction.

En utilisant ce mécanisme entre plusieurs contexte, il est donc possible de consulter une variable globale sans intéragir avec les paramètres d'entrées et les retours.

Dans le cadre du cours, l'utilisation des variables gloables est **interdite** sauf indication contraire. Les variables gloables ont leurs placee en programmation, mais c'est un piège facile pour les débutants en programmation.

# Tests
Pour chaque fonction que écrite, il doit y avoir un test qui l'accompagne pour vérifié sa bonne fonctionnalité. Le test permet de faire des appels avec des valeurs arbitraire donc la réponse est connu. Les tests vérifie que les appels de valeurs arbitraire retourne bien les réponses attendues. Dans le cadre du cours, seules les fonctions n'ayant pas de saisit n'y d'affichage seront testées^[Il est possible de tester ces fonctions mais cela demandes des connaissances qui sont plus large que celles vues dans le cours.].

## Test unitaire / Script de test
Avec chaque fonction va venir un script de test^[Le terme générique est un test unitaire de la fonction.]. À l'intérieur de ce script, la fonction `assert` est utilsé pour vérifié le retour de la fonction. Un script de test devrait contenir quelques appels à la fonction à tester.

## `assert`
La fonction `assert` est une fonction de validation. Elle ne prends qu'un seul paramètre qui est une valeur logique. Si la valeur logique est vrai, rien ne se passe durant l'exécution. Mais, si la valeur logique est fausse, une erreur est généré et le programme s'interrompe. Ce mécanisme est utilisé pour faire la comparaison de valeurs attendu à des valeurs arbitraire^[Il est à noter que puisque les scripts de tests utilisent des valeurs arbitraires, ceux-ci n'ont pas besoin d'être en constante.] donné à un appel de la fonction à tester.

```{title="Script de tests de la fonction mod"}
% Tests pour la fonctions mod
assert(mod(5, 3) == 2)
assert(mod(23, 1) == 0)
assert(mod(4, 12) == 4)
```

## Test de valeurs fractionnaires
Un cas particulier émerge quand vient le temps de tester des fonctions qui retourne des valeurs fractionnaires. MATLAB et l'informatique en générale est incapable de garder en mémoire de façon parfaite des valeurs fractionnaire. Il arrive donc que des tests de comparaison d'égalité échoue car la valeur calculé et la valeur attentue sont très semblable mais par *parfaitement* égale.

```{title="Test d'égalité qui démontre le problème de nombres fractionnaires"}
% Test qui génère une erreur
assert((0.3 - 0.2 - 0.1) == 0)
```

Pour palier à cette défaillance, les tests de fonctions qui retourne des valeurs fractionnaires sera modifiées pour prendre en compte ce petit taux d'erreur possible. Les tests seront un calcul de l'erreur entre la valeur attendu et la valeur calculé. Si ce taux d'erreur est très bas, la fonction va passer le test.

```{title="Test de la fonction sin avec des retour fractionnaires"}
% Tests de la fonction sin
assert(abs(sin(1) - 0.8415) < 0.0001)
assert(abs(sin(2) - 0.9093) < 0.0001)
assert(abs(sin(1.5) - 0.9975) < 0.0001)
```