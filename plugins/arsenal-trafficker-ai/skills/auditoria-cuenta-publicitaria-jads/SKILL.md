---
name: auditoria-cuenta-publicitaria-jads
description: Auditoría de cuenta publicitaria de La Jungla de los Ads (metodología Capimario). Hace preguntas previas al trafficker, saca la data de los últimos 3 a 6 meses por MCP (Meta; TikTok y Google con sus diferencias), cruza la pauta con el pipeline comercial del CRM, ubica dónde se queda la plata y entrega un reporte HTML visual con resultados por mes, vista de campañas, conjuntos y anuncios, qué funciona y por qué, meta realista y plan de acción. Úsala siempre que el usuario diga "audita esta cuenta", "revisa la cuenta del cliente", "heredé una cuenta", "diagnóstico de la cuenta", "qué está mal en esta cuenta" o pida un reporte de auditoría, aunque no diga "auditoría". NO es para la revisión diaria o semanal de campañas activas (eso es optimizador-de-campanas-jads) ni para crear campañas (eso es creador-de-campanas-jads).
---

# Auditoría de cuenta publicitaria — JADS

Foto completa de una cuenta publicitaria: qué se ha hecho, cuánto costó, qué funcionó y, sobre todo, **dónde se está quedando la plata**. Termina en un **reporte HTML** que el trafficker puede revisar y compartir con su cliente.

Etiquetas: **[Universal]** aplica a cualquier nicho · **[Vertical]** cifra de un vertical concreto, no se cruza con otro · **[Confirmado]** validado en 3+ casos · **[Hipótesis]** observado, aún sin evidencia suficiente: dilo si lo usas.

## Principios
1. **Nunca un indicador solo.** Un CTR o un CPL aislado no dice nada; se contrasta con lo que pasa después en el funnel y en el pipeline comercial.
2. **La cuenta se audita contra sí misma**, no contra promedios del rubro.
3. **El volumen solo no es buen indicador** en leads y mensajería. Algunos clientes se quedan tranquilos con volumen ("de 1,000 leads algo sale") y se respeta, pero el trafficker tiene que saber qué pasa con esos leads.
4. **Todo termina en una acción replicable.**

## Paso 1 — Preguntas previas (siempre, antes de sacar data)
Hazlas en un solo mensaje:
1. **¿La cuenta ya viene haciendo campañas? ¿De forma continua o con pausas?**
2. **¿Cuánto invirtió en los últimos 3 meses?** Si la inversión fue poca para el tamaño del negocio, **amplía el análisis a los últimos 6 meses** para tener más data. Qué es "poco" queda a criterio del trafficker (1,000 soles puede ser mucho para un negocio y poco para otro).
3. **¿Cuál es el precio del producto o servicio?** Es el punto de partida para juzgar si el costo por resultado es sano. Si el trafficker no lo tiene, adviértele que sin ese dato el análisis pierde criterio y pídele que lo consiga.
4. **¿El cliente tiene una meta?** (cantidad de leads, mensajes o ventas al mes).
5. **¿El cliente prioriza volumen o calidad?**
6. **¿Hay CRM o registro de lo que pasa con los leads?** Pide un **export reducido de los últimos 3 meses**: solo **fecha del lead, campaña o fuente y estado** (no contesta, descalificado, interesado, compró), **sin nombres, teléfonos ni correos**. Así el cliente comparte con menos recelo y no se suben datos personales.
   - Si el cliente no comparte nada, la auditoría sigue, pero deja escrito que **sin esa data no se puede saber dónde se cae la venta** y que las conclusiones quedan limitadas.

## Paso 2 — Sacar la data por MCP
- **Meta:** usa el MCP de Meta Ads (solo lectura). Saca la data del periodo (3 o 6 meses) a nivel de **campaña, conjunto y anuncio**, separada **por mes**.
- **TikTok:** si hay un MCP de TikTok conectado, mismo criterio con sus nombres (campaña, grupo de anuncios, anuncio).
- **Google:** el MCP oficial de Google Ads es de solo lectura y sirve para auditar. Los criterios específicos de Google están pendientes de definir; por ahora, aplica la misma lógica y avisa al trafficker que esta parte se va a ampliar.
- **Si no hay MCP:** pide un export (CSV o Excel) con las mismas columnas o capturas, y avisa qué no se pudo verificar.
- **Miniaturas:** descarga la imagen o miniatura de cada anuncio y **guárdala dentro del reporte** (embebida en base64) para que no caduque. El enlace de vista previa de la plataforma va como extra, porque puede dejar de funcionar con el tiempo.

### Métricas por nivel
| Nivel | Métricas |
|---|---|
| **Campaña** | Nombre · objetivo · resultados (leads, mensajes o ventas) · costo por resultado · gasto |
| **Conjunto de anuncios** | Nombre · campaña de la que sale · resultados · costo por resultado · CPM · frecuencia · CPC · CTR único · impresiones · gasto |
| **Anuncio** | Miniatura (con vista previa) · nombre · resultados · costo por resultado · CTR único · CPC · impresiones. Si es video: reproducciones de 3 segundos y de 25%, 50%, 75% y 100% |

## Paso 3 — Análisis
### 3.1 Inventario de objetivos
Lista qué objetivos se han trabajado (leads con formulario nativo, leads con landing, WhatsApp, DM de Instagram, ventas de ecommerce, campañas de seguidores u otros), con el **gasto** y el **costo por resultado** de cada uno.

### 3.2 Salud del costo por resultado frente al ticket
Compara el costo por resultado con el precio del producto. Ejemplo: un lead de $300 para un servicio de $1,000 se come el 30% del precio, y es solo un lead, no un cliente → hay que optimizar. **No hay un porcentaje fijo:** el trafficker decide con criterio según el margen del negocio. El costo por mensaje suele ser la **primera alerta** de qué tan sana está la cuenta.

### 3.3 Comparación mes a mes
- Inversión vs. cantidad de resultados, mes a mes.
- **CTR único (porcentaje de clics en el enlace) mes a mes**, para ver cómo evolucionó en los 3–6 meses. Referencia: 1.5% aceptable, 1.5–3% sobre el promedio, más de 3% muy bueno (en high ticket puede aceptarse cerca de 1%, comparando varios anuncios).
- **Variaciones de inversión:** si un mes se invirtió mucho menos que otro, o hubo pausas, señálalo como hallazgo; cambia cómo se leen los resultados y afecta el aprendizaje de la plataforma.
- **Métricas de negocio:** tasa de conversión, costo de adquisición de cliente (CAC) y ROAS. La cuenta publicitaria muchas veces no las tiene (sobre todo en mensajería): pídelas al cliente o calcúlalas con el CRM. Si no existen, márcalo como hueco.
- **Ajusta antes de juzgar [Universal, Confirmado]:** país o ciudad, temporada (caro en Black Friday, Navidad y julio; barato de enero a marzo) y tipo de campaña.

### 3.4 Pipeline comercial: dónde se queda la plata
Con el export del CRM: de los leads o mensajes entregados, cuántos **no contestan**, cuántos están **descalificados**, cuántos **interesados** y cuántos **compraron**, en total y por campaña si se puede. Calcula el porcentaje de cada etapa y señala **dónde se detienen las oportunidades**:
- Muchos "no contesta" → velocidad o forma de atención comercial, o leads de baja intención.
- Muchos "descalificados" → el anuncio o el formulario no filtran (precio visible, preguntas filtro).
- Muchos "interesados" y pocas compras → proceso de cierre u oferta.

### 3.5 Tracking
Pixel o dataset y eventos bien puestos (por ejemplo, CompleteRegistration en la página de gracias, no en la landing), objetivo de campaña coherente con el objetivo del negocio. Si hay dudas serias, deriva al revisor de pixel cuando esté disponible.
- **[Universal, Hipótesis]** Fallos del método de pago pueden reiniciar el aprendizaje y disparar el costo sin que sea un problema creativo.
- **[Universal, Hipótesis]** Un campo con fricción nuevo en el formulario (por ejemplo, documento de identidad) subió el CPL un 10–25% en lo observado.

### 3.6 Estructura
Compárala con el sistema de la metodología: testeo con ABO y escalado con CBO; mínimo 2–3 conjuntos al testear; un ángulo por conjunto con mínimo 3 anuncios; una objeción por anuncio; anuncios de distintos niveles de consciencia; remarketing aparte y enfocado en cierre. Cada desvío es un hallazgo, que se evalúa contra los resultados.

### 3.7 Funnel
Ubica el cuello de botella: impresión → clic → lead, mensaje o compra → pipeline comercial → venta. Si el costo subió, sigue el orden de diagnóstico **[Universal, Confirmado]**: contexto → frecuencia (cerca de 5 en tráfico frío es saturación; en remarketing la frecuencia alta es normal) → recién después ángulo, copy u oferta.

### 3.8 Qué funciona y por qué
Toma los **3 anuncios con mejor costo por resultado** y los **3 con peor**, y compáralos en ángulo, formato, precio visible, hook y nivel de consciencia. Cierra con la regla que se repite en los ganadores ("si X, entonces Y") y la acción para llevarla a los débiles.

### 3.9 Meta realista (solo si el cliente tiene una meta)
- **Presupuesto ÷ costo por resultado actual = resultados posibles**, frente a la meta del cliente → ✅ alcanza / ❌ no alcanza.
- **Capacidad operativa:** indícale al trafficker que **le traslade al cliente la pregunta**: "¿tu equipo puede atender este volumen?".
- Si algo no cuadra, se dice de frente antes de proponer estrategia.

## Paso 4 — Reporte HTML
Genera el reporte con la plantilla `assets/plantilla-reporte.html`: copia la plantilla y **reemplaza solo el objeto `DATA`** con los datos reales (no toques el diseño ni el script), guarda el archivo (por ejemplo, `auditoria-[cuenta]-[DD-MM-AAAA].html`) y ábrelo en el navegador. Presentación limpia, con gráficos de barras, circulares y de tendencia. Secciones, en este orden:

1. **Resumen ejecutivo:** 5 líneas con el estado general, dónde se queda la plata, la mejor oportunidad, el riesgo principal y la primera acción.
2. **Indicadores clave:** inversión total, resultados, costo por resultado promedio, costo por resultado frente al ticket.
3. **Resultados por mes:** gráfico de inversión vs. resultados y tendencia del costo por resultado; nota sobre variaciones de inversión.
4. **Inversión por objetivo:** gráfico circular.
5. **Vista de campañas** (tabla).
6. **Vista de conjuntos de anuncios** (tabla).
7. **Vista de anuncios** (tabla con miniaturas y métricas de video).
8. **Pipeline comercial:** embudo o barras por etapa (si hay CRM; si no, el aviso de limitación).
9. **Tracking y estructura:** hallazgos.
10. **Qué funciona y por qué.**
11. **Meta realista** (si aplica).
12. **Plan de acción:** separado en **Crítico** (corregir ya), **Mejora** (puede esperar) y **Preferencia** (no justifica cambiar lo que funciona).
13. **Huecos de información y nivel de confianza** de cada conclusión.

Además del reporte:
- **Guarda la línea base** en `linea-base-[cliente].md`, en la carpeta del cliente, para que `optimizador-de-campanas-jads` parta de ahí: rango de costo por resultado aceptable por objetivo, benchmark por mes, CTR único de referencia, segmentaciones y anuncios ganadores, tasas de conversión de plataforma y de negocio, y estado del pipeline.
- Deja en el chat un bloque **"Para la siguiente skill"** con la ficha del negocio, el benchmark y el diagnóstico, en el formato de `CONTRATO.md`.

## Lo que esta skill NO hace
- No modifica la cuenta: solo lee.
- No hace la revisión diaria o semanal de campañas activas: eso es `optimizador-de-campanas-jads`.
- No crea campañas: eso es `creador-de-campanas-jads`.
- No define la estrategia completa: eso es `estratega-digital-anuncios-jads`.
