### Définition Animations

La transition et l'animation, nous permettent d'animer des changements de propriétés sur des éléments HTML.
Dans les 2 cas, nous avons un état de départ et un état de fin.

La puissance de l'animation réside dans le fait qu'on va pouvoir définir toutes (ou une partie) des étapes intermédiaires.
Et ainsi avoir un contrôle total de notre animation.

Il faut imaginer une animation, comme une timeline où à chaque image clé vous pouvez définir les propriétés de votre objet.
Si vous avez déjà utilisé Adoble Flash ou After Effet, leur gestion de la timeline correspond tout à fait à
l'idée que je veux vous faire passer ici.

Dans un nouveau fichier, créez une `div#target` dans une `div#container`

```css
#container {
  width: 100%;
  height: 300px;
  background-color: #EEE;
}


/* Vous utilisez la taille et la couleur que vous voulez */
#target {
  position: absolute;
  width: 200px;
  height: 200px;
  background-color: crimson;
}
```

On va maintenant créer notre animation

```css

#target {
  animation: booble 2s infinite;
}

@keyframes booble {
  0% {
    transform: translateY(10px);
  }
  50% {
    transform: translateY(40px);
  }
  100% {
    transform: translateY(10px);
  }
}
```

Dans le détail, on associe une animation booble à notre target, d'une durée de 2 seconde et qui loop de manière infinie.

On crée ensuite l'animation booble et on lui définit 3 étapes clées. A 0, 50 et 100% de l'animation.

