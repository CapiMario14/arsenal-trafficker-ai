---
name: optimizador-de-campanas-jads
description: Optimizador de campañas de La Jungla de los Ads (metodología Capimario). Revisa campañas activas de venta (leads, mensajería o venta directa) en Meta, TikTok o Google, las analiza por capas (campaña, conjunto, anuncio) contra el plan de medios y la línea base de la auditoría, separa métricas de decisión de métricas de contexto y decide qué escalar, qué optimizar, qué apagar y qué no tocar; entrega un reporte HTML con semáforo y plan de acción. Úsala siempre que el usuario diga "optimiza mis campañas", "revisa cómo van las campañas", "subió el CPL", "¿apago este anuncio?", "¿escalo esta campaña?", "lee estas métricas", "análisis de métricas" o pegue datos de campañas activas, aunque no diga "optimizar". NO es para la auditoría inicial de una cuenta (eso es auditoria-cuenta-publicitaria-jads) ni para crear campañas (eso es creador-de-campanas-jads).
---

# Optimizador de campañas — JADS

Trabajo del día a día sobre campañas activas: leer los números por capas, encontrar dónde está el problema y decidir **qué escalar, qué optimizar, qué apagar y qué no tocar**. Aplica a **campañas de venta: leads, mensajería y venta directa**. Las campañas de posicionamiento quedan fuera por ahora.

Trabaja de la mano con:
- **`auditoria-cuenta-publicitaria-jads`**, que deja la **línea base** (benchmark, rango de costo por resultado aceptable, anuncios y segmentaciones ganadores, pipeline).
- **`estratega-digital-anuncios-jads`**, que deja el **plan de medios** (presupuesto y resultados proyectados).

## Regla 1 — El análisis es por capas, como una cebolla
- **Macro:** campaña · **Intermedio:** conjunto de anuncios · **Micro:** anuncios.
- **Nunca se toma una decisión solo con la capa macro.** Si la campaña muestra un CPL caro pero tiene anuncios baratos, no se apaga ni se cambia la campaña por ese número. Siempre se baja hasta los conjuntos y los anuncios, y la decisión sale de combinar las tres capas.

## Regla 2 — Métricas de decisión vs. métricas de contexto
**🎯 Métricas de decisión** (con estas se decide):
- **Resultados** (leads, mensajes, ventas) frente a lo proyectado en el plan de medios.
- **Costo por resultado** (CPL, costo por mensaje, costo por venta) frente al rango aceptable.
- **Ventas generadas por la campaña** (con CRM y UTMs).
- **CAC por canal** (Meta, TikTok, Google).
- **Valor de compra** (solo venta directa: ecommerce e infoproductos), comparado con el margen del producto cuando se conozca. Ejemplo: costo por venta $50 y valor de compra $1,000 no son $950 de ganancia: falta restar el costo del producto, el envío y las comisiones.
- **Tasa de conversión** en dos niveles:
  - **De plataforma:** formulario de Facebook (leads ÷ aperturas del formulario) mínimo **20%** · formulario web (leads ÷ visitas a la landing) mínimo **30%** · WhatsApp (conversaciones iniciadas ÷ clics en el enlace) mínimo **30–40%**.
  - **De negocio:** leads o mensajes que terminan en venta. Depende del negocio (en inmobiliario ronda el **1%**, a veces 0.5–0.8% [Vertical]). Se maneja con pinzas: nunca prometas una tasa que el negocio no ha demostrado.

**🔍 Métricas de contexto** (explican por qué pasa algo; **nunca deciden solas**):
| Métrica | Referencia | Qué indica si está mal |
|---|---|---|
| **CTR único (porcentaje de clics en el enlace)** | Mínimo **1.5%** aceptable · **1.5–3%** sobre el promedio · **más de 3%** muy bueno | El anuncio no atrae. Excepción: en high ticket o industrias difíciles puede aceptarse cerca de **1%**, pero solo después de comparar varios anuncios y el histórico de la cuenta, nunca por ser lo primero que se ve. |
| **Hook rate** (reproducciones de 3 s ÷ impresiones) | Mínimo **20%** | El hook está fallando. |
| **Frecuencia** | **1–5** aceptable · **más de 5** saturación | Saturación en tráfico frío: refrescar anuncios y sostener campañas TOFU baratas (seguidores, reproducciones de video, alcance). **En remarketing, la frecuencia alta es normal.** Si en el año completo da alta porque se usa siempre la segmentación que vende (mes a mes se ve en 2–3), es válido: ahí está la plata. |
| **Impresiones** (atadas al CPM) | Sin rango fijo: se compara con la evolución de la propia cuenta | Bajas por anuncio poco atractivo, audiencia muy chica (mínimo recomendado **300,000 personas**, con criterio en negocios locales) o presupuesto chico. Si el presupuesto es chico para un ticket muy alto, conviene abrir otros canales (por ejemplo, TikTok). |
| **CPM** | Mientras más bajo, mejor | Sube con impresiones bajas, anuncios malos o presupuesto chico. **La solución siempre pasa por optimizar anuncios.** |
| **CPC** | Mientras más bajo, mejor | Si se encarece: revisar qué tan fácil es hacer clic y entrar a la landing. |
| **Clics únicos en el enlace vs. visitas a la página de destino** | Cerca, **±10%** aproximadamente | Visitas muy por debajo: se pierde gente antes de que cargue (velocidad, enlace, pixel de visita). Visitas muy por encima: posible problema de medición (pixel duplicado). |
| **ROAS** | Que sea sano para el negocio | Que retorne dinero no significa que sea un ROAS sano; se lee junto con el margen. |

## Regla 3 — El costo por resultado se maneja en rangos
El costo por resultado depende del país, la ciudad, el mes y el tipo de campaña: normalmente **mensajes es lo más barato, leads intermedio y ventas lo más caro**, y fin de año es más caro, aunque se sigue invirtiendo. El punto de partida es **cuánto está dispuesto a pagar el negocio por un lead o una venta de calidad**, siempre como **rango**, nunca como precio fijo. Si la línea base o el plan de medios no trae ese rango, pídeselo al trafficker antes de juzgar.

## Antes de empezar
1. **Busca la línea base** (`linea-base-[cliente].md`, que deja la auditoría) y el **plan de medios**. Si no existen, avisa: lo ideal es correr primero la auditoría. Si el trafficker quiere seguir igual, arma una línea base rápida con los últimos 30–90 días y pide el rango de costo por resultado aceptable.
2. **Saca la data por MCP** (Meta; TikTok o Google si están conectados) a nivel de campaña, conjunto y anuncio. Si no hay MCP, pide un export o capturas.
3. **Pide la data comercial:** export reducido del CRM (fecha, campaña o fuente, estado), **sin datos personales**. Para cruzar ventas con campañas, verifica que los enlaces usen **UTMs**:
   - `utm_source` (meta, tiktok, google) · `utm_medium` (paid) · `utm_campaign` (nombre de la campaña) · `utm_term` (segmentación) · `utm_content` (anuncio).
   - En Meta se pueden poner con parámetros dinámicos, por ejemplo: `utm_source=meta&utm_medium=paid&utm_campaign={{campaign.name}}&utm_term={{adset.name}}&utm_content={{ad.name}}`.
   - Si no hay UTMs, recomiéndalos como acción crítica: sin ellos no se sabe qué campaña vende.
4. **Ventas por campaña y CAC:** de preferencia con los **últimos 3 meses**, para tener más data.
5. **Pregunta qué cambios se hicieron** en los últimos días (anuncios nuevos, presupuesto, formulario, segmentación).

## Proceso de decisión
### Paso 1 — Resultados frente al plan de medios
Compara los resultados con lo proyectado. Ejemplo: presupuesto de $1,000 con un CPL proyectado de $2 = **500 leads esperados**. Si no se llegó, se investiga por qué en los pasos siguientes. Aplica a leads, mensajes y ventas.

### Paso 2 — Baja por las capas con las métricas de decisión
Para cada **anuncio**, luego cada **conjunto** y al final cada **campaña**, ubica su costo por resultado y sus resultados frente al rango aceptable:
- 🟢 Dentro o por debajo del rango, con resultados.
- 🟡 Por encima del rango pero con calidad que lo justifica, o con pocos días de data.
- 🔴 Por encima del rango sin calidad que lo sostenga.

### Paso 3 — Usa las métricas de contexto para encontrar la causa
Para cada 🟡 o 🔴, revisa en este orden:
1. **Contexto:** país, temporada, tipo de campaña, cambios recientes, problemas de pago.
2. **Frecuencia:** más de 5 en tráfico frío = saturación → refrescar anuncios o ampliar la audiencia antes de tocar el ángulo. En remarketing no aplica.
3. **Anuncio:** CTR único bajo 1.5% (salvo la excepción de high ticket) o hook rate bajo 20% → el creativo o el hook fallan.
4. **Entrega:** impresiones bajas y CPM alto → audiencia chica, anuncio débil o presupuesto chico.
5. **Después del clic:** CPC alto, clics vs. visitas alejados, o tasa de conversión de plataforma bajo su mínimo → landing, formulario o flujo de WhatsApp.
6. **Después del lead:** tasa de conversión de negocio baja con costo por resultado sano → el problema está en **ventas** (tiempo de respuesta, seguimiento, cierre), no en la pauta. Mejorar el CAC es trabajo de anuncios **y** de ventas.

### Paso 4 — Decide
| Decisión | Cuándo |
|---|---|
| **🚀 Escalar** | Anuncio o conjunto 🟢 de forma sostenida, con calidad comprobada en el pipeline o en ventas. Se escala **más formatos del mismo ángulo, más presupuesto y mejor comunicación**. Para pasar a CBO con contenido dinámico hacen falta segmentaciones y anuncios validados con data de ventas (ver `creador-de-campanas-jads`). |
| **🔧 Optimizar** | 🟡 o 🔴 con una causa identificada en el Paso 3. Se cambia **una sola variable** (hook, creativo, formato, audiencia, formulario o landing) para saber qué funcionó. |
| **⛔ Apagar** | 🔴 sostenido que ya se optimizó y no mejoró, sobre todo si en el mismo conjunto hay anuncios 🟢 que pueden recibir ese presupuesto. **No hay un umbral fijo de gasto o de días**: se decide con contexto. |
| **⏸️ No tocar** | 🟢 estable; o recién editado (menos de 2–3 días); o en fase de aprendizaje. |

Reglas que siempre se respetan:
- **Revisar a diario, intervenir cada 2–3 días.** Cada cambio reinicia el aprendizaje; tocar a diario hace más daño que el problema original.
- **Nunca decidir solo con la capa macro** (Regla 1).
- **Nunca apagar por una métrica de contexto** si el costo por resultado y los resultados están bien.
- **No apagar la cuenta en temporada cara** esperando que baje el costo: reactivar desde cero cuesta más.
- **Si un ángulo funciona, se escala; no se cambia por presión de la competencia.**

## Entregable
Pregúntale al trafficker si quiere el **reporte HTML** (por defecto, sí). Genéralo con `assets/plantilla-optimizacion.html`: copia la plantilla, **reemplaza solo el objeto `DATA`** con los datos reales, guárdalo como `optimizacion-[cuenta]-[DD-MM-AAAA].html` y ábrelo en el navegador. Incluye:
1. Resumen en 3 líneas: cómo va, el problema principal y la acción más importante.
2. Resultados frente al plan de medios.
3. Semáforo por campaña, conjunto y anuncio, con métricas de decisión y de contexto.
4. Diagnóstico de cada 🟡 y 🔴 con su causa.
5. Decisiones (escalar, optimizar, apagar, no tocar), con el **cuándo**.
6. Pipeline comercial y ventas por campaña (si hay CRM).
7. Próxima revisión: fecha sugerida y qué mirar primero.

Al final, **actualiza la línea base** (`linea-base-[cliente].md`) si algo se validó: un anuncio ganador nuevo, una segmentación que vende o un rango de costo que cambió.

## Lo que esta skill NO hace
- No modifica las campañas por su cuenta: propone las decisiones y el trafficker las ejecuta.
- No hace la auditoría inicial: eso es `auditoria-cuenta-publicitaria-jads`.
- No crea campañas nuevas: eso es `creador-de-campanas-jads`.
- No optimiza campañas de posicionamiento (por ahora).
