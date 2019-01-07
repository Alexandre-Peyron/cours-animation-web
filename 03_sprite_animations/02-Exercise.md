# Animation Sprite

### Créer le sprite

Téléchargez les sources suivantes : [Knight.zip](../sources/freeknight.zip)

Ici les images sources sont séparées, trouver un outil permettant de générer des sprites.

On va travailler sur l'animation de saut (Jump).

Il faut que les images de votre sprite soient sur une seule ligne horizontale.


### CSS

Propriétés de base
```css
.knight {
  width: 587px;
  height: 707px;
  background: url('knight-jump-sprite.png');
}
```

On crée le keyframes.
```css
@keyframes jump {
   100% { background-position: -["587px * le nombre d'image de votre sprite"]; }
}
```
A chaque étape de l'animation la position X du background position sera modifiée.


Création de l'animation
```css
.knight {
  ...
  animation: jump 0.8s steps(nb image de votre animation) infinite;
}
```
Tout se passe ici :
- on associe l'animation jump
- d'une durée de 800ms
- on divise l'animation en 10 étapes
- elle est jouée indéfiniment 


### Amélioration de l'animation

L'animation se produit, mais votre personnage ne saute pas encore.

Mettez en place le `transition transform` pour améliorer votre animation.

Utilisez les conseils de [cet article](https://css-tricks.com/making-css-animations-feel-natural/) pour améliorer le rendu de votre animation


### Keyboard Event

Enlevez le infinite.

Faites en sorte que l'animation se déclanche lorsqu'on appuie sur la flèche du haut du clavier.

Toujours à faire en vanilla JS.


### Autres

Ajoutez les animations suivantes : 
- déplacement à droite (flèche droite du clavier)
- déplacement à gauche
- animation d'attaque lorsqu'on presse la barre d'espace
- créez un moteur physique de rendu de la gravité et des collisions
