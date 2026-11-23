# Operar GHL con Claude in Chrome

Todo lo que hay que saber para tocar el builder de GHL sin romper nada. Está escrito desde errores reales de este proyecto.

## Herramientas
- Claude in Chrome: carga las herramientas con ToolSearch en una sola llamada (`tabs_context_mcp`, `navigate`, `computer`, `find`, `javascript_tool`, `file_upload`, `read_page`). Usa `browser_batch` para encadenar acciones.
- Navegador integrado de la app: sirve para revisar páginas **públicas**; no tiene la sesión de GHL.
- Si el grupo de pestañas de Chrome cambia entre turnos, vuelve a llamar `tabs_context_mcp` con `createIfEmpty: true`.
- Una pestaña de Chrome puede congelarse (captura con timeout): espera unos segundos y reintenta.
- Las esperas (`wait`) admiten **máximo 10 s** por acción.

## Rutas útiles (sustituye los IDs)
- Lista de embudos: `/v2/location/{LOC}/funnels-websites/funnels`
- Un embudo y sus pasos: `/v2/location/{LOC}/funnels-websites/funnels/{FUNNEL}/steps/{STEP}/overview`
- Configuración del embudo (dominio, favicon, código de encabezado): `…/funnels/{FUNNEL}/settings`
- Builder de una página: `/location/{LOC}/page-builder/{PAGE}`
- Lista de formularios: `/v2/location/{LOC}/form-builder/main`
- Editor de un formulario: `/v2/location/{LOC}/form-builder-v2/{FORM}`
- Biblioteca de medios: `/v2/location/{LOC}/media-storage`

## Pegar código en un bloque (procedimiento fiable)
1. Guarda el código en un archivo local y cópialo al portapapeles:
   `Get-Content -Raw -Encoding UTF8 archivo.html | Set-Clipboard`
   Comprueba que contiene la marca esperada (sin usar comillas anidadas raras dentro de `$(...)` en PowerShell: asigna a variables primero).
2. En el builder: clic en el bloque → panel derecho → **"Abrir el editor sin formato"**. Si el panel derecho no se ve, pulsa el ícono de la esquina superior derecha ("Ocultar/Mostrar configuración").
3. Clic dentro del editor → `Ctrl+A` → `Ctrl+V`. **No teclees el código con `type`**: más de unos pocos cientos de caracteres congela el editor.
4. `Ctrl+Home` / `Ctrl+End` y captura para comprobar el principio y el final pegados.
5. **Captura y localiza el botón "Guardar" del modal.** Su altura cambia según el alto de la ventana (≈552 px con ventana de 675 px de alto; ≈520 px con 606 px). Un clic fuera del botón no guarda nada y no avisa. Fue el origen de una publicación a medias.
6. Guarda el bloque → guarda la página con el ícono de disquete de la barra superior → **comprueba que "Última vez guardado" muestra la hora nueva** → recién entonces publica.

## Publicar
- Botón "Publicar" arriba a la derecha. Muestra "Publicando…" y luego vuelve a "Publicar"; a veces aparece un aviso verde.
- Si se queda en "Publicando…" más de ~2 min, recarga el builder (se pierden cambios no guardados, avísalo) y vuelve a publicar.
- Si dos pestañas del builder están abiertas, una con una copia vieja puede guardar encima y revertir la página publicada (pasó una vez). Pide al usuario cerrar otras pestañas del editor.

## Caché y verificación
La página pública pasa por una caché (Cloudflare, ~60 s, `cf-cache-status`: `HIT`, `UPDATING`, `EXPIRED`). Tras publicar:
```js
const r = await fetch('/ruta?nc=' + Date.now(), {cache:'no-store'});
const h = await r.text();
h.includes('MARCA_UNICA_DE_LA_VERSION_NUEVA')
```
- Usa una **marca única** de la versión nueva. Una cadena genérica (por ejemplo `white-space:nowrap`) puede existir ya en la versión vieja y dar un falso positivo.
- `UPDATING` con `age` alto significa que aún sirve la copia anterior: espera 15–60 s y repite.
- No hagas bucles de espera de más de ~40 s en una sola llamada de JavaScript (hay timeout de 45 s).
- Después de la verificación por texto, mide el DOM real: alto de página, desbordes, elementos esperados.

## Pestaña oculta = pruebas engañosas
Si el panel del navegador integrado está oculto, `requestAnimationFrame`, eventos de scroll, `IntersectionObserver` y animaciones se pausan, y las pruebas del slider o de animaciones fallan sin que el código esté mal. Antes de probar interacción, muestra el panel (`mcp__ccd_view__show_pane` con `preview`). Para móvil usa `resize_window` con `preset: "mobile"` y **restaura `desktop` al terminar**.

## Subir archivos a la biblioteca de medios
`file_upload` sobre el input "Subir" (búscalo con `find`). Luego extrae la URL pública del DOM: las miniaturas traen `…/u_https://assets.cdn.filesafe.space/{LOC}/media/{ID}.{ext}`. Verifica con `fetch` (status 200, tamaño y dimensiones esperados) antes de usarla.

## Acciones sensibles
- Nunca escribas contraseñas.
- Antes de eliminar un elemento, confirma que está seleccionado el correcto (el panel derecho muestra el nombre, por ejemplo "Button").
- Un diálogo abierto por error (por ejemplo "Nuevo paso") se cierra con Cancelar; comprueba después que no se creó nada.
- No envíes formularios de prueba que creen contactos reales sin permiso; pídele al usuario que haga el registro de prueba.

## Atajos de interfaz que sirvieron
- Quick add: botón "+" dentro de la sección → "Filas → 1 Columna" → "+" dentro de la columna → buscar "HTML" → elemento "Código".
- Una página nueva "desde cero" empieza vacía: "Sección en blanco" y de ahí en adelante.
- GHL agrega rellenos por defecto (sección 20 px, fila y columna 10 px). Para diseño a sangre, anúlalos desde el CSS propio: `.fullSection,.c-row,.c-column{padding:0!important}`.
