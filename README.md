# Fuentes de Agua — landing page

Landing bilingüe (ES/EN) para la app de Android **Fuentes de Agua**, optimizada para SEO,
lista para publicarse en GitHub Pages con dominio propio `fuentes-agua.devcodelight.com`.

## Estructura

```
/
├── index.html          → versión en español (raíz, idioma por defecto)
├── en/
│   └── index.html      → versión en inglés
├── assets/
│   ├── style.css
│   └── script.js
├── sitemap.xml
├── robots.txt
└── CNAME               → dominio personalizado para GitHub Pages
```

## Publicar en GitHub Pages

1. Crea un repositorio nuevo (público) en GitHub, p. ej. `fuentes-agua-landing`.
2. Sube todo el contenido de esta carpeta a la raíz del repo (rama `main`).
   El archivo `CNAME` ya incluye `fuentes-agua.devcodelight.com`, no lo borres.
3. En GitHub → **Settings → Pages**:
   - Source: `Deploy from a branch`
   - Branch: `main` / carpeta `/ (root)`
   - Guarda. GitHub generará una URL tipo `usuario.github.io/fuentes-agua-landing`.
4. En tu proveedor de DNS del dominio `devcodelight.com`, añade un registro **CNAME**:
   - Host: `fuentes-agua`
   - Valor: `usuario.github.io` (tu usuario/organización de GitHub, sin `https://`)
5. Vuelve a **Settings → Pages** en GitHub y en "Custom domain" confirma
   `fuentes-agua.devcodelight.com`, luego activa **Enforce HTTPS** (puede tardar
   unos minutos en aparecer disponible tras la propagación DNS).

## Después de publicar

- Verifica la propiedad en **Google Search Console** para ambas versiones
  (o una propiedad de dominio) y envía `sitemap.xml`.
- Revisa que las etiquetas `hreflang` resuelvan bien una vez el dominio esté activo
  (Search Console → Legibilidad internacional, o cualquier validador de hreflang).
- Las capturas de pantalla e icono se sirven directamente desde el CDN de Google Play
  (`play-lh.googleusercontent.com`). Si prefieres no depender de esa URL a largo plazo,
  descarga esos assets y sírvelos desde `/assets/` actualizando las rutas en ambos HTML.
- El texto es 100% editable: los datos de la app (características, capturas, FAQ)
  están tomados de la ficha actual de Google Play y pueden actualizarse cuando cambie
  la app.

## Notas técnicas

- Sin frameworks ni build step: HTML + CSS + un pequeño JS, funciona tal cual en
  GitHub Pages.
- Tipografías: Fraunces (titulares) + Archivo (cuerpo), vía Google Fonts.
- Diseño: líneas de contorno tipo mapa topográfico, marcadores de ruta numerados
  solo en la sección "Cómo funciona" (es una secuencia real de 3 pasos).
- Accesible: foco visible, `prefers-reduced-motion` respetado, skip-link, alt text
  descriptivo en todas las imágenes.
