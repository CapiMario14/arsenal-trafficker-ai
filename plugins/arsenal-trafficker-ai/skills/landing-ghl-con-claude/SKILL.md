---
name: landing-ghl-con-claude
description: Flujo completo para construir, publicar y verificar una landing page (registro a masterclass, captación de leads) en GoHighLevel usando Claude + Claude in Chrome. Cubre estructura y copy de la landing, código en 3 bloques (CSS / HTML / script), formulario GHL, página de gracias, política de privacidad, imágenes, favicon animado, título de pestaña, rendimiento y verificación en vivo. Úsalo siempre que el usuario hable de una landing en GHL, GoHighLevel, embudos/funnels, "página de registro", "página de gracias", formulario de GHL, "código personalizado" o "HTML/Javascript" del builder, publicar una página en su dominio, o de una landing que carga lenta o no deja hacer scroll — aunque no mencione la palabra "skill" ni "landing".
---

# Landing en GHL con Claude

Este skill documenta cómo se construyó, de punta a punta, la landing una masterclass gratuita de publicidad digital (registro a una masterclass gratuita → página de gracias con grupo de WhatsApp → política de privacidad) dentro de GoHighLevel, controlando el navegador del usuario con Claude in Chrome. Está escrito desde lo que salió bien y desde lo que falló, porque casi todos los problemas costosos fueron de proceso, no de diseño.

El código que funcionó está en `assets/ejemplo-masterclass/`. Úsalo como punto de partida y adáptalo: no lo copies a ciegas (paleta, textos, cifras, fotos y enlaces son del proyecto original).

## Qué leer y cuándo

| Necesitas… | Lee |
|---|---|
| Operar el builder de GHL con Chrome: pegar código, guardar, publicar, caché | `references/operar-ghl-con-chrome.md` |
| Entender qué rompió la página y cómo evitarlo (rendimiento, scroll, scripts de terceros) | `references/rendimiento-y-errores.md` |
| Estructura, copy y patrones de diseño de la landing (secciones, botones, slider, bio) | `references/estructura-landing.md` |
| Imágenes, favicon animado, título, formulario, gracias, privacidad | `references/imagenes-formulario-y-extras.md` |
| Código de referencia ya probado | `assets/ejemplo-masterclass/` |

Lee `operar-ghl-con-chrome.md` y `rendimiento-y-errores.md` **antes de tocar GHL**. Las otras se leen según la tarea.

## Principios (y por qué)

1. **Cree lo que dice el usuario antes que lo que mide una herramienta.** PageSpeed dio 96 en móvil mientras el usuario veía la página trabada. Tenía razón: un script de terceros tardaba 21 s en responder y bloqueaba todo. Si el usuario describe un síntoma, búscalo en el sitio real (tiempos de recursos, estado del DOM) en lugar de defender el puntaje.
2. **Nada de scripts externos dentro del flujo del HTML.** Un `<script src=…>` en medio de un bloque de código obliga a GHL a esperar a que baje antes de seguir armando la página. Los scripts de terceros (`form_embed.js`) se cargan aparte, de forma asíncrona, cuando la página ya terminó de cargar.
3. **Escribir poco, pegar mucho.** Teclear código largo en el editor de GHL lo congela. El flujo fiable es: guardar el archivo en disco, copiarlo al portapapeles con PowerShell y pegarlo con Ctrl+V.
4. **Verificar en vivo, no en el editor.** "Guardado" y "publicado" en GHL no garantizan que el servidor ya sirva lo nuevo. Cada cambio se confirma bajando la página pública y buscando una marca única de la versión nueva.
5. **Reportar con franqueza qué se probó y qué no.** Separa siempre "lo comprobé en vivo" de "no pude comprobarlo" (por ejemplo, el scroll con el dedo en un celular real, o un envío real del formulario).
6. **Un embudo por proyecto.** Las páginas que no son parte del flujo registro → gracias (por ejemplo, la política de privacidad) van en un embudo nuevo de un solo paso. Mezclarlas comparte dominio, favicon y código de encabezado, y rompe cosas. El usuario lo pidió explícitamente.
7. **Acciones de cara al público se confirman o ya están autorizadas.** Publicar, cambiar la redirección de un formulario, subir archivos y borrar elementos cambian lo que ve el público. Si el usuario ya lo pidió en palabras, hazlo; si no, pregunta antes.

## Flujo de trabajo

### 0. Antes de empezar
- Confirma la sesión: el usuario debe estar logueado en su Chrome. Usa Claude in Chrome (herramientas `mcp__claude-in-chrome__*`, se cargan con ToolSearch). Las contraseñas las escribe el usuario, nunca tú. El navegador integrado de la app no tiene su sesión de GHL, pero sirve para revisar páginas públicas.
- Reúne el brief: oferta, fecha y hora (con husos horarios si el público es de varios países), bio y cifras con **confirmación del usuario** (no las inventes), fotos, enlace de WhatsApp, correo de contacto.
- En Windows puede no haber Python: usa Node para scripts locales y PowerShell (`Set-Clipboard`) para el portapapeles.

### 1. Diseñar la estructura y el copy
Pide o propón primero el **esqueleto en texto** y que el usuario lo apruebe antes de escribir código. Ver `references/estructura-landing.md`. Orden que funcionó: titular y promesa → problema → camino/números → qué descubrirá → quién está detrás → formulario → pie. Un botón en cada sección que baja al formulario.

### 2. Escribir el código en 3 bloques
Cada página de GHL = Sección → Fila (1 columna) → **3 elementos "Código" (HTML/Javascript personalizado)**:
- Bloque 1: CSS (con la fuente y estilos, todo con prefijo de clase propio, por ejemplo `.jda`).
- Bloque 2: HTML.
- Bloque 3: script pequeño (barra fija móvil, slider, carga diferida de `form_embed.js`).

Un bloque largo único se corta o se daña; tres bloques cortos son manejables y editables por separado.

### 3. Subir imágenes y obtener URLs
Convierte a WebP liviano, sube a la biblioteca de medios de GHL y usa la URL del CDN. Ver `references/imagenes-formulario-y-extras.md`.

### 4. Formulario, redirección y legales
Se incrusta como `iframe` con `loading="lazy"`. La redirección se configura en el formulario (Al enviar → Redirigir a la URL). Cuidado: GHL pone enlaces legales de relleno a `example.com`.

### 5. Pegar, guardar y publicar en GHL
Procedimiento exacto, con las trampas de coordenadas y de "guardado", en `references/operar-ghl-con-chrome.md`. Resumen: abrir el bloque → editor sin formato → Ctrl+A → Ctrl+V → **captura de pantalla para ubicar "Guardar"** → guardar bloque → guardar página y comprobar que cambió la hora de "Última vez guardado" → publicar.

### 6. Verificar en vivo
Tras publicar, espera a que la caché se renueve (1–2 min) y comprueba con una marca única. Después revisa en laptop (≈1300 px y 1024 px) y celular (375 px): sin desbordes horizontales, botones que llevan al formulario, formulario cargado, fotos cargadas. Nunca des por hecho un cambio solo porque el editor dijo "guardado".

### 7. Extras del flujo completo
Página de gracias (una tarjeta, un botón a WhatsApp), política de privacidad en embudo propio, título y favicon por código de encabezado del embudo, pie con enlace a la política. Detalles en `references/imagenes-formulario-y-extras.md`.

## Lista de comprobación final
- [ ] La página carga completa en menos de ~4 s y el scroll llega al final.
- [ ] No hay `<script src>` externo dentro de los bloques de código.
- [ ] Todos los botones de reserva llevan al formulario; el formulario carga y envía.
- [ ] La redirección post-envío lleva a la página de gracias (probado con un registro real hecho por el usuario).
- [ ] Sin textos entre corchetes ni enlaces a `example.com`.
- [ ] Título de pestaña y favicon correctos en registro y gracias.
- [ ] Política de privacidad publicada y enlazada, con el correo que el usuario dio.
- [ ] Móvil: sin desborde horizontal; barra fija no tapa el pie.
- [ ] Informe final: qué se verificó en vivo, qué no se pudo verificar, qué queda pendiente.

## Estilo de trabajo con el usuario
Español, directo y concreto. Cuando algo falló por tu culpa, dilo sin rodeos y explica la causa en lenguaje simple (con una analogía si ayuda). Si el usuario muestra frustración, no discutas: reproduce el problema por otra vía. Entre pasos largos, avisa en una línea qué estás haciendo.
