---
title: INF135 - Normes de programmation et structures itératives
author: Hugo Leblanc
date: Cours 2
pandocomatic_:
  use-template: 
  - presentation
  - presentation-handout
...

# Objectifs de la semaine
* Standards et normes de programmation ;
* Structures de contrôle itératives :
    * `while`;
    * `for`.
* Opérateurs logiques ;
* Utilisation de fonctions :
    * Paramètres d’entrées ;
    * Paramètre de retour.

# Normes de programmation
* Des règles de présentation et de syntaxe sont établies pour maximiser la lisibilité de nos programmes ;
* Les normes du cours prennent une approche de programmation défensive. Le but est de minimiser le nombre d’erreurs possibles venant du programmeur.

# Espacement
* L’espacement est les espaces vides horizontaux ou verticaux laissés dans nos programmes ;
* L’espacement horizontal est nommé l’indentation. Chaque bloc de code aura un niveau d’indentation. Les blocs de code sont délimités avec un mot clé de début et un end ;
* Les espacements verticaux sont des sauts de lignes vides laissés pour délimiter les contextes entre les instructions ;
* Les deux types d’espacements sont mutuellement exclusifs. Il ne faut pas avoir un changement d’indentation avec un saut de ligne. Le changement d’indentation aura priorité.

# Commentaire
* Les commentaires à l’intérieur du code existent pour expliquer le « pourquoi » de nos instructions. Leurs buts sont d’éclaircir pourquoi les instructions sont nécessaires pour arriver à la solution de notre programme ;
* Évitez de « traduire » le code en commentaire. Cela donne un commentaire impertinent.

# En-tête
* Au début de chaque fichier, nous aurons un en-tête qui explique le contenu général du fichier. En avançant dans la session, d’autres considérations seront ajoutées aux en-têtes ;
* Les informations générales dans les scripts seront une description du programme et autre information pertinente (auteurs, date).

# Noms significatifs
* Tout identificateur doit être bien identifié.
* Nous utiliserons la norme du camelCase pour le nom des éléments à identifier.
* Un nom significatif doit être significatif pour tous, par juste pour vous.

# Structure de contrôle itérative `while`
* La boucle `while` répète les instructions jusqu’à ce que la condition soit fausse ;

~~~MATLAB
while condition
    instructions
end
~~~

* Le `while` est habituellement utilisé quand on ne connait pas le nombre d’itérations à faire.

# Exercice 1
Écrivez des scripts qui :

* Saisit un nombre à l’utilisateur et recommence la saisit tant que le nombre saisit n’est pas 0 ;
* Saisit un nombre n et calcule la somme des nombres de 1 à n.
* Saisit un nombre m et calcule le nombre factoriel de n. Le nombre factoriel est la multiplication des nombres de 1 à n. Par exemple, le nombre factoriel de 5 est donné par 1x2x3x4x5.

# Structure de contrôle itératif `for`
* Lorsque le nombre d’itérations est connu, la boucle `for` sera utilisée ;
* La boucle `for` inclut un compteur qui est configuré au début de la boucle ;

~~~MATLAB
for var = nbDebut:nbFin
    instruction
end
~~~

* La boucle va prendre toutes les valeurs de nbDebut à nbFin dans var ;
* Si le saut doit être autre que 1, la configuration du `for` peut contenir un saut avec `nbDebut:saut:nbFin`.

# Exercice 2
Écrivez des scripts qui :

* Saisit un nombre n et calcule la somme des nombres de 1 à n en utilisant la boucle `for`;
* Saisit un nombre n et calcule la somme des nombres pairs de 1 à n ;
* Saisit 10 nombres consécutivement. Détermine et affiche le nombre de fois dont le nombre 0 a été saisi.

# Opérateurs logiques
* Les opérateurs logiques opèrent sur des valeurs logiques et retournent des valeurs logiques ;
    * La conjonction ET `&&` ;
    * La disjonction OU `||` ;
    * La négation NON `~`.

`A` | `B` |   | `A && B` | `A || B`
----|-----|---|:--------:|:-------:
0   | 0   |   | 0        | 0
0   | 1   |   | 0        | 1
1   | 0   |   | 0        | 1
1   | 1   |   | 1        | 1

`A` | `~A`
----|:---:
0   | 1
1   | 0

# Exercice 3
* Écrivez un script qui saisit l’âge d’un utilisateur et qui affiche si l’utilisateur a droit à un tarif réduit. Le tarif réduit est disponible pour les personnes d’âge mineur (plus petit que 18) ou d’âge d’or (plus grand que 60).

# Appel de fonction
* Les fonctions sont des blocs de codes qui réalisent une tâche simple et précise ;
* L’utilisation de fonctions se fait en les appelant ;
* L’appel de la fonction peut demander de préciser des paramètres d’entrées qui sont nécessaires à la fonction ;
* Les paramètres sont présentés entre parenthèses, délimités par une virgule.
* La fonction peut avoir une réponse qui est générée. Cette réponse est nommée un retour ;
* Une fonction qui ne retourne rien peut aussi être nommée une procédure ;
* Le retour prend la place de l’appel dans l’instruction donnée.

~~~MATLAB
var = maFonction(param1, param2) ;
~~~

# Exercice 4
* Écrivez un script qui saisit un nombre d’élèves et un nombre de membres par équipe. Le script affiche le nombre d’élèves restant sans équipe complète. Utilisez la fonction `mod`.