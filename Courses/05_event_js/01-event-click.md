# Évènements JavaScript

Pour aller plus loin en animation, vous aurez souvent besoin d'ajouter du JavaScript.

Notamment pour pouvoir "écouter" les actions utilisateur et agir en conséquence.


### Le Click

Sur un fichier [vierge](01-event-click.html), créez un carré de 200x200px avec une couleur de background et dont l'ID est "square".

A présent, au click nous allons ajouter ajouter une classe à notre carré pour en changer la couleur.

Dans des balises JavaScript, ajoutez le code suivant : 

```javascript
let elemSquare = document.querySelector('#square'); // On met dans une variable notre carré pour pouvoir le manipuler

elemSquare.addEventListener('click', () => { // Ici on écoute le click sur le carré 
    elemSquare.classList.add('onclick'); // Ici on ajoute une class "onclick"
});

```

A présent, dans votre CSS, lorsque la classe "onclick" est présente modifiez la couleur de background.

Pour aller plus loin, lorsqu'on reclick sur le carré cela supprime la classe.

### Mouseenter et Mouseleave

Refaite le même exercice où :
- mouseenter ajoute une class
- mouseleave la supprime


### Liste des évènements d'interaction utilisateur

Vous pouvez écouter l'ensemble de ces évènement sur une page : 
- click
- mousedown
- mouseup
- mouseover
- mousemove
- mouseenter
- mouseleave
- touch (sur mobile)
- touchstart
- touchend
- touchenter
- touchmove
- focus (dans un input ou textarea)
- focusin (dans un input ou textarea)
- focusout (dans un input ou textarea)
- keypress (touche du clavier)
- keydown
- keyup

Vous pouvez trouver des exemples plus complet [ici](https://developer.mozilla.org/fr/docs/Apprendre/JavaScript/Building_blocks/Ev%C3%A8nements).


-> [La correction]() 