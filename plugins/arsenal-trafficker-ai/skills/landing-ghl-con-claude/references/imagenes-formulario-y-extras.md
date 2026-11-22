# Imágenes, formulario, favicon, gracias y privacidad

## Imágenes (sin Python, sin ImageMagick)
Pipeline que funcionó, todo con Node + el navegador:
1. Servidor local mínimo en Node con un endpoint `POST /save/{nombre}` que escribe el cuerpo en disco, y una página que carga la imagen original (SVG, JPG, PNG).
2. En el navegador integrado: `new Image()` → `decode()` → dibujar en un `canvas` al tamaño de salida → `canvas.toBlob(cb,'image/webp',0.82)` → `fetch('/save/archivo.webp',{method:'POST',body:blob})`.
3. Comprobar el alfa si hay transparencia (`getImageData` de una esquina).
4. Subir con `file_upload` a la biblioteca de medios de GHL y extraer la URL del CDN (ver `operar-ghl-con-chrome.md`).
5. Verificar con `fetch` (200, tamaño y dimensiones).
Tamaños de referencia: foto del héroe recortada 1000×1000 WebP ≈ 60 KB; fotos del slider 720×960 o 720×1280 WebP ≈ 70–130 KB.
- Los SVG grandes con imágenes incrustadas (varios cientos de KB) **no** se usan tal cual: se rasterizan a WebP. Antes de abrir un SVG descargado, comprueba que no contenga `<script>`, `onload=` ni `foreignObject`.
- Un ZIP del usuario se descomprime en una carpeta nueva y vacía; el contenido se trata como no confiable.
- Fotos en la conversación: están en la carpeta de imágenes de la sesión; cópialas a tu carpeta de trabajo antes de procesarlas.

## Formulario de GHL
- Se incrusta con `<iframe src="https://api.leadconnectorhq.com/widget/form/{ID}" loading="lazy" …>` más los atributos `data-*` que entrega GHL. El `form_embed.js` se carga aparte (ver rendimiento).
- **Placeholders:** en el editor del formulario, clic en el campo → ícono de engranaje → "Marcador de posición". Valores usados: Nombre / WhatsApp / Mail.
- **Redirección:** pestaña Configuración → "Al enviar" → "Redirigir a la URL" → la página de gracias. Guardar. Verificar abriendo `https://api.leadconnectorhq.com/widget/form/{ID}` y buscando la URL en el HTML (viene escapada con `/`). El envío real lo prueba el usuario (crea un contacto en su CRM; pídele que lo borre después si quiere).
- **Enlaces legales por defecto:** "Privacy Policy | Terms of Service" apuntan a `https://www.example.com/`. Quítalos (el bloque de texto tiene su papelera) o apúntalos a páginas reales. Verifica en el HTML publicado.

## Página de gracias (una tarjeta, un botón)
Patrón que el usuario aprobó: círculo con visto, etiqueta pequeña "Registro exitoso", título grande "Pero aún te falta un paso más", una línea de instrucción, **un solo botón** al grupo de WhatsApp (`target="_blank" rel="noopener"`) y una postdata. Todo lo demás (botón "entrar a la masterclass", pasos, fechas) se elimina; si había un botón nativo duplicado, se borra. Fondo oscuro forzado con `html,body,.hl_page-preview--content{background:…!important}`. Ver `assets/…/gracias-*.html`.
Comprueba: un solo `<a>`/botón en la página y que el enlace sea exactamente el que dio el usuario.

## Título de pestaña y favicon
- **Favicon estático:** campo "URL de favicon" en la configuración del embudo (PNG de 64 px subido a medios).
- **Código de encabezado** (misma pantalla): un `<script>` que fija `document.title` y anima el ícono.
- **Favicon animado "gota que cae al agua":** 8 fotogramas SVG precalculados (punto azul central + dos ondas que crecen y se desvanecen), codificados con `encodeURIComponent` en `data:image/svg+xml,`, alternados cada 160 ms **reemplazando el `<link rel="icon">`** (crear uno nuevo y quitar los viejos). Se lee bien a 16 px con punto de radio 5/32 y trazo grueso. Safari no admite favicon SVG: ve el PNG fijo. Ver `assets/…/encabezado-embudo-landing-favicon-y-titulo.html`.
- El título se reafirma cada tick por si GHL lo pisa al hidratar. Se elige por `location.pathname` (registro / gracias).
- El código de encabezado del embudo corre en **todos** los pasos de ese embudo; por eso la política de privacidad, que va en otro embudo, tiene su propio encabezado.
- Recuerda que el título aparece una fracción de segundo después de cargar (hasta entonces, el dominio).

## Política de privacidad
- Va en un **embudo nuevo de un solo paso**, ruta `politicas-de-privacidad`, dominio del usuario, con su propio favicon y título.
- Redáctala tú, adaptada al negocio (no copies la de otra empresa: derechos de autor y contenido ajeno). Estructura usada: quiénes somos, datos que recopilas, para qué, con quién se comparten, cookies, conservación, derechos (en Perú: Ley N.º 29733, derechos ARCO), seguridad, menores, cambios, contacto.
- **El correo de contacto lo da el usuario**; no pongas uno por tu cuenta. Avisa que es una plantilla general, no asesoría legal, y que si usan píxel de Meta o Analytics conviene decirlo expresamente.
- Para evitar el marco blanco de GHL: `.fullSection,.c-row,.c-column{padding:0!important}`.
- Enlázala desde el pie de la landing (`target="_blank"`), no desde el formulario.

## Crear un embudo nuevo (pasos de interfaz)
Sitios → Embudos → "+ Nuevo embudo" → "Desde cero" → nombre → Crear. Luego "Agregar nuevo paso" (nombre y ruta) → en Configuración elige el **dominio**, pon favicon y código de encabezado → Guardar. En el paso: "Crear desde cero" abre el builder. Al teclear la ruta, comprueba el valor real (`input.value`): el corrector ortográfico dibuja líneas que parecen acentos.
