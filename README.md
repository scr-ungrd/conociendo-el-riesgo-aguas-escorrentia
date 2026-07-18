# Conociendo el riesgo por aguas de escorrentía

[![Quarto Build](https://img.shields.io/badge/built%20with-Quarto-blue?style=flat-square)](https://quarto.org)
[![UNGRD](https://img.shields.io/badge/entidad-UNGRD-navy?style=flat-square)](https://www.gestiondelriesgo.gov.co)

Este repositorio contiene el código fuente y los recursos para la compilación del libro digital interactivo **"Conociendo el riesgo por aguas de escorrentía"**. Este recurso educativo e institucional ha sido desarrollado por la **Unidad Nacional para la Gestión del Riesgo de Desastres (UNGRD)** de Colombia para capacitar y guiar a la población rural y urbana, líderes comunitarios y autoridades locales en el manejo adecuado de las aguas de escorrentía superficial y en la prevención de riesgos asociados.

---

## 📖 Contenido del Libro

El libro está estructurado en capítulos organizados de manera secuencial para guiar al lector desde los fundamentos teóricos hasta las soluciones prácticas:

*   **Inicio (`index.qmd`)**: Página de bienvenida con portada flotante interactiva y una cuadrícula de accesos directos a los capítulos principales.
*   **Presentación (`01-presentacion.qmd`)**: Propósito de la cartilla, justificación y público objetivo.
*   **Capítulo 2: Aguas de escorrentía (`02-aguas-de-escorrentia.qmd`)**: Conceptos clave del ciclo del agua, definición de escorrentía (superficial, hipodérmica y subterránea) y sus ventajas/desventajas.
*   **Capítulo 3: Riesgos asociados y consecuencias (`03-riesgos-asociados-y-consecuencias.qmd`)**: Fenómenos asociados (inundaciones, movimientos en masa, avenidas torrenciales) y elementos expuestos en el territorio colombiano.
*   **Capítulo 4: Factores que agravan el problema (`04-factores-que-agravan-el-problema.qmd`)**: Impacto de actividades antrópicas, cambio de uso del suelo, deforestación, expansión urbana e infraestructura de drenaje deficiente.
*   **Capítulo 5: Medidas de mitigación y buenas prácticas (`05-medidas-de-mitigacion-y-buenas-practicas.qmd`)**: Acciones preventivas para comunidades y autoridades, incluyendo Sistemas Urbanos de Drenaje Sostenible (SUDS), zanjas de infiltración y reforestación.
*   **Referencias bibliográficas (`06-referencias-bibliograficas.qmd`)**: Repositorio de fuentes, normativas e insumos técnicos consultados.

---

## 🛠️ Estructura del Repositorio

El proyecto sigue la estructura estándar de un libro digital de **Quarto**:

```text
├── _quarto.yml             # Archivo de configuración global de Quarto (metadatos, orden de capítulos, estilos)
├── index.qmd               # Página de inicio / portada digital
├── 01-presentacion.qmd     # Sección introductoria
├── 02-aguas-de-escorrentia.qmd
├── 03-riesgos-asociados-y-consecuencias.qmd
├── 04-factores-que-agravan-el-problema.qmd
├── 05-medidas-de-mitigacion-y-buenas-practicas.qmd
├── 06-referencias-bibliograficas.qmd
├── custom.css              # Hoja de estilos personalizados (identidad visual UNGRD)
├── caption-bold.html       # Fragmento de encabezado para formatear pies de imagen en negrita
├── vancouver-apa-hybrid.csl# Estilo de citación bibliográfica
├── media/                  # Carpeta de imágenes, diagramas y recursos gráficos del libro
│   ├── CUB_AGUAS ESCORRENTIA-1.png # Imagen de portada
│   └── [capitulo]/         # Subcarpetas con las imágenes de cada capítulo
└── README.md               # Este archivo de documentación
```

---

## 🎨 Identidad Visual y Diseño (UX/UI)

El diseño de la interfaz interactiva web ha sido personalizado siguiendo la línea institucional de la serie de publicaciones de la UNGRD:

*   **Paleta de Colores**:
    *   **Azul Oscuro (`#223764`)**: Color principal utilizado en barras de navegación, botones primarios y cabeceras de tarjetas.
    *   **Amarillo (`#FAC718`)**: Color secundario para efectos de realce (hover), bordes destacados y elementos interactivos activos.
*   **Componentes Clave**:
    *   `{.ungrd-cover-float}`: Permite que la portada del libro flote de forma fluida a la derecha del texto en pantallas de escritorio.
    *   `{.ungrd-cards-grid}` y `{.ungrd-card}`: Sistema de tarjetas interactivas en la página de inicio con animación de elevación y cambio de fondo al hacer hover.
    *   `{.ungrd-btn}`: Botones con estilo premium y transiciones suaves para la navegación.
    *   **Líneas Divisiorias**: Los títulos principales (`h1`, `.title` y `h2`) incorporan una sutil línea divisoria inferior (`border-bottom`) de color `#ecf0f1` para segmentar adecuadamente el contenido.

---

## 🚀 Instrucciones de Construcción y Visualización

Este libro está construido sobre **Quarto CLI**.

### Requisitos Previos

Asegúrate de tener instalado Quarto (versión 1.5 o superior) en tu sistema:

```bash
# Comprobar la instalación de Quarto
quarto --version
```

*Si no lo tienes instalado, puedes descargarlo de la [página oficial de Quarto](https://quarto.org/docs/get-started/).*

### Comandos de Compilación

1.  **Vista Previa en Tiempo Real (Entorno de Desarrollo)**:
    Este comando levanta un servidor local y actualiza la página automáticamente cada vez que realizas un cambio en los archivos `.qmd` o `.css`:
    ```bash
    quarto preview
    ```

2.  **Compilar la Versión Web (HTML)**:
    Genera el sitio web estático optimizado en el directorio `_book/`:
    ```bash
    quarto render
    ```

3.  **Compilar a Formato PDF**:
    Si tienes configurado un motor LaTeX (como TinyTeX), puedes compilar el libro a formato PDF:
    ```bash
    quarto render --to pdf
    ```

---

## 🌐 Despliegue

La compilación HTML en el directorio `_book/` es ideal para hospedarse en servicios de páginas estáticas como **GitHub Pages**. La configuración del `site-url` está optimizada para publicarse bajo:

`https://scr-ungrd.github.io/conociendo-el-riesgo-aguas-escorrentia/`

---

## 🏢 Créditos e Institución

**Unidad Nacional para la Gestión del Riesgo de Desastres (UNGRD)**  
*Subdirección de Conocimiento del Riesgo (SCR)*  
República de Colombia.
