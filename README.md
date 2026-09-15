# FindAGem

Sitio web de un taller dedicado a la restauración de guitarras y a la venta de piezas
vintage para instrumentos con historia. El proyecto es un portafolio de cinco páginas
maquetado con HTML5, CSS3 y Bootstrap 5, adaptado a mobile y desktop.

## Sitio desplegado

**https://fabriziobalbi27-hash.github.io/trabajo-pagina-web/**

Publicado con GitHub Pages desde la rama `main`.

## Tecnologías

- HTML5 semántico
- SCSS con arquitectura de partials (variables, mixins y nesting)
- CSS3 (Flexbox, Grid, media queries, variables de Bootstrap personalizadas)
- Bootstrap 5.3.8 vía CDN (CSS y JavaScript)
- AOS 2.3.1 vía CDN para las animaciones al hacer scroll
- Tipografía Inter (Google Fonts)

## Páginas

| Página | Contenido |
|---|---|
| `index.html` | Presentación, carousel de guitarras a pedido, productos destacados, servicios y testimonios |
| `pages/servicios.html` | Servicios disponibles y accordion con el proceso de trabajo |
| `pages/proyectos.html` | Restauración de una guitarra vintage, etapas y galería en modal |
| `pages/sobre-mi.html` | La idea detrás del proyecto |
| `pages/contacto.html` | Formulario de consulta y canales de atención |

## Componentes de Bootstrap utilizados

- Navbar responsive (`navbar-expand-lg`) en las cinco páginas
- Carousel con transición fade y captions
- Modal para la galería de proyectos
- Accordion para el proceso de trabajo
- Sistema de grillas y cards
- Formulario con floating labels

Todos los componentes están personalizados con CSS propio para respetar la paleta
del proyecto, sobrescribiendo las variables `--bs-*` donde hizo falta.

## Paleta de colores

| Rol | Color |
|---|---|
| Primario | `#416788` |
| Secundario | `#F0EDE2` |
| Acento | `#FFDAB9` |

## Estilos

Los estilos se escriben en SCSS dentro de `scss/`. El único punto de entrada es
`main.scss`, que solo contiene directivas `@use` hacia los partials:

```
scss/
├── main.scss
├── utilities/
│   ├── _variables.scss   paleta, tipografía, bordes, sombras y breakpoints
│   └── _mixins.scss      media queries y elevación de las tarjetas
├── base/
│   ├── _tipografia.scss  fuente y jerarquía de títulos
│   ├── _base.scss        reset, body y accesibilidad
│   └── _animaciones.scss keyframes de entrada
├── layout/
│   ├── _header.scss
│   ├── _nav.scss
│   ├── _contenido.scss   grillas y secciones
│   └── _footer.scss
└── components/
    ├── _buttons.scss
    ├── _cards.scss
    ├── _imagenes.scss
    ├── _listas.scss
    ├── _proyecto.scss
    ├── _galeria.scss
    ├── _modal.scss
    └── _accordion.scss
```

Para compilar hace falta instalar las dependencias una vez con `npm install`:

```
npm run sass     compila scss/main.scss a styles/styles.css
npm run watch    recompila al guardar
```

`styles/styles.css` es el resultado de la compilación y no se edita a mano.

## Animaciones

La portada de cada página entra con un `@keyframes` propio, aplicado con un mixin
que recibe la duración y el retraso para escalonar el título y el texto. El resto
de las secciones aparecen al hacer scroll con AOS (`data-aos="fade-up"`). Los
estados de hover y focus usan `transition`.

## Estructura del proyecto

```
trabajo-pagina-web/
├── index.html
├── pages/
│   ├── servicios.html
│   ├── proyectos.html
│   ├── sobre-mi.html
│   └── contacto.html
├── scss/
├── styles/
│   └── styles.css
├── img/
│   └── galeria/
└── README.md
```

Todas las rutas a imágenes y hojas de estilo son relativas, de modo que el sitio
funciona igual en local y en GitHub Pages.

## Autor

Fabrizio Balbi — Desarrollo Web, Coderhouse.
