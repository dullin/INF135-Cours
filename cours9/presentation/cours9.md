---
title: INF135 - Classe et propriétés
author: Hugo Leblanc 
date: Cours 9
pandocomatic_: 
  use-template:
  - presentation
  - presentation-handout
---

# Objectifs de la semaine
* Programmation orientée objet;
* Définition de classe `classdef`;
* Propriétés;
* Création d'objets;
* Utilisation d'objets.

# Programmation orientée objet
* La programmation orientée objet est un autre paradigme de programmation qui vient s'ajouter à la programmation procédurale que nous utilisons;
* Le principe fondamental est de catégoriser les éléments d'une problématique en objets qui interagissent entre eux;
* Nous verrons plus en détail les principes majeurs de la Programmation orientée objet (POO) plus tard.

# Définition de classe `classdef`
* Le `classdef` permet de décrire les propriétés et les méthodes d'une classe;
* Le `classdef` est un fichier à part entière comme un script ou une fonction;
* Par convention, toutes nos classes auront comme première lettre une majuscule;
* Le `classdef` est un fichier descriptif; Il n'est pas exécuté de manière procédurale comme les autres fichiers rencontrés jusqu'ici.

# Propriétés
* Une classe avec de propriétés s'apparentes beaucoup à un enregistrement avec de meilleurs mécanismes de programmation défensive;
* Les propriétés seront déclarées dans la classe et pourront être utilisées par les instances (objets) de la classe.

# Exemple d'un `classdef`
~~~MATLAB
classdef MaClasse
    properties
        x
        y
    end
    methods
        % Nous verrons les méthodes plus tard.
    end
end
~~~

# Création d'objets
* La classe est une description d'un élément. À elle-même, il n'y a rien de tangible;
* La création de versions tangibles de la classe se nomme l'instanciation et cela permet de créer des objets tangibles;
* Les objets auront accès à des valeurs précises dans les différentes propriétés fournies par la classe;
* La création des objets se fait avec le constructeur. Le constructeur est une fonction qui porte le même nom que la classe.

~~~MATLAB
obj1 = MaClasse()
obj2 = MaClasse()
~~~

# Utilisation d'objets
* L’utilisation des objets ressemble aux enregistrements;
* Les propriétés sont accessibles avec le nom de l'objet suivi d'un point et le nom de la propriété;
* Les objets ne sont pas dynamiques par rapport à leurs propriétés. Seules les propriétés définies dans la classe sont accessibles.

~~~MATLAB
obj1.x = 45;
fprintf('%g\n', obj1.x)
~~~

# Valeur par défaut
* Il est possible d'assigner une valeur par défaut à une propriété. La valeur par défaut sera assignée à la création de l’objet.

~~~MATLAB
classdef MaClasse
    propertie
        x = 0
        y = 0
    end
end
~~~