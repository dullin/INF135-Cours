---
title: INF135 - Chaines de caractères, tris et fouilles
author: Hugo Leblanc
date: Cours 5
pandocomatic_:
  use-template: 
  - presentation
  - presentation-handout
...
# Objectifs de la semaine
* Chaine de caractères
    * Fonctions de chaines
* Tris
* Fouilles

# Exercice
* Écrivez une fonction qui reçoit un tableau et trouve la somme en alternant addition et soustraction de chaque élément. 
```
>> sumAddSub([2 5 2])
    ans =
      -1
```

# Chaine de caractères
* La chaine est représentée dans MATLAB par des délimiteurs de guillemet simple;

```
chaine = 'Allo la classe'
nom = 'Hugo'
```

* Chaque caractère de la chaine est encodé selon un table de conversion. La table la plus commune est la table ASCII;

* La suite de caractères forme un tableau. Les chaines sont donc des tableaux, comme toutes autres variables de MATLAB.

* Il existe plusieurs fonctions qui permettent de faire les manipulations communes des chaines.

# Fonctions des chaines

* `double` / `char` : Converti d'un type à l'autre;
* `str2num` / `num2str` : Convertie d'une chaine représentant un nombre à la valeur numérique;
* `strcmp` : Compare deux chaines;
* `upper` / `lower` : Modifie les lettres majuscules/minuscules;
* `strfind` : Recherche de patrons de caractères dans une chaine;
* `strtok` : Coupe une partie de la chaine.

# Exercice
* Écrivez trois fonctions qui :
  * Trouve le nombre d'un caractère spécifique dans une chaine;
  * Enlève tous les espaces d’une chaine;
  * Enlève tous les espaces à gauche d’une chaine.

# Tris
* Les tris ordonnent un tableau non ordonné;
* Il existe plusieurs méthodes de tris :
  * Tri par sélection;
  * Tri par insertion;
  * Tri à bulle;
  * Quicksort;
  * Et bien d'autres.
* Dans MATLAB, pour faire un tri, nous utiliserons la fonction `sort`.

# Fouilles
* Les fouilles trouvent un élément dans un tableau;
* Deux types de fouilles sont possibles:
  * Linéaire;
  * Binaire (sur tableau trié).
* Dans MATLAB, la fonction `find` permets de faire des fouilles.
