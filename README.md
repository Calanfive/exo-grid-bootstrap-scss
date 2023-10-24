# Responsive Design

## Objectifs

RÃ©aliser une interface affichable sur diffÃ©rents supports (mobile, tablette, desktop).

## Outils

### Media queries

Les media queries permettent de dÃ©finir des rÃ¨gles CSS qui ne s'appliquent que dans certains cas.

```css
@media (max-width: 600px) {
  body {
    background-color: red;
  }
}
```

```css
@media (min-width: 600px) {
  body {
    background-color: red;
  }
}
```

```css
@media (min-width: 600px) and (max-width: 800px) {
  body {
    background-color: red;
  }
}
```

### Les breakpoints

[Breakpoint de bootstrap](https://getbootstrap.com/docs/5.0/layout/breakpoints/)

### Viewport

La balise `<meta name="viewport" content="width=device-width, initial-scale=1.0">` permet de dÃ©finir la largeur de la page en fonction de la largeur de l'Ã©cran.

### Chrome device toolbar

L'outil de dÃ©veloppement de chrome permet de simuler diffÃ©rents appareils et donc diffÃ©rentes tailles d'Ã©cran.

PlutÃ´t que de multiplier les devices physiques, il est prÃ©fÃ©rable de dÃ©finir des breakpoints et de redimensionner la fenÃªtre du navigateur ou d'utiliser l'outil de dÃ©veloppement de chrome.

### Flexbox

La flexbox permet de gÃ©rer le positionnement des Ã©lÃ©ments dans un conteneur.

```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
```

### Grid

La grid permet de gÃ©rer le positionnement des Ã©lÃ©ments dans un conteneur.
Il permet de gÃ©rer le positionnement en colonnes et en lignes sans avoir Ã  utiliser des `float`.
Mais surtout, il permet de gÃ©rer les espaces vides entre les Ã©lÃ©ments.

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: 1fr 1fr 1fr;
}
```

### Frameworks CSS

Les frameworks CSS permettent de gagner du temps en proposant des composants prÃªts Ã  l'emploi.

- [Bootstrap](https://getbootstrap.com/)
- [Tailwind](https://tailwindcss.com/)

Ils ont aussi l'avantage d'Ãªtre responsive par dÃ©faut ou de proposer des classes pour le responsive.
Avant d'avoir les flexbox, les frameworks CSS Ã©taient trÃ¨s utilisÃ©s pour le responsive, surtout Bootstrap.

## Bien plus qu'une question de taille

Le responsive design ne se limite pas Ã  la taille de l'Ã©cran. Il faut aussi prendre en compte la rÃ©solution, l'orientation, le type d'Ã©cran, etc.

Souvent, on imagine que la diffÃ©rence entre un mobile et un desktop est la direction de l'Ã©cran (portrait ou paysage). 
Mais il y a aussi :
- la taille de l'Ã©cran
- la rÃ©solution
- le type d'Ã©cran (Ã©cran tactile ou non)
- la connexion internet

C'est diffÃ©rences impliquent des comportements diffÃ©rents de la part de l'utilisateur et donc une interface adaptÃ©e Ã  chaque support.
On s'imagine souvent cela comme compliquÃ© et long Ã  mettre en place.
Il est vrai que cela demande un peu de temps et de rÃ©flexion, mais beaucoup moins que ce qu'il faudrait pour crÃ©er une application mobile et une application desktop.

## Exercices

- [Le systÃ¨me de grille Ã  la bootstrap](../Briefs/11-Front-avance/exercice-1.md)
- [Les images, les tableaux et les animations](../Briefs/11-Front-avance/exercice-2.md)
- [Notre site css responsive](../Briefs/11-Front-avance/exercice-3.md)

## Ressources

- [Responsive Web Design](https://www.w3schools.com/css/css_rwd_intro.asp)
- [Media Queries](https://www.w3schools.com/css/css_rwd_mediaqueries.asp)
- [Viewport](https://www.w3schools.com/css/css_rwd_viewport.asp)
- [respnsible tables ?](https://medium.com/appnroll-publication/5-practical-solutions-to-make-responsive-data-tables-ff031c48b122)
- [images responsives](https://developer.mozilla.org/fr/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)
- [Le mobile first](https://www.ynov.com/definition/mobile-first)

# Exercice 1 - CrÃ©er un systÃ¨me de grille en scss

## Contexte

Vous Ãªtes dÃ©veloppeur web full stack. Vous avez besoin d'un systÃ¨me de grille pour votre prochain projet.

## Missions

- CrÃ©er un systÃ¨me de grille en scss de 12 colonnes
- CrÃ©er un nouveau projet vite
- IntÃ©grer le systÃ¨me de grille dans le projet
- reproduire le layout suivant: [image du rendu en taille md](https://postimg.cc/GTdJsY3f)
- en taille xs, toutes les boites doivent prendre 100% de la largeur de l'Ã©cran et Ãªtre les unes en dessous des autres

## TÃ¢ches

- CrÃ©er un nouveau projet vite
- Installer sass et modifier les fichiers html et css pour utiliser sass
- Utilisez bootstrap pour reproduire le layout
    - importer bootstrap dans le fichier html via un cdn
    - utiliser les classes de bootstrap pour reproduire le layout
    - utiliser des classes supplÃ©mentaires pour les couleurs 
- CrÃ©er un fichier scss pour le systÃ¨me de grille pour supprimer l'import de bootstrap

## Comment s'y prendre

### Utiliser bootstrap en l'important

```html
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" integrity="sha384-rbsA2VBKQhggwzxH7pPCaAqO46MgnOM80zW1RWuH61DGLwZJEdK2Kadq2F9CUG65" crossorigin="anonymous">
```

### CrÃ©er la structure et le style css sois-mÃªme

```html
<div class="row">
    <div class="col-xs-6 col-sm-3 blue">A</div>
    <div class="col-xs-6 col-sm-3">B</div>
    <div class="col-xs-6">C</div>
</div>
```

```scss
.container {
    max-width: 1200px;
    margin: 0 auto;
}

.row {
    display: flex;
    flex-wrap: wrap;
}

.col-xs-6 {
    width: 50%;
    max-width: 50%;
}

.col-sm-3 {
    width: 25%;
    max-width: 25%;
}

.blue {
    background-color: blue;
}

```