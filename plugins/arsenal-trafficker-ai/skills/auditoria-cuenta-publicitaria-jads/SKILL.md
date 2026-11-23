---
name: auditoria-cuenta-publicitaria-jads
description: Auditoría inicial de una cuenta publicitaria (Meta, TikTok o Google Ads) que el trafficker hereda o recibe de un cliente nuevo, con la metodología de Capimario (La Jungla de los Ads). Revisa contexto y benchmark, tracking, estructura de campañas, rendimiento a lo largo del funnel y qué está funcionando, y entrega un diagnóstico con plan de acción. Úsala siempre que el usuario diga "audita esta cuenta", "revisa la cuenta que me pasó el cliente", "qué está mal en esta cuenta", "heredé una cuenta", "diagnóstico inicial", o pegue un export, capturas o datos de una cuenta que todavía no gestiona, aunque no diga "auditoría". NO es para la revisión semanal de campañas que el trafficker ya gestiona (eso es revision-de-campanas-jads) ni para armar el plan de medios (eso es estratega-digital-anuncios-jads).
---

# Auditoría de cuenta publicitaria

Foto inicial de una cuenta que el trafficker todavía no gestiona. El objetivo no es listar todo lo que está mal: es encontrar **dónde está el cuello de botella real** y **qué ya funciona** para llevarlo a lo que no funciona.

Cada regla lleva dos etiquetas:
- **[Universal]** = mecanismo que aplica a cualquier nicho. **[Vertical]** = cifra o variante de un vertical concreto; nunca la cruces con otro vertical.
- **[Confirmado]** = validado en 3+ casos reales. **[Hipótesis]** = observado, pero aún sin evidencia suficiente: dilo explícitamente si lo usas.

## Principios (no negociables)

1. **Nunca evalúes un indicador solo [Universal, Confirmado].** Un CTR alto o bajo no dice nada por sí mismo. Contrástalo con lo que pasa después: leads, costo por lead, calidad del lead. Una campaña puede tener excelente entrada de tráfico y fallar en conversión; ese es el problema real, no el tráfico.
2. **La cuenta se audita contra sí misma [Universal, Confirmado].** No hay umbrales universales de CTR o CPL. El benchmark es el histórico propio de la cuenta.
3. **Busca el porqué cualitativo [Universal, Confirmado].** Si una campaña convierte mejor que otra, no lo reportes como dato aislado: pregunta qué es distinto ahí (ángulo, oferta, formato, segmento). Esa variable es el hallazgo.
4. **Todo termina en una acción replicable [Universal, Confirmado].** Si algo funciona en una campaña, la acción es llevarlo a las débiles.

## Antes de empezar: qué necesitas

Pide lo que falte, en un solo mensaje y sin bloquear el trabajo:
- **Datos de la cuenta:** acceso por el MCP de Meta Ads (u otra plataforma), un export (CSV/Excel) o capturas. Mínimo los últimos 30 días; ideal 90 días o más para tener histórico.
- **Ficha del negocio** (ver `CONTRATO.md` del repo): vertical, ticket, ubicación del público, objetivo (cantidad o calidad), presupuesto, capacidad operativa.
- **Qué pasa después del lead:** ¿cuántos leads responden, agendan, asisten o compran? Si el cliente no lo sabe, anótalo como **hueco crítico**: sin eso no se puede juzgar la calidad.

Si solo tienes capturas o datos parciales, audita igual y marca con claridad qué conclusiones quedan abiertas.

## Proceso (en este orden)

### Paso 1 — Contexto y benchmark
1. **Arma el benchmark con el histórico propio [Universal, Confirmado]:** costo por resultado + volumen, según el objetivo:
   - Lead gen → CPL + cantidad de leads
   - Mensajería → costo por mensaje + cantidad de conversaciones
   - Ventas → costo por compra + cantidad de compras
2. **Si la cuenta es nueva o no tiene histórico útil [Universal, Confirmado]:** usa proyectos similares como referencia aproximada. Nunca prometas resultados en X días.
3. **Ajusta el benchmark antes de diagnosticar [Universal, Confirmado].** Si el periodo que comparas no coincide en estas variables, ajusta el benchmark en lugar de declarar un fracaso:
   - **País o ciudad:** en Perú, provincias suelen costar más que Lima; en LatAm, Colombia, México, Ecuador y Argentina tienen costos parecidos entre sí.
   - **Temporada:** caro en Black Friday, Navidad y, en menor medida, julio; barato de enero a marzo.
   - **Tipo de campaña:** formulario nativo, landing, mensajería o remarketing no se comparan entre sí.
4. **Evaluación = "llegar o estar cerca" [Universal, Confirmado]** con criterio de contexto, no un número fijo.

Referencias de vertical (solo si no hay histórico, y solo en su vertical):
- **Real estate, Perú [Vertical, Confirmado]:** formulario nativo en Lima Moderna, tope de CPL de $2–4; resto de Lima, $6–8 (varía con el ticket). Landing, ~15–20% más caro que el formulario nativo (patrón, no regla). Mensajería en tráfico frío, $1–3, condicionado al ticket. Remarketing por mensajería, S/10–15 de piso y hasta S/45 visto en casos reales.
- El tope de CPL **solo se puede romper hacia arriba si la calidad del funnel lo sostiene** (responde → agenda → asiste) [Vertical, Confirmado].

### Paso 2 — Tracking y estado de la cuenta
Revisa lo básico antes de juzgar resultados; un problema aquí invalida todo lo demás:
- ¿El pixel o dataset y los eventos de conversión están instalados y disparan en el lugar correcto (por ejemplo, el evento de registro en la página de gracias, no en la landing)? Si hay dudas serias, deriva al revisor de pixel y GTM.
- ¿El objetivo de la campaña coincide con el objetivo comercial (leads vs. mensajes vs. ventas)?
- **Interrupciones de pago [Universal, Hipótesis]:** fallos de la tarjeta o del método de pago pueden reiniciar la fase de aprendizaje y explicar picos de costo por resultado sin que haya un problema creativo. Revisa el historial de facturación antes de culpar a los anuncios.
- **Campos del formulario [Universal, Hipótesis]:** agregar un campo con fricción (por ejemplo, documento de identidad) subió el CPL en un rango observado de 10–25% respecto al previo, con días puntuales mucho peores. El impacto fue menor en una cuenta con anuncios ya validados. Si el CPL saltó en una fecha concreta, revisa si cambió el formulario.

### Paso 3 — Estructura de campañas
Compara la estructura actual con el sistema de testeo de la metodología. Cada desvío es un hallazgo, no necesariamente un error: evalúalo contra los resultados.
- **Fase de testeo con ABO, escalamiento con CBO [Universal, Confirmado].** En testeo, presupuesto manual y equitativo entre conjuntos (condiciones iguales). CBO solo cuando ya hay un ángulo ganador validado. **Si la cuenta testea con CBO**, Meta concentra el gasto en uno o dos conjuntos y el resto nunca recibe una prueba justa: los "perdedores" pueden no haberse testeado de verdad [Universal, Hipótesis].
- **Un segmento = un ángulo [Universal, Confirmado]:** en fase cero, cada conjunto de anuncios trabaja un solo ángulo o territorio, con mínimo 3–5 anuncios por conjunto. Ángulos mezclados en el mismo conjunto impiden saber qué funcionó.
- **Un anuncio = una objeción [Universal, Confirmado]:** cada anuncio ataca una sola objeción del mercado, sea imagen, carrusel o video.
- **Distribución por nivel de consciencia en tráfico frío [Universal, Confirmado]:** de los anuncios de cada ángulo, la mayoría (~3 de 5) apunta a niveles altos (consciente del producto, muy consciente) y la minoría (~2 de 5) a niveles bajos (consciente del problema, inconsciente). Meta reimpacta a la misma persona, así que alternar niveles funciona como una secuencia narrativa.
- **Remarketing separado y enfocado en cierre [Universal, Confirmado]:** públicos con intención real (visitas, carrito abandonado, leads sin respuesta, conversaciones sin cerrar) solo con anuncios de niveles de consciencia 4–5, con más volumen de anuncios (5 o más) y contenido de cierre: beneficios concretos, diferenciadores, promociones y valor monetario.
- **Remarketing por "¿dónde está la plata?" [Universal, Confirmado]:** prioriza por señales de atención sostenida, poder adquisitivo e interés, no "todo el que alguna vez interactuó". En real estate, la señal es el CRM (leads medios o altos que agendaron visita y no asistieron; requiere ~1,000 personas como mínimo). En ecommerce, públicos de interacciones orgánicas masivas o eventos de intención.
- **Precio en el anuncio [Vertical real estate, Confirmado]:** el precio (total, cuota mensual o inicial) es siempre el mejor filtro de calidad del lead. Si la cuenta tiene mala calidad y no muestra precio, es un hallazgo fuerte. No es un filtro perfecto: filtra volumen y mejora la calidad promedio.

### Paso 4 — Rendimiento a lo largo del funnel
1. Ubica el cuello de botella en este recorrido: impresión → clic → lead, mensaje o compra → calificación → venta. No asumas que el problema está en la primera métrica que se ve mal.
2. **Si el costo por resultado está por encima del benchmark ajustado, sigue el orden de diagnóstico [Universal, Confirmado]:**
   - **a. Contexto:** ¿ya ajustaste por país, temporada y tipo de campaña (Paso 1)?
   - **b. Frecuencia:** en tráfico frío y lead gen, una frecuencia cercana a 5 indica audiencia saturada o mensaje quemado; la acción es refrescar creativos o ampliar el público antes de tocar el ángulo. **En remarketing, la frecuencia alta es esperada por diseño** (público pequeño) y no es señal de saturación: pasa directo a revisar calidad del público, oferta y mensaje.
   - **c. Solo si la frecuencia es normal en tráfico frío:** sospecha del ángulo, copy, oferta o público.
3. **Remarketing caro no es fracaso [Universal, Confirmado]:** puede costar 5–15 veces más que el tráfico frío porque es público precalificado.
4. **Cantidad vs. calidad [Universal, Confirmado]:** antes de interpretar un costo, confirma qué pidió el cliente. El mismo CPL se lee distinto según el objetivo.
5. **El ángulo mueve el costo directamente [Universal, Confirmado]:** un CPL bajo a veces se explica por el ángulo de venta, no por la optimización del público. No asumas que un buen costo es pauta bien optimizada sin revisar el ángulo.
6. **Señal de sobreintervención [Universal, Confirmado]:** si el historial de cambios muestra ediciones casi diarias, los conjuntos nunca salen de la fase de aprendizaje. La regla es revisar diario e intervenir cada 2–3 días.

### Paso 5 — Qué está funcionando y por qué
1. Ordena campañas, conjuntos y anuncios por costo por resultado **y** calidad posterior (no solo por costo).
2. Toma los 2–3 mejores y los 2–3 peores y compáralos en: ángulo o territorio, objeción atacada, nivel de consciencia, formato, presencia de precio, segmento.
3. Formula el hallazgo como regla accionable: "Si X, entonces Y". Por ejemplo: "Los anuncios que abren con el precio traen leads que agendan más; llevar el precio al inicio de los anuncios de los conjuntos débiles".
4. **Si un ángulo funciona, la respuesta es escalarlo [Universal, Confirmado]:** más formatos del mismo ángulo, más presupuesto, mejor comunicación. Nunca cambiar de ángulo por presión de la competencia.

### Paso 6 — Chequeo de realidad del objetivo
Si el cliente tiene una meta, revísala en dos ejes [Universal, Confirmado] y comunícalo antes de proponer estrategia:
- **Matemático:** ¿cuántos resultados permite el presupuesto con el costo esperado?
- **Operativo:** ¿el negocio puede atender ese volumen? (por ejemplo, 1,000 leads al mes exigen WhatsApp API y un equipo de respuesta).

Si falla cualquiera de los dos, se dice de frente. No se construye una campaña para un número que el cliente no podrá sostener.

## Formato de salida

Entrega el informe con estas secciones, en lenguaje claro y sin relleno:

1. **Resumen en 5 líneas:** estado general, cuello de botella principal, la mejor oportunidad, el riesgo más grave y la primera acción.
2. **Contexto y benchmark:** el benchmark usado y los ajustes aplicados.
3. **Tracking y estado:** qué está bien, qué está roto, qué no se pudo verificar.
4. **Estructura:** desvíos frente al sistema de testeo y su impacto probable.
5. **Funnel:** dónde se cae el resultado, con números.
6. **Qué funciona y por qué:** las reglas "si X, entonces Y" encontradas.
7. **Plan de acción** separado en:
   - **Crítico** (corregir ya, afecta el resultado)
   - **Mejora** (puede esperar)
   - **Preferencia** (no justifica cambiar algo que funciona)
8. **Huecos de información:** lo que falta para cerrar conclusiones.
9. **Para la siguiente skill:** ficha del negocio, benchmark y diagnóstico en el formato de `CONTRATO.md`, listos para la estratega.

Indica el nivel de confianza de cada conclusión (**Confirmado** o **Hipótesis**). Si los datos no alcanzan para sacar una conclusión confiable, dilo en lugar de inventarla.

## Lo que esta skill NO hace
- No arma el plan de medios ni define los ángulos nuevos: eso es `estratega-digital-anuncios-jads`.
- No hace la revisión semanal de campañas que ya gestionas: eso es `revision-de-campanas-jads`.
- No reporta la competencia: eso es `el-rastreador-jads`.
