# Pseudo-classes

Une pseudo-classe est un mot-clé qui s'ajoute à un sélecteur afin de l'appliquer dans un état spécifique. 

La pseudo-classe `:hover` est la plus connue. Elle permet d'appliquer une mise en forme spécifique lorsque l'utilisateur survole l'élément ciblé par le sélecteur.

Exemple de code CSS : 
```css
button {
  background-color: magenta;
}

button:hover {
  background-color: rebeccapurple;
}
```

Au survol, le `button` va passer de la couleur `magenta` à `rebecccapurple`.


### Compatibilité
 
Beaucoup de pseudo-classes existent. 

Et de nouvelles sont intégrées régulièrement dans la norme CSS.

[https://developer.mozilla.org/fr/docs/Web/CSS/Pseudo-classes#Liste_des_pseudo-classes_standards](https://developer.mozilla.org/fr/docs/Web/CSS/Pseudo-classes#Liste_des_pseudo-classes_standards)
Ici se trouve la liste des pseudo classes disponibles. Attention, celles associées à une fiole sont expérimentales et sont amenées à évoluer voire disparaitre.

Les plus utilisés : 
- [:hover](https://developer.mozilla.org/fr/docs/Web/CSS/:hover)
- [:first-child](https://developer.mozilla.org/fr/docs/Web/CSS/:first-child) (sélectionne le premier élément d'une liste)
- [:last-child](https://developer.mozilla.org/fr/docs/Web/CSS/:last-child) (dernier élément d'une liste)
- [:nth-child(X)](https://developer.mozilla.org/fr/docs/Web/CSS/:nth-child) 
- [:focus](https://developer.mozilla.org/fr/docs/Web/CSS/:focus) (quand l'utilisateur prend le focus sur un élément, curseur présent dans un input/textarea)
- [:required](https://developer.mozilla.org/fr/docs/Web/CSS/:required) (élément de formulaire qui est obligatoire)


### Exercices 

Téléchargez le fichier suivant et travaillez directement dessus : [fichier](01-Pseudo-classes.html)

Ce fichier contient un bouton avec un style initial. L'objectif est d'ajouter un comportement au hover.

Modifiez notre bouton pour ajouter successivement les propriétés suivantes au hover et observez les changements :
- la couleur de fond
- la couleur du texte (white)
- la bordure (couleur et taille)
- l'arrondi de la bordure
- le padding



***

[Exercice suivant → Les Pseudo-éléments](02-Pseudo-elements.md)