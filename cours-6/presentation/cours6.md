---
title: INF135 - Matrice et tableau de multiples dimensions
author: Hugo Leblanc
date: Cours 6
pandocomatic_:
  use-template:
  - presentation
  - presentation-handout
...
# Objectifs de la semaine
* Matrices
  * Creation
  * Accès
  * Fonctions
  * Dynamisme
* Tableau de multiples dimensions


# Matrice
* Une matrice est un tableau de deux dimensions;
* La numérotation utilise les lignes et les colonnes;
* Une matrice doit rester rectangulaire.
* Les cases seront toujours identifier par la ligne en premier et ensuite la colonne;
* Les paires de variables `i, j` ou `m, n` seront souvent utilisé pour indiquer les lignes et les colonnes.

# Matrice - Création
Les fonctions suivantes permettent de créer des matrices:

* `zeros(i, j)`/`ones(i, j)` - Initialise toutes les cases à 0/1;
* `rand(i, j)`/`randi(max, 1, j)` - Initialise de manière aléatoire entre 0 et 1/1 et un nombre entier;
* `[liste de valeurs]` - Contruit une matrice de valeurs données. Le `;` permet de faire des sauts de ligne;
* La combinaison des sépareteurs permet de créé des matrice manuellement;
```MATLAB
tab = [1, 2, 3;4, 5,6]
```
* `isequal` - Compare deux matrices. Utile pour les tests.

# Matrice - Accès
* Deux paramètres peuvent être utilisé pour accédé aux éléments du tableau;
```MATLAB
tab(3,4)
```
* Si un seul paramètre est utilisé, les indices parcours les lignes et ensuite les colonnes;

# Matrice - Fonctions
Les fonctions et opérations suivantes sont utiles durant l'accès aux matrices:

* `numel(tab)` - Le nombre d’éléments;
* `size(tab)` - Retourne un tableau des tailles des dimensions;
* `size(tab,x)` - Retourne la taille de la dimension x;
* L'opérateur `:` permet de sélectionner toutes les valeurs d'une dimensions;
```MATLAB
mat(3, :) % Retourne la ligne 3 de la matrice.
```
* Le mot clé `end` permet de sélectionné la dernière cases d'une dimension.
```MATLAB
mat(4, end) % Retourne la dernière colonne de la ligne 4.
```

# Matrice - Parcourir la matrice
* Comme pour les vecteurs, il existe une manière générique de parcourir les matrices.
```MATLAB
for i = 1:size(mat,1)
  for j = 1:size(mat, 2)
    % Instructions
    mat(i, j)
  end
end
```

# Exercice
* Écrivez une fonction qui retourne la somme d’une matrice. Ne pas utiliser la fonction `sum` de MATLAB;
* Écrivez une fonction qui retourne la position de ligne et colonne du minimum d’une matrice. La fonction retourne un vecteur de deux cases contenant la ligne et la colonne de la position minimum.

# Matrice - Dynamisme
* La matrice doit garder sa forme rectangulaire;
* L'insertion de donné va créé des cases avec des valeurs nulle pour garder la forme rectangulaire;
* La suppression d'information doit se faire pour garder le forme rectangulaire. La suppression se fait au niveau de ligne ou colonne complète.
```MATLAB
mat(:, 2) = [] % Supprime la ligne colonne 2.
```

# Tableau de multiples dimensions
* MATLAB nous permet d’avoir autant de dimension que nous le voulons;
* Les fonctions précédentes marchent sur un nombre infini de dimensions;
* Le cours va surtout traiter sur des matrices et possiblement sur des tableaux 3D.

# Exercice
* Écrivez une fonction qui retourne une matrice qui fait les ajout orthogonaux de chaque position. La fonction reçoit la taille de la matrice en (ligne, colonne).
```MATLAB
>> ajoutOrthogonale(3,5)
ans =
     1     2     3     4     5
     2     3     4     5     6
     3     4     5     6     7
```
* Écrivez un fonction qui reçoit la taille d'une matrice à construire (ligne,colonne). La fonction retourne un tableau de deux dimensions quadrillé de 0 et 1.