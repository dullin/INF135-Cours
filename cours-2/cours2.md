---
title: INF135 - Normes de programmation et structures itératives
author: Hugo Leblanc
date: Cours 2
pandocomatic_:
  use-template: 
  - presentation
  - presentation-handout
...

# Retour sur les notions vues
* Le flot et les instructions de programmation (scripts);
* Commentaires;
* Les variables et l'instruction d'assignation avec `=`;
* Les opérateurs arithmétiques et de comparaisons;
* Structures de contrôles conditionnelles `if` et `switch`.

# Objectifs de la semaine
* Standarts et normes de programmation;
* Structures de contrôle itérative:
    * `while`;
    * `for`.
* Opérateurs logiques;
* Utilisation de fonctions:
    * Paramètres d'entrés;
    * Paramètre de retour.

# Normes de programmation
* Des règles de présentatation et de syntaxe sont établies pour maximiser la lisibilité de nos programmes;
* Les normes du cours prennent une approche de programmation défensive. Le but est de minimiser le nombre d'erreur possible venant du programmeur.

# Espacement
* L'espacement est les espaces vides horizontales ou verticales laissé dans nos programmes;
* L'espacement horizontale est nommé l'indentation. Chaque bloc de code aura un niveau d'indentation. Les bloc de code sont délimité avec un mot clé de début et un end;
* Les espacement verticales sont des sauts de lignes vide laissé pour délimités les contextes entre les instructions;
* Les deux types d'espacements sont mutuellement exclusif. Il ne faut pas avoir un changement d'indentation avec un saut de ligne. Le changement d'indentation aura priorité.

# Commentaire
* Les commentaires à l'intérieur du code existe pour expliquer le "pourquoi" de nos instructions. Leurs buts est d'éclaircir pourquoie les instructions sont nécéssaires pour arrivé à la solution de notre programme;
* Évitez de "traduire" le code en commentaire. Cela donne un commentaire impertinent.

# En-tête
* Au début de chaque fichier, nous aurons un en-tête qui explique le contenu générale du fichier. En avancant dans la session, d'autre considération seront ajouté aux en-têtes;
* Les infomartions générales dans les scripts seront une description du programme et autres informations pertienentes (auteurs, date).

# Noms significatifs
* Tout identificateur doit être bien identifier.
* Nous utiliserons la norme du camelCase pour le nom des éléments à identifier.
* Un nom significatifs doit être significatifs pour tous, par juste pour vous.

# Structure de contrôle itérative `while`
* La boucle `while` répète les instructions jusqu'à ce que la condition soit fausse;
~~~MATLAB
while condition
    instructions
end
~~~
* Le `while` est habituellement utilisé quand on ne connait pas le nombre d'itérations à faire.

# Exercice 1
Écrivez des scripts qui :

* Saisit un nombre à l'utilisateur et recommence la saisit tant que le nombre saisit n'est pas 0;
* Saisit un nombre n et calcule la somme des nombre de 1 à n.
* Saisit un nombre m et calcule le nombre factoriel n. Le nombre factoriel est la multiplication des nombes de 1 à n. Par exemple, le nombre factoriel de 5 est donné par 1x2x3x4x5.

# Structure de contrôle itérative `for`
* Lorsque le nombre d'itérations est connu, la boucle `for` sera utilisé;
* La boucle `for` inclu un compteur qui est configuré au début de la boucle;
~~~MATLAB
for var=nbDebut:nbFin
    instruction
end
~~~
* La boucle va prendre toutes les valeurs de nbDebut à nbFin dans var;
* Si le saut doit être autre que 1, la configuration du `for`peut contenir un saut avec `nbDebut:saut:nbFin`.

# Exercice 2
Écrivez des script qui:

* Saisit un nombre n et calcule la somme des nombre de 1 à n en utilisant la boucle `for`;
* Saisit un nombre n et calcule la somme des nombres pair de 1 à n;
* Saisit 10 nombres consécutivements. Détermine et affiche le nombre de fois que le nombre 0 à été saisit.

# Opérateurs logiques
* Les opérateurs logiques opèrent sur des valeurs logiques et retourne des valeurs logique;
    * La conjonction ET `&&`;
    * La disjonction OU `||`;
    * La négation NON `~`.

# Exercice 3
* Écrivez un script qui saisit l'âge d'un utilisateur et qui affiche si l'utilisateur a droit à un tarif réduit. Le tarif réduit est disponible pour les personnes d'âge mineur (plus petit que 18) ou d'âge d'or (plus grand que 60).

# Appel de fonction
* Les fonctions sont des bloc de codes qui réalisent une tâche simple et précise;
* L'utilisation de fonctions se fait en les appellant;
* L'appel de la fonction peut demander de présisé des paramètres d'entrés qui sont nécéssaire à la fonction;
* Les paramètres sont présenté entre parenthèses, délimités par une virgule.
* La fonction peut avoir un réponse qui est généré. Cette réponse est nommé un retour;
* Une fonction qui ne retourne rien peut aussi être nommé une procédure;
* Le retour prend la place de l'appel dans l'instruction donné.
~~~MATLAB
var = maFonction(param1, param2);
~~~

# Exercice 4
* Écrivez un script qui saisit un nombre d'élèves et un nombre de membres par équipe. Le script affiche le nombre d'élève restant sans équipe complète. Utilisez la fonction `mod`.