---
title: INF135 - Graphiques
author: Hugo Leblanc 
date: Cours 8
pandocomatic_: 
  use-template:
  - presentation
  - presentation-handout
...

# Objectifs de la semaine
* Graphiques de MATLAB

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
