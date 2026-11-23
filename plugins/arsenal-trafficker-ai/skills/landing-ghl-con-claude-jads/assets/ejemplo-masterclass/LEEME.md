# Ejemplo: landing de masterclass en GHL

Código que estuvo publicado y verificado en un proyecto real, con los datos personales reemplazados por marcadores `{{…}}`. Úsalo como base: **antes de pegarlo en GHL, rellena todos los marcadores** y cambia paleta y textos de venta por los del proyecto nuevo. Comprueba al final que no quede ningún `{{` en el código pegado (`grep "{{"`).

| Archivo | Dónde va en GHL |
|---|---|
| `01-landing-css.html` | Landing, bloque de código 1 (CSS) |
| `02-landing-html.html` | Landing, bloque 2 (HTML) |
| `03-landing-script.html` | Landing, bloque 3 (barra fija móvil, slider, carga diferida de `form_embed.js`) |
| `gracias-css.html` / `gracias-html.html` | Página de gracias, bloques 1 y 2 |
| `politica-privacidad.html` | Un único bloque, en un **embudo propio** |
| `encabezado-embudo-landing-favicon-y-titulo.html` | Configuración del embudo de la landing → "Código de seguimiento del encabezado" |
| `encabezado-embudo-privacidad-titulo.html` | Lo mismo, en el embudo de la política de privacidad |

## Marcadores que debes rellenar (pídeselos al usuario; no los inventes)

| Marcador | Qué es |
|---|---|
| `{{NOMBRE_DEL_EVENTO}}` | Nombre del evento o marca que aparece en título, pie y política |
| `{{NOMBRE_DEL_NEGOCIO}}` | Razón o nombre comercial responsable de los datos |
| `{{DOMINIO}}` | Dominio conectado en GHL (sin `https://`) |
| `{{PAIS}}` | País desde donde opera (la política cita la ley peruana de protección de datos: cámbiala si el país es otro) |
| `{{CORREO_DE_CONTACTO}}` | Correo público para derechos sobre datos |
| `{{ENLACE_GRUPO_WHATSAPP}}` | Enlace de invitación del grupo |
| `{{ID_FORMULARIO}}` y `{{NOMBRE_DEL_FORMULARIO}}` | ID y nombre del formulario de GHL |
| `{{URL_FOTO_PRINCIPAL_RECORTADA}}`, `{{URL_FOTO_SLIDER_n}}` | URLs del CDN de GHL tras subir las imágenes a la biblioteca de medios |
| `{{NOMBRE}}`, `{{PROFESION}}`, `{{DESCRIPCION_FOTO_n}}` | Textos alternativos de las fotos |
| `{{BIO_DE_2_O_3_FRASES…}}`, `{{CIFRA_n}}`, `{{QUE_MIDE_CIFRA_n}}`, `{{CREDENCIAL_n}}` | Bio, cifras y credenciales **confirmadas por el usuario** |
| `{{TITULO_DE_LA_PAGINA_DE_REGISTRO}}` | Título de la pestaña de la landing |

Los textos de venta (titular, problema, escenarios, "lo que descubrirás") quedaron como ejemplo del tono y la estructura: reescríbelos para la oferta nueva.

Marcas útiles para verificar versiones en vivo: `aboutgrid`, `data-cta`, `loadEmbed`, `function onda`, `hero-img`.
