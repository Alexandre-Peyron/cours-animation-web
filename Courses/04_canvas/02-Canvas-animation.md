# Canvas Animation

### Les transformations

Comme en CSS, il est possible d'appliquer des transformations sur les éléments d'un canvas.

Utilisez ce fichier avec un canvas déjà déclaré : [fichier](02-Canvas-animation.html)

Créez un cercle rouge : 

```javascript
ctx.beginPath();
ctx.strokeStyle = "red";
ctx.lineWidth = 5;
ctx.arc(0, 0, 100, 0, Math.PI * 2);
ctx.moveTo(0, 0);
ctx.lineTo(100, 0);
ctx.stroke();
```

Appliquez les transformations suivantes et observez le résultat.

```javascript
ctx.translate(200, 200);
```

```javascript
ctx.rotate(Math.PI / 2);
```

```javascript
ctx.scale(2, 2);
```

### Les animations

Ok, ça transforme mais ça bouge pas beaucoup tout ça ! On y vient.

Pour créer des animations en canvas, on fait ça en JavaScript directement 
et on utilise la méthode [requestAnimationFrame](https://developer.mozilla.org/fr/docs/Web/API/Window/requestAnimationFrame)

Elle va être utilisée ainsi : 

```javascript
function render() {
    // Ici nos éléments à animer

    requestAnimationFrame(render);
}

requestAnimationFrame(render);
```

Cette méthode prend en paramètre une fonction (ici render) qui sera exécuté au prochain rafraichissement d'image.
A la fin de notre fonction, on rappelle cette même fonction. C'est ce qu'on appelle de récursivité (une fonction qui s'appelle elle-même).

Cela crée une boucle infinie sur la fonction render, qui créera un rendu d'image à chaque rafraichissement d'image à une cadence d'environ 60 images par seconde.

Pour bien comprendre complétons notre exemple :


```javascript
function render(timestamp) {
    ctx.beginPath();
    ctx.scale(1.05, 1.05); // A chage itération, on multiplie le scale de cette valeur
    ctx.strokeStyle = "red";
    ctx.lineWidth = 5;
    ctx.arc(175, 175, 100, 0, Math.PI * 2);
    ctx.moveTo(175, 175);
    ctx.lineTo(275, 175);
    ctx.stroke();
    ctx.closePath();

    requestAnimationFrame(render);
}

requestAnimationFrame(render);
```

Testez et observez !

Comme tout à l'heure, on crée un cercle. 
Et à chaque itération on augmente le scale (l'échelle) de notre cercle.

Sauf que !

Le fonctionnement d'un canvas, c'est qu'à chaque itération, il crée une nouvelle image complète qui s'ajoute aux précédentes.
Ce qui donne cet effet de tunnel.

Pour corriger le comportement, il faut effacer le canvas au début de chage itération avec cette méthode :

```javascript
ctx.clearRect(0, 0, innerWidth, innerHeight);
```

Travaillons maintenant sur le x de notre élément et ajoutons des conditions :

```javascript
var x = 1;
var xVariation = 1; // A modifier pour changer la vitesse de déplacement

function render(timestamp) {
    ctx.clearRect(0, 0, innerWidth, innerHeight);

    ctx.beginPath();
    ctx.strokeStyle = "red";
    ctx.lineWidth = 5;
    ctx.arc(x, 175, 100, 0, Math.PI * 2);
    ctx.moveTo(x, 175);
    ctx.lineTo(x + 100, 175);
    ctx.stroke();
    ctx.closePath();

    x += xVariation;

    // On fixe des limites, à chaque bord, on change la direction du mouvement
    if (x > 650  || x < 0) {
        xVariation = -xVariation;
    }

    requestAnimationFrame(render);
}

requestAnimationFrame(render);
```

Voilà, vous avez maintenant les bases de l'animation avec un Canvas.

