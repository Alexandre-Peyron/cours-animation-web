# Exercice sur les transitions

Le but final de l'exercice est de créer une interface qui permet de manipuler la propriété `transform` 
d'une div présente dans la page.

Pour cela, on va créer une `div#target`

```css
/* Vous utilisez la taille et la couleur que vous voulez */
#target {
  width: 200px;
  height: 200px;
  background-color: crimson;
}
```

On va ensuite créer 4 boutons d'interface qui nous permettrons d'activer ou non chacune des transformations suivantes :

- translate - (100px, 0)
- rotate - (45deg)
- scale - (2, 2)
- skew - (30deg, 20deg)

Encore une fois, vous utilisez les valeurs que vous souhaitez.

Au click sur un bouton, cela ajoutera ou supprimera une class sur notre `div#target` qui activera ou non la transformation.

Pour la gestion des class, on va biensûr utiliser du JavaScript, mais du Vanilla JS uniquement.


### Pour aller plus loin

Vous pouvez ajouter les transformations suivantes :

- translate3d
- translateZ
- scale3d
- scaleZ
- rotate3d
- perspective

### Pour aller plus loin 2

Sur la même page, à la suite, nous allons créer une `div#target2`.

Cette fois-ci, pas de boutons, mais un tableau de 2x3 avec des `input[type=text]`.
Chaque case du tableau va nous permettre de manipuler la propriété `matrice transform`.

Cette fois, pas d'ajout de classe, mais directement du css inline généré depuis le JavaScript.

