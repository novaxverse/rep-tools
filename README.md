# NovaXverse · Repositorio de Instaladores

Página de descargas de NovaXverse con herramientas, homebrew y utilidades para PS4.

Hay **dos versiones** de la misma página:

| Versión | URL | Uso |
|---|---|---|
| HTTPS (GitHub Pages) | `https://novaxverse.github.io/rep-tools/` | Catálogo y descargas del `.pkg`. El navegador de la PS4 **bloquea** desde aquí hablar con la consola. |
| **HTTP (host gratuito)** | `http://TU-SUBDOMINIO.rf.gd` | La página **de instalación**. Desde HTTP el navegador PS4 sí permite arrancar RPI e instalar. |

## Flujo completo (sin PC)

> En firmware 11.00+/12.00/12.5x/13.00 el PayLoader de GoldHEN (puerto 9090) **solo acepta payloads de kernel**: RPI y los homebrew se instalan como **app** (pkg), no se envían por 9090. La instancia se hace **una sola vez**; después todo funciona desde la página.

1. **Libera la PS4** en el navegador de la consola con cualquier host (ver abajo). Queda GoldHEN 2.4b18 activo.
2. **Instala una sola vez** `RPI.pkg` (card **RPI Instalador Remoto**): con **FPKGi** (se instala igual por USB → GoldHEN Debug Settings → Install Package) o con **USB → Debug Settings → Install Package**. Abre RPI desde el menú: abre el puerto 12801.
3. **Abre la versión HTTP** (`http://...rf.gd`) en el navegador de la PS4.
4. Pulsa **🔗 COMPROBAR INSTALADOR (RPI)** → debe mostrar `INSTALADOR ACTIVO ✔ (puerto 12801)`.
5. Pulsa **📥 INSTALAR EN PS4** en la tarjeta que quieras → la consola descarga el `.pkg` e instala sola.

> Si entras por la versión HTTPS (GitHub) los botones no funcionarán: el navegador PS4 bloquea el tráfico a `127.0.0.1` desde páginas HTTPS (limite de navegador). La página lo avisa al pulsar.

## Liberar la PS4 con WebKit

Abre el enlace que corresponda a tu firmware desde el navegador de la PS4:

| Firmware | Host de exploit |
|---|---|
| 7.00 – 13.00 | https://gamerhack.github.io/g2all/ |
| 11.50 – 13.00 | https://rawgame4.github.io |
| 6.00 – 13.00 | https://zecoxao.github.io/ntfonto/ |
| 6.00 – 13.00 | https://novaxverse.github.io/CSSExploit/public/ |

## Publicar la versión HTTP (host gratuito)

La comunicación de la página con RPI (`127.0.0.1:12801`, y el arranque de RPI en consolas antiguas) solo funciona si la página se sirve **por HTTP** (GitHub Pages fuerza HTTPS). Se usa un hosting estático gratis que no fuerce HTTPS, por ejemplo **InfinityFree** (el mismo método que usa `hippie68.rf.gd`):

1. Crea una cuenta en `infinityfree.com` y un "hosting account" con subdominio, p. ej. `novaxverse.rf.gd`.
2. Sube al `htdocs` de ese hosting los 3 archivos del repo:
   - `index.html`
   - `style.css`
   - `enlaces.js`
3. `RPI.pkg` ya está en un release de GitHub (`vR2`) y su tarjeta ya tiene el enlace en `enlaces.js`; no hace falta subirlo al hosting.
4. Abre `http://novaxverse.rf.gd` desde el navegador de la PS4 y sigue el flujo de arriba.

> En el plan gratis InfinityFree inserta un marco publicitario sobre la página; es cosmético y no afecta al flujo. Todo el resto (catálogo, `.pkg`) puede seguir en GitHub.

## Archivos

- `index.html` — la página (catálogo + COMPROBAR INSTALADOR + INSTALAR EN PS4).
- `style.css` — estilos.
- `enlaces.js` — datos de las tarjetas (URLs de descarga directa).
- `RPI.pkg` — instalador remoto (puerto 12801), pkg oficial de `njzydark/PS4RPI` 1.02, listo para subir a un release.

## Únete a esta VERSE

- **📺 YouTube:** mira nuestros tutoriales y novedades en [NovaX Verse](https://www.youtube.com/@novax_verse)
- **🐦 Twitter/X:** síguenos para estar al día en [@NovaXverse](https://x.com/NovaXverse)