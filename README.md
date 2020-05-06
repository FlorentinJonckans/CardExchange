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

Les composants ne doivent pas ni récupérer ni enregistrer directement les données. Ils doivent uniquement se concentrer sur la présentation des données. 

Pour ce faire, nous allons déléguer l'accès aux données à un service.
La commande `ng generate service nomDuService` permet de créer un service.

Les services sont un excellent moyen de partager des informations entre des classes qui ne se connaissent pas. 

### Utilisation d'un service

Pour utiliser un service depuis un composant, il faut tout d'abord l'importer dans le fichier `app.module.ts` et le déclarer dans la section `providers`. Il faut également importer le service dans le composant dans lequel on souhaite l'utiliser. 

Nous devons ensuite créer un constructeur afin de pouvoir effectuer une injection de constructeur Angular. Pour ceci, on va déclarer le service comme paramètre privé du constructeur en specifiant son type. Et on pourra ainsi utiliser toute la logique du service depuis ce composant.

export class QuoteBoxComponent {
  public quote = new Quote('', '');
  constructor(public quoteService: QuoteService) {
    ...
  }

## 3. Installation

Documentation : https://www.javatpoint.com/angular-8-installation .

Pour installer Angular, il faut d'abord installer [NodeJs](https://nodejs.org/fr/).
Pour vérifier que vous avez bien installé [NodeJs](https://nodejs.org/fr/), faites la combinaison `Windows+r` puis tapez `cmd` pour ouvrir l'invite de commande, et entrez la commande `node -v`.

Une fois que vous avez bien installé [NodeJs](https://nodejs.org/fr/) dans l'invite de commande, tapez `npm install -g @angular/cli`.

Vous pouvez vérifier que Angular est bien installé via la commande `ng --version`.

## 4. Création d'une mini application Angular


Le but de ce projet vise à générer de manière aléatoire, des citations d'auteurs.
Pour cela, nous allons utiliser les différentes fonctionnalités de [Angular](https://angular.io/).

Tout d'abord, nous avons besoin de créer le projet grâce à la commande `ng new votre_projet`.
ensuite, nous aurons besoin d'installer deux packages via la commande npm :

-`npm install boostrap`.
-`npm install font-awesome`.

Nous allons créer un répertoire nommé `models` dans le src de notre projet puis nous allons créer un fichier `quote.class.ts`
qui nous permettra d'instancier plus tard un objet `Quote`.

Nous allons créer un répertoire nommé `services` dans le src de notre projet.
Puis, nous allons créer un fichier `quote.service.ts` dans laquelle nous allons créer une fonction qui nous permettra de récupérer des citations depuis le site [stormconsultancy](http://quotes.stormconsultancy.co.uk/random.json).

Maintenant, nous allons créer notre composant `quote-box`.

La commande `ng g c quote-box` va nous générer automatiquement le composant `quote-box` avec un fichier `.component.html`, `.component.css`, `.component.ts` et `.component.spec.ts`.

Dans le fichier `.component.ts`, nous allons créer une fonction `getQuote()` afin d'instancier la class `quote` avec les données récupérer par le service.

Dans le `.component.html`, il suffit d'utiliser l'objet `quote` afin de récupérer les données et les afficher.

Pour ajouter des routes à notre projet, il faudra ajouter le code ci-dessous dans le fichier `app.module.ts` au niveau des imports.

`RouterModule.forRoot([
      {
        path: ''
        component: HomeComponent
      },
      {
        path: 'quote',
        component: QuoteBoxComponent
      }
    ]`

Quand on lance l'application, nous accéderons au composant `home` par défaut et nous pouvons faire un lien vers `/quote`.

