---
name: el-rastreador-jads
description: El Rastreador, la skill de investigación de mercado y de competencia para pauta paga (metodología CIF de Capimario). Úsala siempre que el usuario pida un benchmark, un CIF, analizar qué comunica el mercado o la competencia, detectar saturación de mensajes, encontrar territorios creativos o ángulos de venta no explotados, definir objeciones y deseos del cliente, o preparar la Fase 2 de una estrategia de anuncios, aunque no use la palabra "CIF". Requiere Apify y Supadata conectados. Parte de anuncios scrapeados de las bibliotecas de anuncios (Meta, TikTok, Google) vía Apify y videos transcritos vía Supadata y entrega hallazgos con datos, territorios creativos priorizados y objeciones por anuncio. NO evalúa si un anuncio propio funciona (eso es análisis de anuncios) ni arma el plan de medios (eso es el estratega).
---

# El Rastreador: investigación de mercado y competencia (CIF)

Skill de La Jungla de los Ads. Lee las huellas que dejan los anuncios para saber qué comunica el mercado y por dónde no ha pasado nadie.

Fase 2 del framework: Onboarding → **Investigación de mercado** → Aterrizaje de estrategia.
Entrega al Estratega los territorios y las objeciones que necesita para el plan de medios.

## Dos módulos

1. **Módulo Competencia (CIF)**: qué comunica hoy el mercado, qué está saturado, qué no dice nadie. Lee `references/cif-competencia.md`.
2. **Módulo Cliente**: deseos, motivadores, problemas internos/externos y objeciones. Sale de la voz del cliente, no de la competencia. Lee `references/modulo-cliente.md`.

El CIF da territorios macro. El Módulo Cliente da las objeciones micro (una por anuncio). Si el usuario solo pide uno, ejecuta ese y avisa qué falta del otro.

## Reglas de método (no negociables)

1. **Las categorías salen del conteo, nunca se heredan.** Extrae hooks y copies, agrúpalos por tema con el vocabulario del nicho, cuenta y propón las categorías. Confírmalas con el usuario antes de analizar. "Ubicación", "exclusividad" o "diseño" solo entran si salen del conteo. En ecommerce o infoproductos aparecerán otras (precio, prueba social, garantía, transformación, etc.).
2. **Cada categoría lleva definición operativa** (qué entra y qué no), para que el mismo anuncio no se clasifique distinto.
3. **La dominancia es relativa a la muestra.** Un mensaje puede dominar en un set competitivo y estar ausente en otro (ej. lifestyle domina en Proyecto C y Proyecto B, y casi no aparece en Proyecto A). Nunca importes conclusiones de un CIF previo.
4. **Hallazgo válido = cita N o % de anuncios.** Sin número es observación, no hallazgo. Si dos proyectos comparten mercado, los hallazgos pueden parecerse, pero se re-derivan con el dato propio de cada muestra. Prohibido copiar y pegar hallazgos de otro CIF.
5. **La pregunta 2 del objetivo es "¿Qué está comunicando hoy el mercado?"**, no "¿qué está funcionando?". La Biblioteca de Anuncios no da métricas de rendimiento. Las cuatro preguntas del objetivo: qué está haciendo el mercado, qué está comunicando hoy, qué oportunidades existen, qué podemos adaptar al proyecto.
6. **Fecha de inicio = señal débil de sostenimiento, nunca prueba de rendimiento.** Un anuncio activo mucho tiempo puede ser descuido. Repórtalo como "indicio" y cruza con variantes del mismo anuncio o reinversión en creativos similares.
7. **Saturado no es lo mismo que prohibido.** Un atributo saturado no abre el anuncio con la fórmula del mercado ("Vive en X", "a pasos de…"). Puede seguir siendo territorio si el ángulo cambia de **declarar** el atributo a **mostrar la vida que ocurre alrededor**. Esa diferencia debe verse en la ejecución del anuncio, no solo en el nombre del territorio. Si no, entra solo como prueba o filtro (ej. precio en la última slide).
8. **Prueba de diferenciación.** Si el titular de un territorio lo diría cualquiera de los 3 competidores top sin cambios, se descarta.
9. **Territorios sin porcentaje.** Se entregan ordenados por prioridad. En la fase de testeo el presupuesto es equitativo (ABO manual, 3-5 anuncios por territorio, un segmento = un ángulo). Los % de reparto solo existen en el plan de escalamiento, con datos reales del test.
10. **Control de solapamiento.** Si dos territorios dicen casi lo mismo (mismo titular, copy base o motivación), la skill los une (mejores conceptos como variantes micro) o avisa a quien investiga qué los hace parecidos y deja la decisión. Nunca entrega en silencio dos territorios incomparables. Si se mantienen separados, pide qué los diferencia en la ejecución.
11. **Los territorios son hipótesis.** Los valida el ABO. No se presentan como conclusiones.
12. **Territorio válido** = nace de un hueco del dataset + se conecta a una motivación del Módulo Cliente + es mutuamente excluyente de los otros.

## Requisitos obligatorios: Apify y Supadata

Esta skill **no corre sin estas dos herramientas conectadas**. Sin ellas la investigación queda a medias y no es confiable.

- **Apify**: scrapeo total de las bibliotecas de anuncios (Meta Ads Library, biblioteca de anuncios de TikTok y Google). Es obligatorio invocarlo para el universo analizado.
- **Supadata**: transcripción de los anuncios en video (hooks verbales, promesa, CTA hablado). Es obligatorio invocarlo para todo anuncio en video de la muestra.

**Paso 0, antes de cualquier análisis:** verifica que ambas estén disponibles (con tool_search si están diferidas). Si falta alguna:
1. **Detente.** No improvises un scrapeo manual ni un análisis con ejemplos pegados a mano.
2. Avisa al usuario con este mensaje, adaptado: "Para esta investigación necesito Apify (scrapeo de bibliotecas de anuncios) y Supadata (transcripción de videos) conectados. Sin ellos la investigación saldría incompleta. Conéctalos en Configuración > Conectores y vuelve a pedírmelo."
3. Retoma solo cuando estén conectadas.

Detalle de uso en `references/herramientas.md`.

## Flujo

0. **Verificar Apify y Supadata** (sección anterior). Sin ambas, no se avanza.
1. **Objetivo y proyecto**: nombre exacto del proyecto, vertical, ticket, ubicación.
2. **Universo**: scrapeo con **Apify** sobre las bibliotecas de anuncios que apliquen (Meta, TikTok, Google); transcripción de videos con **Supadata**. Reporta N anuncios, N copies, N CTA/destinos, N proyectos nacionales e internacionales. Piso observado en casos reales: ~100 anuncios y 8 proyectos; máximo ~300 anuncios y ~20 proyectos. Es referencia, no umbral. Si la muestra es menor, dilo. Valida manualmente los hallazgos.
3. **Categorías**: propón, confirma, define (reglas 1 y 2).
4. **Análisis**: ejecuta los bloques de `references/cif-competencia.md`.
5. **Territorios y conceptos**: reglas 7 a 12.
5b. **Opcional**: ganchos, líneas de copy y orientación de formato como primer paso (bloque 14). Es investigación, no propuesta creativa completa; ofrécelo, no lo impongas.
6. **Control de calidad** antes de entregar: `references/control-calidad.md`.

## Alcance por vertical

Reglas 1 a 12 son de método y probablemente viajan a ecommerce e infoproductos, pero **es hipótesis**: solo están validadas en real estate premium Lima. Lo específico de real estate (captación, CTA, ticket alto) está marcado en `references/cif-competencia.md` y no se hereda a otros verticales.

## Fronteras con otras skills

- **Análisis de anuncios**: evalúa creativos propios o del cliente (¿este anuncio funciona?). Esta skill analiza anuncios ajenos a nivel de mercado (¿qué patrón domina y qué falta?).
- **Estratega de anuncios**: no reinventa esta fase. Recibe de aquí territorios priorizados y objeciones para armar el plan de medios.
