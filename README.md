# ValoHub

Sitio web estático de 6 páginas sobre **Valorant**: agentes, mapas, estrategias, esports y notas de parche. Proyecto final del curso de CSS de Coderhouse (Diplomatura Full Stack).

🔗 **Sitio online:** https://valohub-marcos.netlify.app  
📁 **Repositorio:** https://github.com/Noka11/Nue-ezMarcosPre-entregacss4/tree/feature/preentrega-6-sass  

> Proyecto educativo sin fines de lucro. No está afiliado ni respaldado por Riot Games. Valorant es marca registrada de Riot Games, Inc.

---

## Páginas

| Página | Archivo | Contenido |
|---|---|---|
| Inicio | `index.html` | Carousel principal y presentación del portal |
| Agentes | `pages/agentes.html` | Roles y habilidades de los agentes |
| Mapas | `pages/mapas.html` | Pool de mapas, callouts y rotaciones |
| Estrategias | `pages/estrategias.html` | Comunicación y control de mapa |
| Esports | `pages/esports.html` | Circuito competitivo VCT |
| Parches | `pages/parches.html` | Notas de parche y balance |

Cada página tiene su propio `<title>`, `meta description` y `meta keywords`, y todas las imágenes llevan atributo `alt`.

## Tecnologías

- **HTML5** semántico e indentado.
- **Sass (SCSS)** con arquitectura de partials, compilado a CSS.
- **Bootstrap 5.3** (grilla, navbar, componentes), personalizado desde SCSS.
- **AOS** (Animate On Scroll) como librería de animación.
- **Google Fonts** (Anta).

## Estructura del proyecto

```
├── index.html
├── pages/
│   ├── agentes.html
│   ├── mapas.html
│   ├── estrategias.html
│   ├── esports.html
│   └── parches.html
├── assets/
│   └── img/              # imágenes, logo y favicon
├── scss/
│   ├── main.scss         # solo contiene @use de los partials
│   ├── base/             # reset, tipografía y estilos base
│   ├── layout/           # header, nav y footer
│   ├── components/       # botones, badges, cards y carousel
│   ├── pages/            # estilos propios de cada página
│   └── utilities/        # variables, mixins, placeholders y animaciones
└── styles/
    └── style.css         # CSS compilado
```

## SCSS: qué se usa y dónde

- **Variables:** colores, tipografías, espaciados, tamaños y puntos de quiebre (`$bp-sm`, `$bp-md`, `$bp-lg`, `$bp-xl`) en `utilities/_variables.scss`.
- **Anidamiento:** selectores anidados en cards, carousel, botones y páginas.
- **Mixins con parámetros** en `utilities/_mixins.scss`:
  - `desde($ancho)`: media query mobile-first con `@content`.
  - `flex-columna($separacion)`: columna flex con separación configurable.
  - `boton-base`, `badge`, `transicion-elevacion`.
- **`@extend` con placeholder:** `%tarjeta-interactiva` (en `utilities/_placeholders.scss`) comparte el efecto de elevación entre `.card-valohub` y `.card-tactical`.
- **Partials:** cada sección en su archivo, importados con `@use` desde `main.scss`.
- **Bootstrap personalizado:** navbar y componentes estilizados desde SCSS.

## Diseño responsive

Enfoque **mobile-first**, probado en celular (320 y 375 px), tablet (768 px) y escritorio (1280 px), sin scroll horizontal.

- Grilla de Bootstrap (`col-12`, `col-md-6`, `col-lg-4`, etc.).
- Media queries propias mediante el mixin `desde()` en el carousel y la sección de mapas.
- Navbar colapsable con menú hamburguesa en pantallas chicas.
- Imágenes con `object-fit: cover` y alturas controladas desde variables.

## Animaciones

- **Nativas (CSS):** transiciones de elevación en cards y botones, zoom de imagen al pasar el mouse y `@keyframes` en `utilities/_animaciones.scss`.
- **Librería:** [AOS](https://michalsnik.github.io/aos/), con entrada de elementos al hacer scroll. En pantallas menores a 992 px se desactiva para evitar desbordes laterales; también se respeta `prefers-reduced-motion`.

## Cómo correr el proyecto

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/TU-USUARIO/TU-REPO.git
   cd TU-REPO
   ```
2. Abrir `index.html` en el navegador (o usar la extensión Live Server de VS Code).

### Compilar el SCSS (opcional, solo si se modifican estilos)

Requiere [Sass](https://sass-lang.com/install) instalado:

```bash
npm install -g sass
sass --watch scss/main.scss:styles/style.css --no-source-map
```

## Deploy

El sitio está publicado en **Netlify**, conectado al repositorio de GitHub (rama `main`).
Todas las rutas son relativas y los nombres de archivos están en minúscula, porque el servidor distingue mayúsculas y minúsculas.

## Autor

**Marcos Núñez** — Estudiante de la Diplomatura Full Stack, Coderhouse.