### SVG Animations

Comment est construit un SVG ? C'est un arbre exactement comme une page HTML


Ici une ligne
```svg
<svg width="347px" height="3px" viewBox="0 0 347 3" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    <path d="M1.5,1.5 L345.5,1.5" id="Line" stroke="#979797" stroke-width="3"></path>
</svg>
```

Un rectangle
```svg
<svg width="198px" height="160px" viewBox="0 0 198 160" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    <rect stroke="#979797" stroke-width="1" x="4.5" y="2.5" width="189" height="151"></rect>
</svg>
```

Un text sur un rond vert, sur un rectangle rouge
```svg
<svg version="1.1" baseProfile="full" xmlns="http://www.w3.org/2000/svg">
  <rect width="100%" height="100%" fill="red"/>

  <circle cx="150" cy="100" r="80" fill="green"/>

  <text x="150" y="125" font-size="60" text-anchor="middle" fill="white">SVG</text>
</svg>
```

Un rectangle avec une ombre portée
```svg
<svg width="198px" height="160px" viewBox="0 0 198 160" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    <defs>
        <rect id="path-1" x="4" y="2" width="190" height="152"></rect>
        <filter x="-3.7%" y="-3.3%" width="107.4%" height="109.2%" filterUnits="objectBoundingBox" id="filter-2">
            <feOffset dx="0" dy="2" in="SourceAlpha" result="shadowOffsetOuter1"></feOffset>
            <feGaussianBlur stdDeviation="2" in="shadowOffsetOuter1" result="shadowBlurOuter1"></feGaussianBlur>
            <feComposite in="shadowBlurOuter1" in2="SourceAlpha" operator="out" result="shadowBlurOuter1"></feComposite>
            <feColorMatrix values="0 0 0 0 0   0 0 0 0 0   0 0 0 0 0  0 0 0 0.5 0" type="matrix" in="shadowBlurOuter1"></feColorMatrix>
        </filter>
    </defs>
    <g id="Page-1" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
        <g id="Rectangle">
            <use fill="black" fill-opacity="1" filter="url(#filter-2)" xlink:href="#path-1"></use>
            <use fill="#B24040" fill-rule="evenodd" xlink:href="#path-1"></use>
            <rect stroke="#979797" stroke-width="1" x="4.5" y="2.5" width="189" height="151"></rect>
        </g>
    </g>
</svg>
```


#### Création d'un svg

Dessinez une forme à base de ligne dans votre outil vectoriel préféré (Illustrator, Sketch...)

Exportez au format `.svg`

Ouvrez le fichier svg dans un éditeur de texte et copier le contenu.

Intégrer votre svg dans une page web.

Tester l'affichage.

#### Première animation

Dans votre .svg directement, ajoutez une class `animated-svg` sur le path qui possède un `stroke`

```svg
<svg ...>
  <path class="animated-svg" stroke="#000000" ... >
</svg>
```

Maintenant créez une animation sur l'objet path

```css
.animated-svg {
  stroke-dasharray: 100;
  animation: dash 5s linear;
}

@keyframes dash {
  to {
    stroke-dashoffset: 1000;
  }
}
```

#### Simulation de génération SVG

Nouvelle animation, appliquez les propriétés suivantes :

```css
.animated-svg {
  stroke-dasharray: 1000;
  stroke-dashoffset: 1000;
  animation: dash 5s linear alternate infinite;
}

@keyframes dash {
  from {
    stroke-dashoffset: 1000;
  }
  to {
    stroke-dashoffset: 0;
  }
}
```

Votre animation devrait simuler l'apparition d'un svg en dessinant la ligne progressivement.

La propriété `alternate` permet de lire l'animation dans un sens, puis dans l'autre.

Exemple inspiré de [cet article](https://css-tricks.com/svg-line-animation-works/)

#### Conclusion

Vous avez vu qu'on peut appliquer des class sur les éléments d'un svg, comme en HTML. On peut ainsi animer chaque
partie de manière indépendante.

Des [exemples](https://www.hongkiat.com/blog/svg-animations/) à voir absolument.


