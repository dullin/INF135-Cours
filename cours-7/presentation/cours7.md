---
title: INF135 - Validation et fichiers externes
author: Hugo Leblanc
date: Cours 7
pandocomatic_:
  use-template:
  - presentation
  - presentation-handout
...

# Objectifs de la semaine
* Validation avec `validateattributes`
* Fichiers externes

# Validation avec `validateattributes`
* `validateattributes` permet de valider rapidement et efficacement les paramètres d'entrées de fonctions.
* La fonction reçoit trois paramètres:
  * La variable à valider;
  * Le type voulu de la variable;
  * Une liste de caractéristique voulue à valider.
* L'utilisation des deux derniers paramètres demande des tableaux de cellules. Nous n'irons pas dans les détails de leurs utilisations.

# Exemple d'utilisation de `validateattributes`
```MATLAB
% Valide que x est un entier scalaire (1x1) positif paire.
validateattributes(x, {'numeric'}, {'scalar', 'positive', 'even'})

% Valide que vec est un vecteur de valeur plus grande que 5.
validateattributes(vec, {'numeric'}, {'vector', '>', 5})

% Valide que chaine est une chaine de caractères avec 6 lettres (éléments)
validateattributes(chaine, {'char'}, {'scalartext', 'numel', 6})
```

# Les fichiers externes
* MATLAB peut accéder à des fichiers externes. Ces fichiers vont rester après l'exécution de notre programme, contrairement aux variables. Il est donc possible de garder de l'information de manières permanentes.
* Deux types de fichiers seront étudiés dans le cours:
  * Fichier texte (ASCII)
  * Fichier binaire
* Pour travailler avec les fichiers, des fonctions spécifiques seront utilisées pour leurs gestions.
* Un concept d'identificateur de fichier permet de faire référence à un fichier autrement que par son nom.

# Identificateur de fichier (fid)
* Pour ne pas avoir à redonner le nom de fichier à chaque fonction, un identificateur de fichier est utilisé pour représenter le fichier durant ses interactions avec MATLAB.
* La fonction `fopen` génère un nouvel identificateur de fichier qui sera utilisé par les fonctions subséquentes. Seule la fonction `fopen` a donc besoin du nom de fichier.
* L’identificateur de fichier est seulement un chiffre qui permet à MATLAB de savoir avec quel fichier interagir.
* L’identificateur de fichier permet aussi à MATLAB de garder la position d’un curseur dans le fichier. On peut donc lire plusieurs informations sans repartir du début du fichier.
* Pour arrêter les interactions avec le fichier, la fonction `fclose` permet de libérer l’utilisation de l’identificateur pour MATLAB.

# Ouverture de fichier
* `fopen` permet d'ouvrir un fichier et générer un identificateur de fichier. L'utilisation de base ne demande que le nom du fichier. Ce fichier sera recherché dans le dossier courant.
* `fopen` retourne -1 si il y a un problème. Par convention, nous allons toujours vérifier que le fid n'est pas -1 après une ouverture de fichier.
```MATLAB
fid = fopen('nomFichier.txt');
assert(fid ~= -1)
```

# Ouverture en écriture et fermeture
* `fopen` ouvre le fichier en lecture par défaut. Un deuxième paramètre permet d'ouvrir le fichier en écriture.
* Si le fichier n'existe pas, il sera créé.
```MATLAB
% Ouverture en écriture, efface le contenu
fid = fopen('nomFichier.txt', 'w');
% Ouverture en ajout du fichier courant
fid = fopen('nomFichier.txt', 'a');
```
* `fclose` prends un identificateur et le ferme.
```MATLAB
fclose(fid)
```

# Écriture de fichier texte
* La fonction `fprintf` permet d'écrire dans un fichier texte à la place de la fenêtre de commande. Suffit de lui indiquer l'identificateur de fichier voulu.
```MATLAB
fprintf(fid, 'Allo le goupe %g!\n, 1)
```

# Lecture de ligne de texte
* `feof` permet de détecter si le curseur est à la fin du fichier;
* `fgetl`/`fgets` retourne une ligne de texte du fichier;
  * `fgetl` retourne sans le caractère de saut de ligne;
  * `fgets` retourne avec le caractère de saut de ligne.

```MATLAB
while ~feof(fid)
  chaineLigne = fgetl(fid)
  fpritnf('%s\n', chaineLigne)
end
```
* `fscanf` permet de faire la lecture de valeurs précise. Un peu comme un fprintf à l'envers.

# Exercice
* Trouvez le nombre de caractères sur la ligne ayant le plus grand nombre de caractères dans le fichier O_Canada.txt
* Écrivez un appel de fscanf qui lit le fichier donnees_formates3.txt et retourne toutes ses valeurs.
* Écrivez un/des appel(s) de fscanf qui lit le fichier donnee_formatees4.txt et retourne toutes ses valeurs.

# Écriture de fichier binaire
* `fwrite` permet d'écrire dans un fichier binaire.
* On doit spécifier le type de l'information à écrire pour que `fwrite` décide de la place à prendre pour l'écriture.
* Les types que nous utiliserons sont:
  * `int32` pour les nombres entiers;
  * `double` pour les nombres réels;
  * `char` pour les chaines de caractères

```MATLAB
% Écrire la valeur 34 (un entier) dans un fichier binaire.
fwrite(fid, 34, 'int32')
% Écrire une matrice de nombres réels.
fwrite(fid, [1 2 3; 4 5 6], 'double')
% Écrire une chaine.
fwrite(fid, 'allo', 'char')
```

# Lecture de fichier binaire
* `fread` fait la lecture de fichier binaire.
* L'utilisation demande un nombre d'éléments à aller lire.

```MATLAB
% Lire une valeur d'un entier.
entier = fread(fid, 1, 'int32')

% Lire une matrice 2x3 de réels.
mat = fread(fid, [2 3], 'double')

% Lire une chaine qui va jusqu'à la fin du fichier.
chaineLu = fread(fid, 'char')
% fread donne des vecteur colonne et la chaine doit
% être un vecteur ligne
chaine = chaineLu'
```
