# Loader 4 Dots

Dans cet exercice nous allons créer une animation de chargement. Un loader à 4 points.

L'objectif étant de travailler les animations de mouvement ainsi que la propriété `filter`.

Le résultat attendu est celui-ci : 

![CanIUse Transition](img/loader-dots.gif "Loader Dots")

Téléchargez le fichier suivant et travaillez directement dessus : [fichier](Loader-dot.html)


### Le premier point

Animons le premier point.

Pour cela, créez une animation infinie qui déplace le point de gauche à droite.

Plus exactement de *96px* pendant 3s aller-retour.

### Les 3 autres points

A présent, déplaçons les 3 autres points.

Créez une animation qui déplace d'un seul bloque les 3 points de 31px pendant 3s.

### Filtre et contrast

L'animation est complète concernant le mouvement mais il manque le côté sticky/collant qui lui donne tout son charme.

Pour cela, on va utiliser des proprités un peu particulière et assez rarement utilisées `Filter` et `Contrast`.

Ajoutez la ligne suivante à votre div .loader : 
- filter: contrast(20);

Maintenant, ajoutez la ligne suivante à vos .dot et .dots :
- filter: blur(4px);

Et voilà le travail !

 