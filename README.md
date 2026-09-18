# 📦 Repositorio de Instaladores PS4 — Guía completa

Página web para alojar en **GitHub Pages** tus enlaces de descarga (MediaFire) para tu canal.

---

## 1. Cómo publicarla en GitHub (paso a paso)

1. Crea una cuenta en [github.com](https://github.com) si no la tienes.
2. Pulsa el botón verde **New** (Nuevo repositorio).
3. Pónle un nombre, p. ej. `novaxverse`. Deja todo lo demás como está y pulsa **Create repository**.
4. Sube los archivos de esta carpeta (arrastra SOLO archivos, no carpetas):
   - `index.html`
   - `style.css`
   - `enlaces.js`
   - `banner.png`  ← tu banner va junto al `index.html` (no en carpetas)
   - si quieres también `README.md`

5. Activa la página: entra en tu repo → pestaña **Settings** → menú lateral **Pages** → en **Branch** elige `main` y carpeta `/ (root)` → **Save**.
6. Espera 1–2 minutos. Te aparecerá una dirección así:
   `https://TUUSUARIO.github.io/novaxverse/`

   **Esa es tu página.** Ábrela en el navegador de tu PS4 liberada y listo.

> 💡 Cada vez que modifiques `enlaces.js` y hagas *push*, la página se actualiza sola.

---

## 2. Dónde editar el código

| Qué quieres cambiar | Dónde |
|---|---|
| **Añadir/quitar enlaces de descarga** | Archivo `enlaces.js` (tiene instrucciones explicadas arriba) |
| **Colores y tema del canal** | Archivo `style.css`, las variables de arriba (`:root`) |
| **Nombre del canal / encabezado** | Archivo `index.html`, línea que dice `MI&nbsp;CANAL` y el `<h1>` |
| **Instrucciones del aviso** | Archivo `index.html`, dentro de la sección `.aviso` |

### Ejemplo: añadir un segundo enlace
Abre `enlaces.js` y tras el bloque de `Store-R2.pkg` pega (con coma):

```js
  ,
  {
    categoria: "Juegos",
    titulo: "Nombre del Juego.pkg",
    descripcion: "Descripción del juego.",
    tamano: "2 GB",
    url: "https://www.mediafire.com/file/TUCODIGO/Nombre.pkg/file"
  }
```

---

## 3. Como acortar el enlace (opcional)

MediaFire no permite acortar la URL oficialmente, pero el enlace debe funcionar tal cual en la PS4. Si aún así quieres uno más corto:

- **TinyURL:** entra en [tinyurl.com](https://tinyurl.com), pega el enlace de MediaFire y te genera uno corto tipo `https://tinyurl.com/xyz`.
- En `enlaces.js`, pon en `url:` el enlace corto en lugar del de MediaFire.

---

## 4. Flujo de descarga actual (MediaFire → GoldHEN)

El repositorio **solo contiene la página** (no se suben `.pkg`). Los archivos están en MediaFire y la página apunta sus enlaces:

1. En `enlaces.js`, cada archivo lleva su `url:` de MediaFire.
2. En la PS4 liberada (GoldHEN activo), abre la página y pulsa **Descargar**.
3. Se abre MediaFire → pulsas **Download** → el `.pkg` baja a la consola.
4. Cuando termina, lo instalas desde GoldHEN (o Debug Settings → Package Installer).

> 💡 Los enlaces directos de MediaFire (`download###.mediafire.com/...`) caducan.
> Si quieres usar uno, en `enlaces.js` pegas el de la caja de MediaFire normal.

---

## 5. (Opcional) Instalación automática con RPI

Si algún día quieres que la PS4 **descargue e instale sola**, usa Remote Package Installer (RPI) con un **enlace directo** al `.pkg`:

1. Pega en el RPI el enlace directo (p. ej. uno de GitHub Releases).
2. La consola lo descarga e instala automáticamente.

---

## 6. Archivos grandes: GitHub Releases (2 GB)

GitHub permite subir en **Releases** archivos de hasta **2 GB** con **enlace directo** para usarlo con el RPI u otro gestor:

1. En tu repo pulsa **Releases** → **Create a new release**.
2. Rellena `Tag` y `Title`, y arrastra tu archivo `.pkg` en **Attach binaries** → **Publish release**.
3. Clic derecho sobre el nombre del `.pkg` → **Copiar enlace**.

> El enlace tiene este formato y **baja directo sin pasar por ninguna web**:
> `https://github.com/TUUSUARIO/novaxverse/releases/download/NOMBRE-TAG/Nombre.pkg`