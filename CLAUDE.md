# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Qué es esto

Libro digital Quarto (`project: type: book`) en español: **"Conociendo el riesgo por aguas de escorrentía"**, producido por la Subdirección de Conocimiento del Riesgo (SCR) de la UNGRD. Se publica como sitio HTML en GitHub Pages (`https://scr-ungrd.github.io/conociendo-el-riesgo-aguas-escorrentia/`) y también se ofrece como descarga PDF (`downloads: [pdf]` en `_quarto.yml`).

## Comandos

```bash
quarto preview          # servidor local con recarga en vivo al editar .qmd/.css
quarto render           # compila el sitio HTML estático a _book/
quarto render --to pdf  # compila la versión PDF (requiere motor LaTeX, p.ej. TinyTeX)
```

No hay build de JS/CSS ni tests: es contenido Quarto puro. El despliegue a GitHub Pages es automático vía `.github/workflows/publish.yml` en cada push a `main` (ejecuta `quarto render` y publica `_book/`).

## Estructura y orden de capítulos

El orden y la lista de capítulos viven en `_quarto.yml` (`book.chapters`) y deben coincidir con los archivos `NN-titulo.qmd` en la raíz:

```
index.qmd → 01-presentacion.qmd → 02-aguas-de-escorrentia.qmd →
03-riesgos-asociados-y-consecuencias.qmd → 04-factores-que-agravan-el-problema.qmd →
05-medidas-de-mitigacion-y-buenas-practicas.qmd → 06-referencias-bibliograficas.qmd
```

Al agregar/renombrar un capítulo hay que actualizar `_quarto.yml` y, si aplica, las tarjetas de navegación en `index.qmd`.

Cada capítulo tiene su propia subcarpeta de imágenes en `media/<nombre-del-capitulo>/`, con archivos nombrados `img_<hash>.png|jpeg` (convención de pegado automático, no descriptiva). Al referenciar una imagen desde el `.qmd`, usar rutas relativas a `media/`.

## Bibliografía: NO usa el sistema de citas de Quarto

Aunque `_quarto.yml` define `csl: vancouver-apa-hybrid.csl` y `link-citations: true`, **no existe archivo `.bib`** y `06-referencias-bibliograficas.qmd` es una lista de referencias escrita a mano en texto plano (formato APA/Vancouver híbrido), no citas `@clave` enlazadas a un `.bib`. Nuevas referencias deben añadirse manualmente en ese archivo siguiendo el mismo formato (Autor, Año, *Título en cursiva*, fuente).

## Identidad visual UNGRD (custom.css)

Los estilos institucionales están centralizados en `custom.css` y se aplican con clases sobre divs de Pandoc (`:::`), no inline. Las más usadas:

- `.ungrd-cover-float` — portada flotando a la derecha del texto (usada en `index.qmd`).
- `.ungrd-cards-grid` / `.ungrd-card` / `.ungrd-card-header` / `.ungrd-card-body` / `.ungrd-card-img` — tarjetas de navegación a capítulos en la portada, con hover.
- `.ungrd-btn` — botones de navegación con transición.
- `.clearfix` — para limpiar el flotado tras `.ungrd-cover-float`.
- Paleta: azul oscuro `#223764` (principal) y amarillo `#FAC718` (realce/hover).

`caption-bold.html` (inyectado vía `include-in-header`) pone en negrita los pies de figura/tabla; `crossref.fig-prefix`/`tbl-prefix` están en español ("Figura"/"Tabla").

## Convenciones de contenido

- Idioma: español (`lang: es`), tono institucional/educativo dirigido a población rural/urbana, líderes comunitarios y autoridades locales.
- Encabezados de capítulo usan `{.unnumbered}` (sin numeración automática; `number-sections: false`).
- Los metadatos de citación académica (`citation_book_title`, `citation_publication_date`, etc.) están hardcodeados como `<meta>` tags en `_quarto.yml` — si cambia la fecha de publicación o el título, actualizarlos ahí también.
