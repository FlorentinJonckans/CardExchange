# RandomQuotes
[Angular CLI](https://github.com/angular/angular-cli) version 9.1.3.
## Development server
Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## 1. Introduction

Bonjour, nous vous présentons un projet réalisé avec le framework Javascript [Angular](https://angular.io/). Le but de ce projet vise à générer de manière aléatoire, des citations d'auteurs.

## 2. Principes de fonctionnement

Angular est un framework Javascript côté client qui permet de réaliser des applications de type "Single Page Application". 

Ce framework est basé sur une architecture de composants indépendants les uns des autres. 
Une fois le composant principal chargé, il analyse la vue `html` correspondant à celui-ci et détecte s'il comporte d'autres composants. Si c'est le cas, Angular va trouver toutes les correspondances et exécuter le code lié à celles-ci. 

On peut imbriquer autant de composants que l'on souhaite.

Un composant dans Angular sert à générer une partie de code `html` et fournir des fonctionnalités à celle-ci. C'est pour cela qu'un composant est constitué d'une classe dans laquelle on pourra définir la logique d'application pour ce composant avec des propriétés, des méthodes etc... .

### Pour ajouter un composant

Dans une application Angular, il est recommandé d'imbriquer un ou plusieurs composants pour faciliter la visibilité de ces derniers.

Avec la commande `ng generate component nomduComposant` à la racine du projet, un dossier avec le nom du composant va être créer dans lequel quatre autres fichiers vont être créer : un fichier .component.ts, .component.html, .component.css, .component.spec.ts .

`.component.ts` = fichier dans lequel on aura une classe, propriétés ...
`.component.html` = fichier servant à afficher la vue.
`.component.css` = fichier appliquant une feuille de style sur la vue.
`.component.spec.ts` = fichier pour faire des test sur le fichier `.component.ts`.

### Afficher des données dans la vue

Pour cela, nous allons nous servir de l'interpolation dans le `.component.html`, soit des doubles accolades qui rendra un contenu de type string sur notre vue.

### Système d'événements

Pour lier des évènements depuis le template vers le composant, on utilisera la syntaxe d'Angular prévue à cet effet. Par exemple, pour lier un "click" vers notre composant, on va insérer (click)="nomMethode()" dans la balise souhaitée et on déclarera également cette méthode dans notre composant qui contiendra la logique de l'action.

### Système de service



## 3. Installation

Documentation : https://www.javatpoint.com/angular-8-installation .

Pour installer Angular, il faut d'abord installer [NodeJs](https://nodejs.org/fr/).
Pour vérifier que vous avez bien installé [NodeJs](https://nodejs.org/fr/), faites la combinaison `Windows+r` puis tapez `cmd` pour ouvrir l'invite de commande, et entrez la commande `node -v`.

Une fois que vous avez bien installé [NodeJs](https://nodejs.org/fr/) dans l'invite de commande, tapez `npm install -g @angular/cli`.

Vous pouvez vérifier que Angular est bien installé via la commande `ng --version`.
