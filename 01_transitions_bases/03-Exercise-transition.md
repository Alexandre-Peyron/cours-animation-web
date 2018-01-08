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

