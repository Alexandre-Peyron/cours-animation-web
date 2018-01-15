### Sprite Animations

Un sprite est une image contenant plusieurs images. En CSS, on va jouer sur la propriété `background-position`
pour afficher l'image souhaitée en fonction du contexte.

Un sprite est utilisé dans 2 cas :

- sur le web classique, afin de regrouper l'ensemble des images de design et icônes en une image et 
ainsi limiter les requêtes http. Tout ceci dans un soucis de performance

- dans le cas d'une transition d'image, type dessin animé. 

C'est ce 2e cas qu'on va voir aujourd'hui.

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
  animation: jump 0.8s steps(10) infinite;
}
```
Tout se passe ici :
- on associe l'animation jump
- d'une durée de 800ms
- on divise l'animation en 10 étapes
- elle est jouée indéfinimant 