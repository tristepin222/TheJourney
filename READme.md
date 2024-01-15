# Projet AWA1

Site d'agence de bateaux fait en HTML, CSS et JS

des bateau apparaissent de droite à gauche, à chaque clique sur un bateau, un menu apparaitra (page de login, page des images de bateau etc)

plusieurs elements ont des animations, tel que les nuages et bateaux


## Points techniques

### Parallax

Fait en css, Utilise Transform

-webkit-transform vs transform

    .parallax-child {
      position: absolute;
      top: 50%;
      left: 50%;
      -webkit-transform-origin: 50% 50% 0;
      transform-origin: 50% 50% 0;
      -webkit-transform: translateX(-50%) translateY(-50%) rotate(90deg);
      transform: translateX(-50%) translateY(-50%) rotate(90deg);
      z-index: 1;
    }

Avec Translation en Z, et scale

    .parallax-background {
      position: absolute;
      top: 50%;
      left: 50%;

      -webkit-transform: translateX(-60%) translateY(-140%) translateZ(-8px) scale(4.   5) rotate(90deg);
      transform: translateX(-60%) translateY(-140%) translateZ(-14px) scale(4.5)    rotate(90deg);
      z-index: -2;
    }

### Limitation du scroll

évite que l'utilisateur scroll trop loin

    const maxscroll = 19000;
      const scroll = document.querySelector("#scroll");
      scroll.addEventListener("scroll", event => {
        if (scroll.scrollTop > maxscroll) {
          scroll.scrollTop = maxscroll;
        }
      }, { passive: true });

### Timeline

Créée une animation, en utilisant des SVG

    timeLine.add({
      targets: '#boat',
      keyframes: [
      {strokeDashoffset: [anime.setDashoffset, 0]},
      {strokeDashoffset: [0, anime.setDashoffset]}
      ],
      begin: function() {
        document.querySelector('.loader').style.visibility = 'visible';
      },
      easing: 'linear',
      duration: 1500,
      delay: function(el, i) { return i * 250 },
    }).add({
      targets: '#wave',
      keyframes: [
      {strokeDashoffset: [anime.setDashoffset, 0]},
      {strokeDashoffset: [0, anime.setDashoffset]}
      ],
      easing: 'linear',
      duration: 1500,
      delay: function(el, i) { return i * 250 },
      begin: function() {
        document.querySelector('#wave').style.visibility = 'visible';
      },
    }).add({
      targets: '#wave-2',
      keyframes: [
      {strokeDashoffset: [anime.setDashoffset, 0]},
      {strokeDashoffset: [0, anime.setDashoffset]}
      ],
      easing: 'linear',
      duration: 1500,
      delay: function(el, i) { return i * 250 },
      begin: function() {
        document.querySelector('#wave-2').style.visibility = 'visible';
      },
    }).add({
      targets: '#wave-3',
      keyframes: [
      {strokeDashoffset: [anime.setDashoffset, 0]},
      {strokeDashoffset: [0, anime.setDashoffset]}
      ],
      easing: 'linear',
      duration: 1500,
      delay: function(el, i) { return i * 250 },
      begin: function() {
        document.querySelector('#wave-3').style.visibility = 'visible';
      },
    }).add({
      targets: '#anchor',
      keyframes: [
      {strokeDashoffset: [anime.setDashoffset, 0]},
      {strokeDashoffset: [0, anime.setDashoffset]}
      ],
      easing: 'linear',
      duration: 1500,
      delay: function(el, i) { return i * 250 },
      begin: function() {
        document.querySelector('#anchor').style.visibility = 'visible';
      },
    });


## Librairies 

- anime.js
- particles.js
- effect parallax : https://dev.to/ingosteinke/pure-css-parallax-perspective-beyond-landscape-images-24g2

## sources des images

- Google