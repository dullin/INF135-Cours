\maketitle
Environnement
=============

Current Folder
--------------

Le dossier courant représente l'espace de travail utilisé pour
l'utilisation de scripts ou fonctions. Pour pouvoir utiliser les
programmes que nous allons créer, il faut que ceux-ci soient dans le
dossier courant. On peut modifier le dossier courant avec la barre
d'exploration au-dessus de la fenêtre.

Command Window
--------------

La fenêtre de commande est l'interface principale dans MATLAB. Elle
permet de recevoir les instructions qui seront ensuite exécutées.

Workspace
---------

L'espace de travail représente la mémoire de MATLAB. C'est la
représentation des différentes variables qui sont disponibles pour
l'exécution.

Editor
------

L'éditeur est l'endroit où nous travaillerons le plus. C'est ici que
nous pouvons écrire nos scripts et fonctions qui seront la base de nos
programmes. Il est à mentionner que l'éditeur utilise une barre d'outils
avec plusieurs fonctionnalités propres à l'éditeur.

Concepts fondamentaux de MATLAB
===============================

Instructions
------------

Une instruction est l'élément de base que MATLAB traite dans un
programme. Une instruction peut exécuter une expression mathématique,
appeler une fonction spécifique ou prendre des décisions par rapport à
un état ou une condition. Un programme est constitué d'une multitude
d'instructions qui sont exécutées à la chaine par MATLAB. MATLAB est
seulement capable d'exécuter une instruction à la fois et doit attendre
de compléter l'instruction courante avant de pouvoir en exécuter une
autre. Deux méthodes de bases nous permettent d'utiliser des
instructions: La première et la plus directe est d'utiliser la fenêtre
de commande ou \"Command Window\". Pour exécuter une instruction, on
écrit l'instruction après l'invite de commande suivit de la touche
\[Entrer\] pour exécuter l'instruction. La deuxième méthode est d'écrire
un script. Un script est une série d'instructions écrite d'avance qui
sera exécutée de manière séquentielle par MATLAB. Le principe est
semblable à copier-coller chaque instruction du script dans la fenêtre
de commande puis de l'exécuter manuellement. Les scripts permettent de
faire des programmes complexes de manière plus automatique que l'entrée
manuelle d'instructions. Les instructions ont la possibilité de
retourner une réponse qui peut être assignée à une variable. Si
l'instruction retourne une réponse et qu'aucune variable n'est assignée,
la réponse est assignée à la variable \"ans\" par défaut. MATLAB affiche
le résultat de l'instruction dans l'invite de commande après son
exécution.

Le point-virgule
----------------

Le point-virgule ( ; ) peut être ajouté après une instruction pour
ignorer l'affichage du résultat dans la fenêtre de commande.
L'instruction est quand même exécutée, mais l'affichage n'est pas
présent.

Les points de suspension
------------------------

Les points de suspension ( \... ) permettent de faire une instruction
sur plusieurs lignes à la place d'une seule. Utilisés dans la fenêtre de
commande, MATLAB attend le reste de l'instruction après avoir appuyé sur
\[Entrer\]. Les points de suspension peuvent être utilisés à répétitions
sans problèmes.

Expressions
-----------

Une expression est un concept important, car le principe d'expression
revient durant tous les concepts de MATLAB. Dans sa définition la plus
simple, une expression est une opération qui donne un résultat. Il
existe plusieurs types d'expression, la plus commune est l'expression
mathématique. MATLAB va résoudre les expressions d'une instruction avant
de l'exécuter. La résolution de l'expression est régie par les règles de
priorité des opérations.

Fonctions
---------

MATLAB supporte plusieurs milliers de fonctions qui sont mises à notre
disposition pour faciliter la conception de nos programmes. Chaque
fonction comporte un nom propre et une utilité unique. Les paramètres
d'entrées sont des informations primordiales à l'exécution de certaines
fonctions, par exemple : l'angle pour calculer un sinus. On appelle une
fonction en écrivant son nom dans une instruction. Si la fonction a
besoin de paramètres d'entrées, on utilise des parenthèses pour
encapsuler les paramètres et des virgules pour les séparer.

Identificateurs
===============

Quand vient le temps de créer des éléments nommés dans MATLAB, des
règles doivent être suivies. On appelle tout élément nommé de notre
propre cru des identificateurs. Les identificateurs sont surtout
utilisés pour nommer des fichiers et des variables. Leur nom doit
débuter par une lettre, suivi de lettre, de chiffres ou de tirets bas.
MATLAB est sensible à la casse, il faut donc aussi faire attention à
notre utilisation de lettres majuscules ou minuscules dans la création
de nos identificateurs. Il faut aussi faire attention de ne pas utiliser
des noms de fonctions déjà existantes ou des mots réservés, car la
priorité est donnée au nom de variable et la fonction devient donc
inaccessible.

Script
======

Quand vient le temps de créer des programmes, on veut automatiser
l'exécution des instructions. Les scripts de MATLAB permettent de faire
l'exécution automatique d'instructions écrites dans le fichier. Les
scripts sont des fichiers textes avec une extension .m . Chaque ligne du
fichier représente une instruction que MATLAB devra exécuter. Les
instructions seront exécutées de manières séquentielles à partir du
début du fichier, c'est à dire en ordre de lecture. N'importe quelle
instruction utilisée dans la fenêtre de commande peut être incluse de la
même manière dans un script. Le script peut aussi contenir des lignes
vides pour augmenter la lisibilité. Pour exécuter le script, on appuie
sur le bouton \[Run\] de MATAB quand le script est sélectionné dans
l'éditeur. On peut aussi exécuter le script en appelant le nom du script
dans la fenêtre de commande sans son extension.

Commentaires
------------

Les commentaires sont des notes laissés par le programmeur qui ne sera
pas exécuté par MATLAB. Les commentaires permettent de laisser des
explications utiles sur les instructions dans nos programmes. Les
commentaires commencent avec un symbole de pourcentage ( % ) et le
restant de la ligne est automatiquement en commentaire. Une ligne
suivant les points de suspension terminant un commentaire est elle aussi
considérée comme tel.

Arrêt d'urgence d'un programme
------------------------------

Si MATLAB ne répond plus ou est constamment \"Busy\", on peut
interrompre le programme courant avec le raccourci \[ Ctrl \] \[ C \]
après avoir sélectionné la fenêtre de commande. Plusieurs annulations
peuvent être nécessaires si plusieurs opérations étaient en attente.

Fonctions de bases
------------------

Plusieurs fonctions simples sont utiles en commençant l'utilisation de
MATLAB.

-   clc - Vide la fenêtre de commande

-   clear - Vide l'espace de travail

-   help fonction - Donne de l'aide sommaire sur la fonction

-   doc fonction - Donne la documentation sur la fonction

Variables
=========

Une variable est l'unité de mémoire de base de nos programmes. Une
variable consiste en 3 choses :

-   Un identificateur - Le nom de la variable

-   Une valeur - Le contenu de la variable

-   Un type - La nature de la variable

On crée une variable avec une instruction d'assignation. L'assignation
utilise le sigle égal ( = ) pour indiquer l'assignation d'une expression
à un identificateur. Pour utiliser une variable déjà assignée, on place
son identificateur à l'intérieur d'une expression. La valeur contenue
dans la variable sera remplacée dans l'expression avant qu'elle ne soit
résolue.

Type de données
---------------

Les variables de MATLAB peuvent avoir plusieurs formes. Nous nous
concentrerons sur trois types de variables durant le début du cours.

-   Valeurs numériques - double

-   Valeurs logiques - logical

-   Valeurs textuelles - char

double
------

Pour les variables numériques, le type double est utilisé par défaut
dans MATLAB. Ce type est capable de contenir des nombres réels de tout
genre. Il existe une problématique avec le type numérique double. Dû à
la gestion de la mémoire pour représenter les valeurs, il est souvent
difficile de faire des comparaisons entre deux valeurs qui sont
supposées être identiques. Pour faire des comparaisons de valeurs
calculées, on veut utiliser une comparaison entre une valeur minimale
(ex: 0.01) et la différence absolue des deux valeurs.

logical
-------

Pour des éléments logiques binaires, le type logical est utilisé. Ce
type peut avoir seulement deux possibilités: true ou false, représentées
aussi par les valeurs 1 et 0 respectivement.

char
----

Pour sauvegarder du texte, le type char est disponible. Les variables
sont capables de contenir des chaines de caractères. Les chaines des
caractères sont représentées par du texte à l'intérieur de guillemets
simples.

Constantes
----------

Durant la création de nos programmes, il nous est donné d'utiliser des
valeurs arbitraires pour représenter des informations (taux de taxation,
âge minimum, etc.) Pour augmenter la lisibilité du code et éviter des
erreurs, ce genre de valeurs doit être contenu dans des variables avec
des identificateurs spéciaux. Les constantes auront des noms de
variables constitués seulement de lettres en majuscules pour les
différences des variables typiques. Si notre programme à besoin de
plusieurs variables, il est habituel de les regrouper dans un script et
d'appeler le script au moment opportun.

fprintf
=======

La fonction fprintf permet d'afficher de l'information dans la fenêtre
de commande. Son utilisation de base est simple, mais elle contient
plusieurs configurations optionnelles. La version la plus simple du
fprintf affiche le contenu d'une chaine de caractères envoyé en
paramètre.

``` {title="Simple fprintf"}
fprintf('Bonjour la vie!\n')
```

Pour afficher le contenu d'une variable avec fprintf, il nous faut
inclure un opérateur de formatage à l'intérieur de notre chaine de
caractère. Il faut ensuite inclure la valeur à afficher comme expression
dans la fonction.

``` {title="fprintf avec opérateur de formatage"}
fprintf('Nombre : %g', 3)
fprintf('Mot : %s', 'allo')

% Limite le nombre de décimales avec %.Xf
fprintf('Nombre : %.2f', 3.12345) % Affiche 3.12

x = 5;
fprintf('Nombre : %g', x)
```

L'opérateur de formatage utilisé dépend de la valeur à afficher. Les
deux cas généraux sont %g pour des valeurs numériques et %s pour des
chaines de caractères. Il nous est aussi possible d'afficher un nombre
limité de valeurs fractionnaires avec %.Xf ou X est le nombre de
décimales à afficher. La fonction fprintf nous donne aussi la
possibilité d'afficher des caractères spéciaux qui ne sont pas
représentés par des caractères normaux ou des caractères réservés. Voici
les exemples les plus communs.

-   \\n - Un saut de ligne

-   \- Un guillemet simple

-   \%% - Un sigle de pourcentage

N'oubliez pas qu'on peut utiliser une expression avec l'opérateur de
formatage. Cela nous laisse facilement afficher le contenu de variables.

input
=====

La fonction input permet de saisir des informations d'un utilisateur.
Son appel bloque temporairement l'exécution des autres instructions et
MATLAB attend que l'utilisateur entre une information dans la fenêtre de
commande. La fonction s'utilise habituellement avec une assignation et
un message de saisie. Une autre version est aussi disponible si l'on
veut avoir une saisie d'une chaine de caractères.

``` {title="Exemples d'utilisations de la fonction input"}
x = input('Entrez un nombre : ')
saisi = input('Entrez un mot : ', 's')
```

Opérateurs et caractères spéciaux
=================================

MATLAB est bourré d'opérateurs et de caractères spéciaux à utiliser avec
nos instructions. Les opérateurs arithmétiques de bases sont tous
présents, mais il existe aussi d'autres types d'opérateurs qui peuvent
être utilisés pour générer des expressions.

Opérateur relationnels
----------------------

Les opérateurs relationnels permettent de comparer deux valeurs et
donner une réponse logique (true ou false). Les opérateurs relationnels
sont :

-   $<$ - Plus petit que

-   $<=$ - Plus petit ou égale que

-   $>$ - Plus grand que

-   $>=$ - Plus grand ou égale que

-   $==$ - Égale à

-   $\ensuremath{\sim}=$ - Différent de

Les opérations relationnelles peuvent être jumelées à des opérations
arithmétiques qui se feront en premiers d'après la priorité des
opérations de MATLAB.

Structure de contrôles conditionnel
===================================

Les structures de contrôles permettent de briser le flot habituel
d'exécution des instructions. Les premières structures de contrôles que
nous allons voir sont les structures de contrôles conditionnelles, mais
il existe aussi des structures de contrôles à boucles.

Conditionnel if
---------------

La structure de contrôle conditionnel if permet de prendre une décision
par rapport à une condition et d'exécuter seulement les instructions
voulues selon celle-ci.

Il existe plusieurs variations du if. Commençons avec ça forme la plus
simple.

``` {title="Structure du if simple"}
if ¬\mlplaceholder{condition}¬
    ¬\mlplaceholder{instructions}¬
end
    
```

\hfill
``` {title="Exemple du if simple"}
if x > 5
    fprintf('x plus grand que 5.')
end
    
```

Dans ce cas simple, la condition, une expression booléenne, est évaluée.
Si la condition est vrai, le bloc d'instruction entre le if et le end
est exécuté. Sinon, dans le cas où l'expression est fausse, le bloc est
ignoré et l'exécution continue après le end. Le deuxième cas ajoute un
bloc d'instruction pour une condition fausse.

``` {title="Structure du if avec else"}
if ¬\mlplaceholder{condition}¬
    ¬\mlplaceholder{instructions}¬
else
    ¬\mlplaceholder{instructions}¬
end
    
```

\hfill
``` {title="Exemple du if avec else"}
if x > 5
    fprintf('x plus grand que 5.')
else
    fprintf('Pas plus que 5.')
end
    
```

Avec cette configuration, si la condition est vraie, on exécute le
premier bloc d'instruction. Si la condition est fausse, on exécute le
bloc entre le else et le end. Dans les deux cas, après avoir exécuté le
bloc, on continue l'exécution après le end. Le troisième cas permet
d'avoir des conditions supplémentaires si la première n'est pas vraie.

``` {title="Structure du if avec elseif"}
if ¬\mlplaceholder{condition}¬
    ¬\mlplaceholder{instructions}¬
elseif ¬\mlplaceholder{condition}¬
    ¬\mlplaceholder{instructions}¬
end
    
```

\hfill
``` {title="Exemple du if avec elseif"}
if x > 5
    fprintf('x plus grand que 5.')
elseif x == 3
    fprintf('x est égale à 3.')
end
    
```

Le principe initial reste pareil, si la première condition est vraie, on
exécute le premier bloc d'instruction. Sinon, on regarde la deuxième
condition et on exécute son bloc d'instructions si la condition est
vrai. Les blocs d'instructions sont mutuellement exclusifs, dès qu'un
des blocs est exécuté , le programme saute au end et continu à partir de
là.

On peut aussi mélanger les deux configurations, la seule restriction est
que le else doit obligatoirement être le dernier bloc d'instructions. Ce
dernier sera exécuté seulement si aucune des conditions n'est vraie.

Conditionnel switch
-------------------

La conditionnel switch est un cas particulier du if avec une syntaxe qui
permet de faciliter son implémentation et sa lisibilité. Le switch est
utilisé quand une variable doit être comparée à une série d'égalité
possible. On switch sur la variable et implémente plusieurs cas
possibles.

``` {title="Structure d'un if pouvant être un switch"}
if x == 3
    ¬\mlplaceholder{instructions}¬
elseif x == 7
    ¬\mlplaceholder{instructions}¬
else
    ¬\mlplaceholder{instructions}¬
end
    
```

\hfill
``` {title="Structure du switch"}
switch x
    case 3
        ¬\mlplaceholder{instructions}¬
    case 7
        ¬\mlplaceholder{instructions}¬
    otherwise
        ¬\mlplaceholder{instructions}¬
end
    
```

Les principes des blocs d'instructions du if sont aussi applicables au
switch. Les blocs sont mutuellement exclusifs et il existe un bloc pour
le cas où toutes les possibilités ont échoué. Le switch peut être
utilisé pour la comparaison de valeurs numériques ou de chaines de
caractères.

\nobibliography{cours1}
\bibliographystyle{plainnat}
