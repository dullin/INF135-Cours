---
title: INF135 - Classe et méthodes
author: Hugo Leblanc 
date: Cours 10
pandocomatic_: 
  use-template:
  - presentation
  - presentation-handout
---

# Principe de programmation orientée objet
* La programmation orientée objet est un concept de programmation où un problème est caractérisé par des objets sur lesquels on agit.
* La programmation orientée objet utilise un concept d’une définition de classe (recette) qui permet de générer des objets (biscuits) de ladite classe.
* La définition de la classe va caractériser l’objet (properties) ainsi que définir les comportements de l’objet (méthodes).

# Méthodes
* Les méthodes sont des fonctions qui sont attachées à notre classe.
* Les méthodes auront accès aux différentes propriétés des objets des classes définies.
* On peut redéfinir des fonctions prédéfinies avec la redéfinition de fonctions.
* Les fonctions définies dans le bloc de méthodes appartiennent à la classe et ne peuvent pas être utilisées de l’extérieur.

# handle
* L’option handle doit être ajoutée au début de notre définition de classe.
* Les fonctions (autre que le constructeur) auront comme premier paramètre l’objet sur lequel on travaille.
* Étant l’objet, on peut utiliser les propriétés de l’objet à l’intérieur des méthodes en les accédants par le premier paramètre.

~~~MATLAB
classdef MaClasse < handle % TOUJOURS AJOUTER CECI
    % Reste du classdef
end
~~~

# Définitions des méthodes
* La définition de méthodes se fait dans le bloc methods d’une définition de classe.
* On peut définir plusieurs fonctions l’une après l’autre dans les blocs de méthodes qui seront attachées à la classe.
* Les méthodes auront accès aux propriétés de la classe. On peut donc les utiliser à l’intérieur de nos fonctions.
* Des règles supplémentaires sont requises pour l’implémentation des fonctions dans le bloc de méthodes.
* Plusieurs types de fonctions sont disponibles dans le bloc de méthodes (constructeur, redéfinition, etc.)

# Exemple de classe avec des méthodes
~~~MATLAB
classdef MaClasse < handle
    properties
        x
        y
        z
    end
    methods
        function maMethod1(obj) % Premier paramètre obligatoire
            % Utilise la référence pour l'accès aux propriétés.
            obj.z = obj.x + obj.y;
        end
        function [retour] = methodAvecRetour(obj, arg1)
            retour = arg1 + obj.z;
        end
    end
end
~~~

# Utilisation de méthodes
* Une fois l’objet créé on peut les utiliser comme avec leurs méthodes.
* On peut utiliser les méthodes avec les objets correspondants.
* L’utilisation des méthodes est activée avec le ‘.’, on a le nom de l’objet suivi de la fonction.
* Si l’on utilise la forme courte (avec ‘.’), on peut omettre le premier paramètre de la fonction (qui est l’objet lui-même).

# Exemple d'utilisation de méthode
~~~MATLAB
mc1 = MaClasse; % Création de l'objet
mc1.x = 45;
mc1.y = 23; % Assignation des propriétés
% Appel de la méthode maMethod1. Remarquez l'omission du premier paramètre.
% Les modifications de propriétés dans la fonction reste,
% contrairement aux fonctions normales.
mc1.maMethod1

% Appel d'une méthode avec un retour
% Le premier paramètre envoyé à l'appel sera le deuxième de la définition.
% Ici, la valeur 34 sera assignée au paramètre d’entrée arg1 de la méthode.
maReponse = mc1.methodAvecRetour(34)
~~~

# Exercice
* Écrivez une classe qui représente un étudiant avec les propriétés suivantes:
    * nom
    * code permanent
    * liste de notes d'examens
* Ajoutez à la classe une méthode qui ajoute un examen à liste des notes d'examens.
* Ajoutez à la classe une méthode qui retourne la moyenne des notes d'examens. Valide qu'il y a au moins un examen dans la liste d'examens.
* Écrivez un script qui construit un objet de type Etudiant et remplit son nom et code permanent. Ajoute ensuite deux examens avec la méthode écrite plus haut. Affiche finalement la moyenne de l'étudiant en utilisant la méthode écrite plus haut.

# Constructeur
* On peut avoir un constructeur précis qui remplace (redéfini) le constructeur par défaut. Le nom de la fonction du constructeur doit être la même que le nom de la classe.
* La fonction constructrice ne pourra qu’avoir qu’une seule valeur de retour qui sera automatiquement l’objet créé.
* On peut assigner les propriétés de l’objet avec un accès des propriétés de la valeur de retour.
* On valide habituellement le nombre de paramètres d’entrée pour être capable de créer un objet avec les champs vides si l’on ne donne aucun paramètre au constructeur.

# Exemple d'une classe avec un constructeur
~~~MATLAB
classdef MaClasse < handle
    properties
        x
        y
    end
    methods
        function [obj] = MaClasse(x, y)
            if nargin == 2
                obj.x = x;
                obj.y = y;
            end
        end
    end
end
~~~

# Exercice
* Ajoutez un constructeur à la classe Etudiant qui reçoit le nom et le code permanent et assigne leurs propriétés en conséquence.

# Classes imbriquées
* Les classes peuvent être imbriquées l’une dans l’autre.
* Habituellement, on appel le constructeur MaClasse.empty sur la propriété par défaut.
* L’utilisation de la méthode courte d’appels devient encore plus puissante ici. Ex: objet1.objet2.fcnobj2
* Faire attention à la conversion de type si on ne définit pas par défaut le type.

# Redéfinition de fonctions
* On peut remplacer des méthodes de fonctions qui existent déjà dans MATLAB.
* La redéfinition remplace l’utilisation normale des fonctions par notre implémentation.
* La redéfinition est habituellement utilisée pour le constructeur, les fonctions arithmétiques (plus, minus, mddivide) et les fonctions de comparaison (eq, gt, lt, le, ge, ne).
Cela permet de faire de la comparaison directe sur les objets avec les opérateurs habituels ( ==, >, <, <=, >=, ~=).
* On remplace souvent la fonction `char` et `disp` pour prendre le contrôle de l'affichage des objets.

# Exemple de la redéfinition de l'affichage
~~~MATLAB
classdef Point2D < handle
    properties
        x
        y
    end
    methods
        function [chaine] = char(obj)
            chaine = sprintf('Le x est : %g \n', obj.x);
            chaine = [chaine sprintf('Le y est : %g \n', obj.y)];
        end
        function disp(obj)
            fprintf('%s', obj)
        end
    end
end
~~~

# Attributs des propriétés
* Les propriétés peuvent avoir des attributs pour limiter ou configurer l'accès aux propriétés.
* Les attributs possibles sont les suivants :
    * `Access = private` : Limite l'utilisation des propriétés aux méthodes de la fonction;
    * `SetAccess = private` : Limite les modifications des propriétés;
    * `GetAccess = private` : Limite les lectures des propriétés;
    * `Constant = true` : Permet une seule assignation à la propriété;
    * `Dependant` : La propriété est calculé avec des méthodes pour l'accès et la modification.

# Exemple d'attributs de propriétés
~~~MATLAB
classdef MaClass < handle
    properties
        x
    end
    properties (SetAccess = private)
        y
    end
    properties (Constant = true)
        MA_CONSTANTE = 4
    end
end
~~~

# Propriétés dépendantes
* Les propriétés dépendantes ne sont pas accessibles comme valeur. Leur information est calculée avec une méthode à chaque accès ou modification.
* Le nom des méthodes utilise le nom de la propriété pour que MATLAB les identifie correctement.

# Exemple de propriétés dépendantes
~~~MATLAB
classdef MaClasse < handle
    properties
        x
        y
    end
    properties (Dependent)
        z
    end
    methods
        function [z] get.z(obj)
            z = obj.x + obj.y;
        end
        function set.z(obj, z)
            obj.x = z - obj.y;
        end
    end
~~~

# Classe d'énumération
* Une classe d’énumération permet d’avoir l’énumération d’élément qui n’a pas de valeur intrinsèquement rattachée. 
* Le bloc d’énumération prend la place des propriétés. 
* On peut ensuite invoquer une “valeur” de l’énumération en utilisant NomClasse.ValeurEnumeration . 
* Les énumérations peuvent avoir des méthodes qui travaillent sur les valeurs possibles des énumérations.

# Exemple d'une classe d'énumération
~~~MATLAB
classdef MonEnum
    enumaration
        A
        B
        C
    end
end
~~~

# Validation de classe
* `isequal(a,b)` - Détermine si deux éléments sont égaux. On regarde ici toutes les propriétés et on les compare;
* `isa(x,'type')` - Détermine si un élément est d’un type spécifique.

# Méthodes statiques
On peut avoir besoin de créer des méthodes qui n’ont pas besoin de l’objet lui-même. Il faut faire attention de n’avoir ni besoin des propriétés ni des méthodes. 
On peut avoir un bloc de méthode avec l’option Static qui permet de faire abstraction de la règle de l’option handle. 
On peut donc avoir des fonctions ‘normales’ qui sont rattachées à une classe.

# Exemple de méthodes statique
~~~MATLAB
classdef MaClasse < handle
    properties
        x
        y
    end
    methods (Static)
        function [c] = fcn1(a, b)
            c = a + b;
        end
    end
end
~~~

# Dossier de classe
* On peut diviser une classe qui devient trop grande en multiple fichier 
* Pour se faire, il faut un dossier avec le nom @MaClasse. Les fichiers appartenant à la classe y seront. 
* Le dossier doit contenir un fichier du même nom où il y aura une définition du constructeur ainsi que des propriétés. 
* On peut avoir les autres méthodes dans des fichiers séparés de fonctions. 
* Si certaines méthodes ont besoin d’options, précise (Access, Static). Il faut spécifier le prototype de ses méthodes dans le fichier du constructeur.