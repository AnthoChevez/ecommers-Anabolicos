# Titan Suplementos Repository Guidelines

## Build, Test, and Lint

This repository is a static HTML/CSS site deployed as the `ecommerce` web application under Apache Tomcat. There is no package manifest, build script, automated test suite, or configured linter.

- To preview the site through Tomcat, place the repository at `webapps\ecommerce` and open `http://localhost:8080/ecommerce/` (or the configured Tomcat port).
- For a focused manual check, open the page being changed directly, then verify its navigation links, local images, responsive layout, and browser console for broken resource URLs.
- When validating a CSS-only change, check all four pages because they share `css/estilos.css`.

## Architecture

- `index.html`, `productos.html`, `servicios.html`, and `contacto.html` are independent page entry points for the same Titan Suplementos site.
- Every page uses the shared stylesheet at `css/estilos.css` and relative paths to assets in `iconos/` and `imagenes/`; preserve this structure so the site works when served from the Tomcat context path.
- The common page shell is a dark header, navigation bar, two-column `.content` area (`main` plus `aside`), and social-link footer. The home page additionally contains the mission content and an embedded Google Maps iframe.
- Product content is represented directly in `productos.html` as repeated `article` blocks. The services and contact pages currently present construction placeholders rather than dynamic functionality.

## Conventions

- Keep page language and user-facing copy in Spanish, with `lang="es"` and UTF-8 metadata retained.
- Use the existing shared class and ID vocabulary (`.destacado`, `#favorito`, `.content`, `.imagen-mision`, `.precio`) before adding new selectors.
- Keep navigation reciprocal: each page should link to the other site sections, and the logo/title should return to `index.html`.
- Reference local resources with paths relative to the page, using the existing lowercase asset directories and filenames. Keep descriptive `alt` text for images.
- Preserve the responsive breakpoint in `css/estilos.css`: desktop uses the `main`/`aside` row, while screens at or below 600px stack the content and make navigation links full width.
- Match the existing visual system: dark `#222`/`#333` header and navigation, orange `#f39c12` highlight text, white content cards, rounded corners, and the shared footer/social-link treatment.
- Keep repeated header, aside, and footer markup synchronized across pages when changing shared site content.
