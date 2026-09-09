# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Qué es este repositorio

Sitio web de apuntes del módulo **PMDM** (Programación Multimedia y Dispositivos Móviles) del ciclo DAM. Es un sitio **Jekyll** publicado con **GitHub Pages**, escrito íntegramente en español. El contenido son apuntes, ejercicios y recursos de Android/Kotlin organizados por unidad didáctica. No hay código de aplicación: todo es Markdown + Sass.

## Comandos

No hay `Gemfile` en el repo; GitHub Pages compila el sitio automáticamente al hacer push a `main`. Para previsualizar en local hace falta Ruby + Jekyll:

```bash
# instalación local (una vez)
gem install jekyll bundler

# servir con recarga en http://localhost:4000
jekyll serve --livereload

# build a _site/ sin servidor
jekyll build
```

`_site/`, `.jekyll-cache/`, `.sass-cache/`, `.bundle/` y `vendor/` están en `.gitignore` y no deben commitearse.

## Arquitectura

- **`_config.yml`** — configuración Jekyll. Tema `minima`, título del sitio. Cambiar aquí `theme` o añadir `plugins` afecta a todo el sitio.
- **Páginas de contenido** — un `unidadN/index.md` por unidad. Cada archivo lleva front matter YAML (`layout: page`, `title: ...`) y el cuerpo en Markdown. La portada es `index.md` en la raíz con `layout: home`.
- **Navegación** — el índice de unidades se mantiene **a mano** en `index.md` (raíz). Al añadir una unidad nueva hay que enlazarla ahí; no se genera sola.
- **Estilos** — `assets/main.scss` importa `minima` y luego sobrescribe con la paleta PMDM. Es el único hoja de estilos del sitio (minima 2.5 de GitHub Pages lo compila a `assets/main.css`). Las dos primeras líneas `---\n---` (front matter vacío) son obligatorias para que Jekyll procese el Sass.

## Convenciones de contenido

- **Bloques de ejercicio**: envolver en `<div class="ejercicio" markdown="1"> ... </div>`. El `::before` del CSS ya añade la etiqueta "Ejercicio"; dentro se usa `**Ejercicio N.M**` en negrita para numerar. `markdown="1"` es necesario para que Jekyll interprete Markdown dentro del `div`.
- **Botones**: enlaces con `{: .btn}` al final, p. ej. `[Volver al inicio](../){: .btn}`.
- **Enlaces entre páginas**: relativos con barra final (`unidad1/`, `../`), no rutas absolutas.
- **Paleta** (definida como variables Sass, no reutilizar literales hex): primario `#0F6E56` (verde teal, cabeceras), acento `#534AB7` (violeta, enlaces/botones), aviso `#BA7517` (ámbar, ejercicios), fondo `#F1EFE8` (crema).
- Los ejemplos de código son Kotlin/Android en bloques ` ```kotlin `.
