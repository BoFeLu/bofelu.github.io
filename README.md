# Sitio de Alberto “BoFeLu” — ASIR · DevOps

Web mixta (portafolio + blog técnico) publicada con **GitHub Pages**.

## Estructura
- `index.html` — portada
- `about.html` — bio/CV
- `blog/` — tareas y artículos
- `assets/css/custom.css` — ajustes de estilo sobre Tailwind (CDN)

## Publicación (paso a paso)
1. Crea un repositorio llamado `USUARIO.github.io` (sustituye USUARIO por tu user de GitHub).
2. Sube todos los archivos de esta carpeta al repo (raíz).
3. Entra en **Settings → Pages** y verifica que el sitio está activo.
4. Tu web estará en: `https://USUARIO.github.io/`.

## Tailwind por CDN
Usado para simplicidad en GitHub Pages. Si más adelante quieres build con Node (purga, minificado), migramos a flujo con `postcss`.
