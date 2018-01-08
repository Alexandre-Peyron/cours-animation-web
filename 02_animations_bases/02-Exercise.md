# Exercice sur les animations

Il s'agit de créer la même interface que l'exercice précédent, plusieurs boutons qui agissent sur la propriété
transform d'une target. 

Sauf que maintenant lorsqu'un bouton sera actif, l'animation se déroulera de manière infinie.

```css
@keyframes example {
    from {transform: translateY(0px);}
    to {transform: translateY(100px);}
}
```

### Pour aller plus loin

Autre contrainte, les différentes animations doivent s'additionner au clik sur les boutons (matrice et génération de keyframe en JS).