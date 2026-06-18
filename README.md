# CODEX — Sitio web

Landing de una sola página para **CODEX — Electrónica y Codificación Automotriz** (Santa Cruz de la Sierra, Bolivia).

Sitio **estático** (HTML/CSS/JS en un solo archivo, sin paso de build). Tema oscuro, optimizado para móvil, con cotizador por WhatsApp, diagnóstico por síntoma, mapa de ubicación e imagen de previsualización al compartir el link.

## Contenido de la carpeta

```
index.html            → toda la página (HTML + CSS + JS)
logo-codex.png        → logo CODEX (blanco, para fondo oscuro)
favicon.png           → ícono de pestaña (isotipo CX)
apple-touch-icon.png  → ícono para pantalla de inicio (móvil)
og-codex-cx.png       → imagen al compartir el link (1200×1200, isotipo CX)
vercel.json           → cabeceras de seguridad (solo Vercel)
.gitignore            → archivos a ignorar en Git
```

## Previsualizar en tu compu

Abrí `index.html` con doble clic en el navegador.

## Paso 1 — Subir a GitHub (forma correcta)

> 🔑 **Lo más importante:** el `index.html` tiene que quedar en la **raíz** del repo, NO dentro de una subcarpeta. Si arrastrás la carpeta entera, GitHub la deja anidada y Vercel da **404**.

1. En GitHub: **New repository** → ponele un nombre (ej. `codex-web`) → **Create**.
2. En el repo vacío: **Add file → Upload files**.
3. Abrí esta carpeta en tu compu, **seleccioná TODOS los archivos de adentro** (Ctrl+A) y arrastrá **esos archivos** (no la carpeta) a GitHub.
4. **Commit changes**.

Así el repo queda con `index.html` arriba de todo (en la raíz). ✅

## Paso 2 — Desplegar en Vercel

1. Entrá a [vercel.com](https://vercel.com) → **Add New → Project** → **Import** tu repo de GitHub.
2. Configurá:
   - **Framework Preset:** `Other`
   - **Build Command:** *(vacío)*
   - **Output Directory:** *(vacío)*
   - **Root Directory:** `./`
3. **Deploy**. Te da una URL tipo `tu-proyecto.vercel.app`.

El `vercel.json` aplica las cabeceras de seguridad solo.

### Si te sale 404
Es que el `index.html` quedó dentro de una subcarpeta en el repo. Solución rápida:
**Vercel → tu proyecto → Settings → General → Root Directory → Edit → poné el nombre de la subcarpeta → Save → Redeploy.**

## ⚠️ Importante: el dominio de la imagen de previsualización

Para que la imagen al compartir el link aparezca, las URLs absolutas dentro de `index.html` deben coincidir con el dominio donde despliegues.

Ahora apuntan a `https://codexautokeys.com/`. Si lo subís a otro dominio (Vercel o GitHub Pages), reemplazá `codexautokeys.com` por tu dominio nuevo en `index.html` (aparece en 6 lugares: `og:url`, `og:image`, `twitter:image`, `canonical`, y dos veces en el JSON-LD).

## Pendientes

- Confirmar que la dirección de texto ("4to Anillo y Av. Alemania #4160") coincide con el pin de Google Maps.
- Conectar el dominio codexautokeys.com al hosting (Vercel) y volver a desplegar.
