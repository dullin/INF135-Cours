---
title: Fondements de programmation
author: Hugo Leblanc
date: Cours 1
pandocomatic_:
  use-template: 
  - handout
...
# Environnement

## Current Folder
Le dossier courant^[[Desktop Basics](https://www.mathworks.com/help/matlab/learn_matlab/desktop.html)] représente l'espace de travail utilisé pour
l'utilisation de scripts ou fonctions. Pour pouvoir utiliser les
programmes que nous allons créer, il faut que ceux-ci soient dans le
dossier courant. On peut modifier le dossier courant avec la barre
d'exploration au-dessus de la fenêtre.

## Command Window
La fenêtre de commande est l'interface principale dans MATLAB. Elle
permet de recevoir les instructions^[[Enter Statements in Command Window](https://www.mathworks.com/help/matlab/matlab_env/enter-statements-in-command-window.html)] qui seront ensuite exécutées.

## Workspace
L'espace de travail représente la mémoire de MATLAB. C'est la
représentation des différentes variables qui sont disponibles pour
l'exécution.

## Editor
L'éditeur est l'endroit où nous travaillerons le plus. C'est ici que
nous pouvons écrire nos scripts et fonctions qui seront la base de nos
programmes. Il est à mentionner que l'éditeur utilise une barre d'outils
avec plusieurs fonctionnalités propres à l'éditeur.

# Concepts fondamentaux de MATLAB
## Instructions
Une instruction^[“command” ou "statement" en anglais.] est l'élément de base que MATLAB traite dans un
programme. Une instruction peut exécuter une expression mathématique,
appeler une fonction spécifique ou prendre des décisions par rapport à
un état ou une condition. Un programme est constitué d'une multitude
d'instructions qui sont exécutées à la chaine par MATLAB. MATLAB est
seulement capable d'exécuter une instruction à la fois et doit attendre
de compléter l'instruction courante avant de pouvoir en exécuter une
autre. Deux méthodes de bases nous permettent d'utiliser des
instructions: La première et la plus directe est d'utiliser la fenêtre
de commande ou "Command Window"^[L'invite de commande est représentée par deux signes plus grand que (>>). Cela indique que MATLAB est prêt à recevoir une nouvelle instruction.]. Pour exécuter une instruction, on
écrit l'instruction après l'invite de commande suivit de la touche 
`Entrer` pour exécuter l'instruction. La deuxième méthode est d'écrire
un script. Un script est une série d'instructions écrite d'avance qui
sera exécutée de manière séquentielle par MATLAB. Le principe est
semblable à copier-coller chaque instruction du script dans la fenêtre
de commande puis de l'exécuter manuellement. Les scripts permettent de
faire des programmes complexes de manière plus automatique que l'entrée
manuelle d'instructions. Les instructions ont la possibilité de
retourner une réponse qui peut être assignée à une variable. Si
l'instruction retourne une réponse et qu'aucune variable n'est assignée,
la réponse est assignée à la variable ans par défaut. MATLAB affiche
le résultat de l'instruction dans l'invite de commande après son
exécution.

## Le point-virgule
Le point-virgule (;)^[[MATLAB Operators and Special Characters](https://www.mathworks.com/help/matlab/matlab_prog/matlab-operators-and-special-characters.html)]  peut être ajouté après une instruction pour
ignorer l'affichage du résultat dans la fenêtre de commande.
L'instruction est quand même exécutée, mais l'affichage n'est pas
présent.

## Les points de suspension
Les points de suspension (...)^[[Continue Long Statements on Multiple Lines](https://www.mathworks.com/help/matlab/matlab_prog/continue-long-statements-on-multiple-lines.html)] permettent de faire une instruction
sur plusieurs lignes à la place d'une seule. Utilisés dans la fenêtre de
commande, MATLAB attend le reste de l'instruction après avoir appuyé sur
Entrer. Les points de suspension peuvent être utilisés à répétitions
sans problèmes.

## Expressions
Une expression^[[Expressions](https://www.mathworks.com/help/matlab/learn_matlab/expressions.html)] est un concept important, car le principe d'expression
revient durant tous les concepts de MATLAB. Dans sa définition la plus
simple, une expression est une opération qui donne un résultat. Il
existe plusieurs types d'expression, la plus commune est l'expression
mathématique. MATLAB va résoudre les expressions d'une instruction avant
de l'exécuter.^[On dit qu'une expression est évaluée quand elle est résolue par MATLAB.
Nous utiliserons souvent le terme expression comme substitut dans nos exemples, il faut donc comprendre que n'importe quelle expression peut être insérée à cet endroit.] La résolution de l'expression est régie par les règles de
priorité des opérations^[[Operator Precedence](https://www.mathworks.com/help/matlab/matlab_prog/operator-precedence.html)].

## Fonctions
MATLAB supporte plusieurs milliers de fonctions^[[Calling Functions](https://www.mathworks.com/help/matlab/learn_matlab/calling-functions.html)] qui sont mises à notre
disposition pour faciliter la conception de nos programmes. Chaque
fonction comporte un nom propre et une utilité unique.^[”L'appel d'une fonction” est le terme utilisé pour dire qu'on exécute, utilise ou invoque une fonction.] Les paramètres
d'entrées sont des informations primordiales à l'exécution de certaines
fonctions, par exemple : l'angle pour calculer un sinus. On appelle une
fonction en écrivant son nom dans une instruction. Si la fonction a
besoin de paramètres d'entrées, on utilise des parenthèses pour
encapsuler les paramètres et des virgules pour les séparer.

# Identificateurs
Quand vient le temps de créer des éléments nommés dans MATLAB, des
règles^[[Variable Names](https://www.mathworks.com/help/matlab/matlab_prog/variable-names.html)] doivent être suivies. On appelle tout élément nommé de notre
propre cru des identificateurs. Les identificateurs sont surtout
utilisés pour nommer des fichiers et des variables.^[Le tiret bas (_) est aussi communément appelé "underscore".] Leur nom doit
débuter par une lettre, suivi de lettre, de chiffres ou de tirets bas.
MATLAB est sensible à la casse^[[Case and Space Sensitivity](https://www.mathworks.com/help/matlab/matlab_prog/case-and-space-sensitivity.html)], il faut donc aussi faire attention à
notre utilisation de lettres majuscules ou minuscules dans la création
de nos identificateurs. Il faut aussi faire attention de ne pas utiliser
des noms de fonctions déjà existantes^[Par exemple, les fonctions max et min existent déjà, ce qui pourrait être problématique.] ou des mots réservés^[[iskeyword](https://www.mathworks.com/help/matlab/ref/iskeyword.html)], car la
priorité est donnée au nom de variable et la fonction devient donc
inaccessible.

# Script
Quand vient le temps de créer des programmes, on veut automatiser
l'exécution des instructions. Les scripts^[[Create Scripts](https://www.mathworks.com/help/matlab/matlab_prog/create-scripts.html)] de MATLAB permettent de faire
l'exécution automatique d'instructions écrites dans le fichier. Les
scripts sont des fichiers textes avec une extension .m . Chaque ligne du
fichier représente une instruction que MATLAB devra exécuter. Les
instructions seront exécutées de manières séquentielles à partir du
début du fichier, c'est à dire en ordre de lecture. N'importe quelle
instruction utilisée dans la fenêtre de commande peut être incluse de la
même manière dans un script. Le script peut aussi contenir des lignes
vides pour augmenter la lisibilité. Pour exécuter le script, on appuie
sur le bouton Run^[![Bouton Run](run-button.png){width=50px}] de MATAB quand le script est sélectionné dans
l'éditeur. On peut aussi exécuter le script en appelant le nom du script
dans la fenêtre de commande sans son extension.

## Commentaires
Les commentaires^[[Add Comments to Programs](https://www.mathworks.com/help/matlab/matlab_prog/comments.html)] sont des notes laissés par le programmeur qui ne sera
pas exécuté par MATLAB. Les commentaires permettent de laisser des
explications utiles sur les instructions dans nos programmes. Les
commentaires commencent avec un symbole de pourcentage (%) et le
restant de la ligne est automatiquement en commentaire. Une ligne
suivant les points de suspension terminant un commentaire est elle aussi
considérée comme tel.

## Arrêt d'urgence d'un programme
Si MATLAB ne répond plus ou est constamment "Busy", on peut
interrompre^[[Stop Execution](https://www.mathworks.com/help/matlab/matlab_env/stop-execution.html)] le programme courant avec le raccourci Ctrl-C
après avoir sélectionné la fenêtre de commande. Plusieurs annulations
peuvent être nécessaires si plusieurs opérations étaient en attente.

# Fonctions de bases
Plusieurs fonctions simples sont utiles en commençant l'utilisation de
MATLAB.

* clc^[[clc](https://www.mathworks.com/help/matlab/ref/clc.html)] - Vide la fenêtre de commande
* clear^[[clear](https://www.mathworks.com/help/matlab/ref/clear.html)] - Vide l'espace de travail
* help^[[help](https://www.mathworks.com/help/matlab/ref/help.html)] fonction - Donne de l'aide sommaire sur la fonction
* doc^[[doc](https://www.mathworks.com/help/matlab/ref/doc.html)] fonction - Donne la documentation sur la fonction

# Variables
Une variable est l'unité de mémoire de base de nos programmes. Une
variable consiste en 3 choses :

* Un identificateur - Le nom de la variable
* Une valeur - Le contenu de la variable
* Un type - La nature de la variable

On crée une variable avec une instruction d'assignation. L'assignation
utilise le sigle égal (=) pour indiquer l'assignation d'une expressions
à un identificateur.^[L'assignation se fait toujours d'une expression à droite vers un identificateur à gauche.] Pour utiliser une variable déjà assignée, on place
son identificateur à l'intérieur d'une expression. La valeur contenue
dans la variable sera remplacée dans l'expression avant qu'elle ne soit
évaluée.

# Type de données
Les variables de MATLAB peuvent avoir plusieurs formes^[[Fundamental MATLAB Classes](https://www.mathworks.com/help/matlab/matlab_prog/fundamental-matlab-classes.html)]. Nous nous
concentrerons sur trois types de variables durant le début du cours.

* Valeurs numériques - `double`
* Valeurs logiques - `logical`
* Valeurs textuelles^[Les valeurs textuelles sont appelées chaine de caractères.] - `char`

## `double`
Pour les variablesé numériques, le type `double`^[[double](https://www.mathworks.com/help/matlab/ref/double.html)] est utilisé par défaut
dans MATLAB. Ce type est capable de contenir des nombres réels de tout
genre. Il existe une problématique avec le type numérique double. Dû à
la gestion de la mémoire pour représenter les valeurs^[[Floating-Point Numbers](https://www.mathworks.com/help/matlab/matlab_prog/floating-point-numbers.html)], il est souvent
difficile de faire des comparaisons entre deux valeurs qui sont
supposées être identiques^[Exemple : Essayez de faire 0.3 - 0.2 - 0.1 dans la fenêtre de commande.]. Pour faire des comparaisons de valeurs
calculées, on veut utiliser une comparaison entre une valeur minimale
(ex: 0.01) et la différence absolue des deux valeurs.

## `logical`
Pour des éléments logiques binaires, le type logical^[[logical](https://www.mathworks.com/help/matlab/ref/logical.html)] est utilisé. Ce
type peut avoir seulement deux possibilités: true^[[true](https://www.mathworks.com/help/matlab/ref/true.html)] ou false^[[false](https://www.mathworks.com/help/matlab/ref/false.html)], représentées
aussi par les valeurs 1 et 0 respectivement.

## `char`
Pour sauvegarder du texte, le type char^[[char](https://www.mathworks.com/help/matlab/ref/char.html)] est disponible. Les variables
sont capables de contenir des chaines de caractères.^[Des chaines de caractères sont nommées "string" en anglais. Il faut faire attention par contre, car il existe un type string dans MATLAB, mais celui-ci ne sera pas utilisé dans le cours, nous utiliserons des “character vectors” de type char.] Les chaines des
caractères sont représentées par du texte à l'intérieur de guillemets
simples.

## Constantes
Durant la création de nos programmes, il nous est donné d'utiliser des
valeurs arbitraires pour représenter des informations (taux de taxation,
âge minimum, etc.) Pour augmenter la lisibilité du code et éviter des
erreurs, ce genre de valeurs doit être contenu dans des variables avec
des identificateurs spéciaux. Les constantes auront des noms de
variables constitués seulement de lettres en majuscules pour les
différences des variables typiques. Si notre programme à besoin de
plusieurs variables, il est habituel de les regrouper dans un script et
d'appeler le script au moment opportun.

# `fprintf`
La fonction `fprintf`^[[fprintf](https://www.mathworks.com/help/matlab/ref/fprintf.html)] permet d'afficher de l'information dans la fenêtre
de commande. Son utilisation de base est simple, mais elle contient
plusieurs configurations optionnelles. La version la plus simple du
fprintf affiche le contenu d'une chaine de caractères envoyé en
paramètre.

~~~
fprintf('Bonjour la vie!\n')
fprintf('Bonjour la vie!\n')
fprintf('Bonjour la vie!\n')
~~~