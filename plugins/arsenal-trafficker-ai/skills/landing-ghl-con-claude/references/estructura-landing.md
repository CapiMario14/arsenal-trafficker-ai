# Estructura, copy y patrones de diseño

## Regla de oro del proceso
Entrega primero el **esqueleto en texto** (secciones, copy, botones) y espera el visto bueno. El usuario aprobó el texto antes de ver código, y ahorró rondas. Pide los datos que no puedes inventar: bio, cifras, fotos, fecha/hora, correo, enlace de WhatsApp.

## Esqueleto que funcionó (masterclass gratuita)
1. **Titular y promesa** (fondo oscuro): etiqueta "Masterclass gratis en vivo", titular con la cifra destacada, subtítulo para quién es, cajita de fecha con **hora en cada país del público** (Perú 7:00 PM / México 6:00 PM / Argentina 9:00 PM), botón al formulario y foto a la derecha.
2. **El problema**: una pregunta incómoda ("¿Y si mañana cambian las condiciones?") + dos tarjetas por perfil (por ejemplo "Si eres egresado en marketing" / "Si vienes de otra carrera"): dolor + qué necesita.
3. **El camino a la cifra prometida**: qué hace el profesional, a quién le sirve, por qué se paga; y **dos escenarios** con cuentas (2 × USD 500 = USD 1.000; 3 × USD 350 = USD 1.050; muestra la cifra real, no la redondees).
4. **Lo que descubrirás**: 5 tarjetas numeradas, cada una con título y una línea.
5. **Quién está detrás**: párrafo corto + 3 cifras de autoridad + lista de credenciales + slider de fotos.
6. **Formulario** (abajo): "Regístrate aquí y reserva tu cupo", repitiendo fecha y horas.
7. **Pie**: nombre del evento + enlace a la política de privacidad + aclaración de resultados ("los resultados dependen de cada persona… son un objetivo, no una garantía").

Un botón "Reservar mi lugar gratis" en **cada sección anterior al formulario**, todos con `href="#registro"` (el id de la sección del formulario). Con enlace a ancla dentro de un bloque de código no hace falta configurar nada en GHL. En móvil, una **barra fija inferior** con el mismo botón que se oculta cuando algún botón o el formulario está visible.

## Cosas que el usuario pidió quitar (no las repitas)
- Textos de relleno bajo el formulario ("Gratis. Ves tu enlace…") y la letra chica de "no es un resultado asegurado" junto a los escenarios (la aclaración se queda en el pie).
- Franja de cifras con marquesina: se movió a la sección de quién eres.
- Datos que no suman a la venta (por ejemplo el nombre de la agencia donde trabaja, si la gente iría a buscarlo).

## Código en 3 bloques (ver `assets/ejemplo-masterclass/`)
- **CSS**: todo con prefijo de clase propio (`.jda …`) para no chocar con los estilos de GHL. Variables CSS para la paleta. Mobile-first con dos saltos: ≥720 px y ≥1024 px. Reglas globales mínimas (`html{scroll-behavior:smooth}`, fondo del `body`).
- **HTML**: secciones semánticas, `id="registro"` en la sección del formulario, `data-cta` en cada botón de reserva, comentarios de sección.
- **Script**: barra fija móvil con `IntersectionObserver`, slider, y carga diferida de `form_embed.js`.

## Titular con foto del instructor
- Foto recortada sin fondo (PNG/WebP con transparencia) apoyada en el borde inferior del hero: `.hero.has-img{padding-bottom:0;overflow:hidden}`.
- En laptop, la foto debe quedar casi tan alta como el bloque de texto: `width: calc(100% + 100px)` con margen izquierdo negativo, y `calc(100% + 130px)` desde 1200 px. Cuida que los logos del recorte no pisen la cajita de fecha. Medir con `getBoundingClientRect`.
- No achiques la columna de texto para agrandar la foto: el titular pasa a 5 líneas y empeora.

## Sección de quién eres con slider
- Dos columnas en laptop (texto a la izquierda, slider a la derecha); una columna en móvil (texto, slider, botón). Con `display:grid` y `grid-template-areas:"text media" "cta media"`.
- Slider: marco fijo **4:5** para todas las fotos (verticales u horizontales; `object-fit:cover`, `object-position:50% 28%` para no cortar caras), `scroll-snap`, una foto por vez en laptop (`flex:0 0 100%`) y 88 % en móvil para dejar asomar la siguiente.
- Avance automático cada 4 s solo si está a la vista y nadie lo toca (pausa con `pointerdown`/`mouseenter`/`focusin`, reanuda 2,5 s después); respeta `prefers-reduced-motion`.
- Los puntos se crean con JS según el número de fotos: agregar una foto = copiar un `<figure class="slide">`.
- En laptop todas las cifras ("+USD 3.5M" y similares) en una sola línea: `white-space:nowrap` y tamaño ≈1.7rem.

## Pie de página
Pequeño. En laptop `padding:14px 16px`. En móvil deja ≈76 px abajo porque la barra fija ocupa el borde inferior.

## Qué NO inventar
Cifras de resultados, años de experiencia, clientes, nombres de empresas, testimonios, fotos, ni datos legales. Pregunta; si dos fuentes discrepan (dos cifras distintas para lo mismo), pregunta cuál vale. Si falta una foto, publica sin foto con un diseño que funcione sin ella, no con un cuadro amarillo de relleno.
