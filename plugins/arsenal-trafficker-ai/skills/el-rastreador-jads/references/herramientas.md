# Herramientas obligatorias

## Apify (scrapeo de bibliotecas de anuncios)

Plataformas: Meta Ads Library, biblioteca de anuncios de TikTok, biblioteca de Google.

Procedimiento
1. Con `search-actors`, busca el Actor adecuado para cada biblioteca. No asumas nombres de Actors de memoria.
2. Verifica con `fetch-actor-details` qué entrada acepta y qué campos devuelve.
3. Ejecuta con `call-actor` y recupera resultados con `get-actor-run` y `get-dataset-items`.
4. Pide al menos: texto del anuncio (copy), título, CTA, URL de destino, formato, fecha de inicio, estado activo, anunciante y enlace al creativo.
5. Si no existe Actor utilizable para una biblioteca, dilo al usuario y no la incluyas en el universo. No inventes datos ni sustituyas con ejemplos manuales.

Registra para el bloque 2 (Universo): N anuncios, N copies, N CTA/destinos, N proyectos nacionales e internacionales y qué bibliotecas se usaron.

La fecha de inicio y el estado activo son indicios débiles de sostenimiento, no rendimiento (regla 6).

## Supadata (transcripción de videos)

1. Del dataset de Apify, separa los anuncios en video y toma su URL.
2. Usa `supadata_transcript` y, si el trabajo es asíncrono, `supadata_check_transcript_status` hasta obtener el resultado. `supadata_metadata` si necesitas datos del medio.
3. Analiza el hook verbal (primeros segundos), la promesa y el CTA hablado, y súmalos al conteo de categorías junto con los copies.
4. Si un video no se puede transcribir, repórtalo con su N y no lo cuentes como analizado.

## Si falla una herramienta a mitad de la investigación
Informa qué falló y qué parte de la muestra quedó fuera. No entregues el CIF como completo si el universo quedó recortado sin decirlo.
