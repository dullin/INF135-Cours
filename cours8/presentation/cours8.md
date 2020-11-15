---
title: INF135 - Graphiques et enregistrements 
author: Hugo Leblanc 
date: Cours 8
pandocomatic_: 
  use-template:
  - presentation
  - presentation-handout
...

# Objectifs de la semaine
* Graphiques de MATLAB
* Enregistrement

# Figure des graphiques de MATLAB
* L'affichage de graphique dans MATLAB est centré sur la `figure`;
* La `figure` est une fenêtre pouvant contenir un ou plusieurs graphiques;
* Voici quelques fonctions pour travailler avec les `figure` :
    * `figure` : Génère une nouvelle figure;
    * `figure(X)` : Génère ou sélectionne la figure X. X étant un entier;
    * `close`, `close(X)`, `close('all')` : Ferme la figure courante, X ou
      toutes les figures;
    * `subplot(m, n, p)` : Découpe la figure courante en m x n cases et
      sélectionne la case p comme graphique courant.

# Fonctions d'affichage de graphiques
* Avec la figure, des fonctions d'affichage de graphique seront utilisées :
  * `plot` : Ligne 2D;
  * `bar` : Diagramme à bar;
  * `scatter` : Suite de points;
  * Il existe des dizaines de fonctions d'affichage dans l'aide de MATLAB.

# Présentation et annotation des graphiques
* La présentation des informations du graphique peut être configurée
  manuellement à même la figure ou avec des fonctions : 
    * `title` : Titre du graphique;
    * `xlabel`, `ylabel` : Titre des axes;
    * `legend` : Ajoute une légende;
    * `grid` : Ajoute un quadrillé.

# Enregistrement
* Les enregistrements (aussi nommé structure ou `struct`) permettent de
  consolider plusieurs contenant de différents types à l'intérieur d'une seule
  variable sous un seul identificateur commun;
* Chaque contenant va porter son propre nom nommé champs;
* Chaque champ va contenir une donnée. Tous les types de données peuvent être
  dans un champ, même un autre enregistrement!
* Par convention, les identificateurs d'enregistrement vont commencer par une
  lettre majuscule.

# Création d'enregistrement
* La création d'enregistrement utilise deux syntaxes:

* L'utilisation de la fonction struct pour définir chaque champ et valeur
  associés :

```MATLAB
Etudiant = struct('nom', 'Leblanc', 'prenom', 'Hugo', 'note', 99);
```

* La deuxième méthode est une assignation manuelle de chaque champ. Le point
  `.` est utilisé pour accédé aux champs 

```MATLAB
Etudiant.nom = 'Leblanc';
Etudiant.prenom = 'Hugo';
Etudiant.note = 99;
```

# Utilisation d'enregistrement
* Les champs peuvent être accédés aux champs avec le point `.` entre
  l'identificateur et le nom du champ;

```MATLAB
Etudiant = struct('nom', 'Leblanc', 'prenom', 'Hugo', 'note', 99);
fprintf('La note est %g\n', Etudiant.note)
```

* Il faut faire attention, car les enregistrements sont dynamiques et une erreur
  dans le champ peut créer un nouveau champ
```MATLAB
Etudiant = struct('nom', 'Leblanc', 'prenom', 'Hugo', 'note', 99);
Etudiant.ntoe = 100
fprintf('La note est %g\n', Etudiant.note) % N'affiche pas 100
```

# Fonctions avec enregistrements
* Les enregistrements peuvent être des paramètres de fonctions :
```MATLAB
function afficherEtudiant(Etudiant)
fprintf('nom : %s\n', Etudiant.nom)
fprintf('prenom : %s\n' Etudiant.prenom)
fprintf('note : %g\n', Etudiant.note)
end
```

# Exercices
* Écrivez une fonction qui trouve la position de ligne et colonne du minimum
  d’un tableau de deux dimensions. Un enregistrement contenant la ligne et la
  colonne sera retourné.
* Écrivez la même fonction, mais, qui peut trouver un tableau de position minimum.