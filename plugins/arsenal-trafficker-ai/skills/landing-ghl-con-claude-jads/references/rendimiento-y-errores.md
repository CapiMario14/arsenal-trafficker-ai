# Rendimiento y errores que ya nos pasaron

## El caso: "la landing no carga ni deja hacer scroll"
**Síntoma:** al abrir la página solo se veía el primer bloque; no se podía bajar; PageSpeed (móvil) decía 96 y LCP 0,9 s.

**Causa real (medida, no supuesta):** el script `https://link.msgsync.com/js/form_embed.js` estaba dentro del HTML del bloque, justo en el hero. Ese día tardó **21 s** en responder. GHL espera a que un script externo termine antes de seguir armando el resto de la página, así que todo lo de abajo y sus propios archivos JS quedaron en espera. En el DOM: `readyState: "loading"`, alto de página 768 px.

**Cómo se encontró:** `performance.getEntriesByType('resource')` mostró `form_embed.js` con `duration ≈ 21000` y los archivos de GHL empezando justo después.

**Arreglo:**
1. Quitar el `<script src="…form_embed.js">` del HTML.
2. Cargarlo desde el bloque de script, de forma asíncrona, cuando la página ya cargó:
```js
function loadEmbed(){var s=document.createElement('script');s.src='https://link.msgsync.com/js/form_embed.js';s.async=true;document.body.appendChild(s);}
if(document.readyState==='complete'){setTimeout(loadEmbed,0);}else{window.addEventListener('load',loadEmbed);}
```
3. El iframe del formulario con `loading="lazy"` y el formulario abajo de la página, no en el primer pantallazo.

**Por qué PageSpeed no lo vio:** mide una carga puntual y la lentitud del servidor de terceros era intermitente. La métrica no desmiente al usuario.

**Enseñanza para el proceso:** cuando el usuario reporta un problema que tu herramienta no ve, no lo discutas. Mide el recurso real, prueba otra vía y, si hace falta, pídele una grabación de pantalla (una grabación con el celular sirve; revísala cuadro por cuadro).

## Otras reglas de rendimiento
- **Animaciones continuas:** evítalas. Animar `box-shadow` repinta en cada cuadro. Si hace falta algo vivo, que sea una animación de `transform`/`opacity` y de una sola cosa.
- **`content-visibility:auto`:** no lo uses en secciones largas; cambia el alto de la página mientras se hace scroll (3113 → 3328 px) y confunde el scroll.
- **Fuentes de Google:** un solo `<link>` con pocos pesos (400, 600, 800 y uno para datos). Precargar con `rel="preload"` más `preconnect` extra empeoró la advertencia de PageSpeed sobre preconnect (GHL ya trae varios).
- **Imágenes:** WebP pequeñas (una foto de héroe de 1,3 MB en SVG pasó a 61 KB). Fotos de slider 70–130 KB. Siempre `width`/`height` y `loading="lazy"` salvo la del héroe (`fetchpriority="high"`).
- **El fondo fijo de GHL (`bg-fixed`) y Cloudflare Insights** aparecen en el DOM; si hay jank de scroll, son candidatos.
- **Ajuste "Optimizar JavaScript" del embudo:** carga diferida del código personalizado; viene activado.

## Errores de proceso que costaron tiempo
| Error | Consecuencia | Prevención |
|---|---|---|
| Clic en "Guardar" a altura fija sin mirar | Solo se guardó un bloque; página publicada a medias (HTML y script nuevos con CSS viejo) | Captura tras abrir el modal; comprobar la hora de "Última vez guardado" |
| Dar por bueno "publicado" sin verificar | El usuario vio la versión vieja | Verificar con marca única, esperar la caché |
| Falso positivo por cadena genérica | Creí que el CSS nuevo estaba | Marca única |
| Teclear 9 KB con `type` | Editor congelado | Portapapeles |
| Medir animaciones con el panel oculto | Concluí que fallaban | Mostrar el panel antes |
| Pestaña de builder vieja abierta | Se revirtió la publicación | Una sola pestaña de editor |
| Intentar añadir la política como paso del embudo de la landing | El usuario cortó la acción | Embudo nuevo por proyecto |
| Enlaces legales por defecto del formulario | Apuntaban a `example.com` | Revisar el HTML del formulario publicado |

## Pantallas de comprobación recomendadas
1024, 1300 px (laptop con zoom) y 375 px (celular). Un laptop con zoom del navegador al 125 % se comporta como ≈1300 px de ancho: calcula con eso.
