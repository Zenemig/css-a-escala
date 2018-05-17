title: Como Escalar CSS y No Morir en el Intento
author:
  name: Matías Giménez
  twitter: zenemig
  email: hola@zenemig.net
  url: http://zenemig.net
output: index.html
theme: juanbrujo/cleaver-beerjs

--

# Como Escalar CSS
## Sin Morir en el Intento

--

# ¿Qué buscamos en nuestro CSS?

# **MANTENIBLE** <br> **ESCALABLE** <br> **DRY**

--

# Mantenible

## BEM + Namespacing

--

# ¿Qué es BEM?

> BEM es lo más feo que hay

*Jorge Epuñan y varias personas más*

--

# block__element--modifier

--

```scss
.o-card {
  box-shadow: 0 1px 2px 0 rgba(0,0,0,0.10);
  background-color: white;
  &--flat {
    box-shadow: none;
    background-color: lightgrey;
  }
}
.o-card__image {
  margin-bottom: 15px;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
  width: 100%;
  height: 150px;
}
.o-card__title {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: bold;
}
.o-card__text {
  margin-bottom: 15px;
  font-size: 16px;
}

```

--

```html
<div class="o-card">
  <figure class="o-card__image">
    <img src="https://media.giphy.com/media/wmKa73ET9IoMM/giphy.gif">
  </figure>

  <h3 class="o-card__title">Título de la Carta</h3>

  <p class="o-card__text">Texto de la carta</p>
</div>
```

```html
<div class="o-card o-card--flat">
  <figure class="o-card__image">
    <img src="https://media.giphy.com/media/wmKa73ET9IoMM/giphy.gif">
  </figure>

  <h3 class="o-card__title">Título de la Carta</h3>

  <p class="o-card__text">Texto de la carta</p>
</div>
```

--

# Namespacing

## `o-` para objetos <br> `js-` para clases que se usarán en el Javascript <br> `u-` para clases utilitarias

--

# Escalable

## Atomic Design + Sass

--

# ¿Qué es Atomic Design?

<div style="margin: 0 auto; width: 1200px;">
  ![Detalle de Atomic Design](http://bradfrost.com/wp-content/uploads/2013/06/atomic-design.png)
</div>

--

# ¿Qué es Sass?

<div style="margin: 0 auto; width: 600px;">
  ![Sass Logo](https://sass-lang.com/assets/img/logos/logo-b6e1ef6e.svg)
</div>

--

# Arquitectura CSS

```
- scss/
    |- lib/
    |- helpers/
    |- variables/
    |- base/
    |- layouts/
    |- objects/
    |- components/
    |- styles.scss
    |- _utilities.scss
```

--

# styles.scss

```
[...]

// Variables
@import 'variables/colors';
@import 'variables/typography';
@import 'variables/breakpoints';

[...]

// Objects
@import 'objects/buttons';
@import 'objects/input';
@import 'objects/typography';

[...]

// Shame
@import 'shame';
```

--

# DRY

## Ya expliqué como modularizar el CSS así que no me repetiré

![I see what you did there](https://media.giphy.com/media/5gw0VWGbgNm8w/giphy.gif)

--

# Referencias

- [Brad Frost - Atomic Design](http://bradfrost.com/blog/post/atomic-web-design/)
- [BEM](http://getbem.com/)
- [Sass](http://sass-lang.com/)
- Zell Liew - Writing Modular CSS (inglés)
  - [Parte 1](https://zellwk.com/blog/css-architecture-1/)
  - [Parte 2](https://zellwk.com/blog/css-architecture-2/)
  - [Parte 3](https://zellwk.com/blog/css-architecture-3/)
