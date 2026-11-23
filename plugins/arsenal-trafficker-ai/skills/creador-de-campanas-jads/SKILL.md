---
name: creador-de-campanas-jads
description: Creador de Campañas de La Jungla de los Ads (metodología Capimario). Guía al trafficker para elegir el objetivo publicitario correcto, definir la estructura (testeo con ABO o escalado con CBO), las segmentaciones, el presupuesto y los anuncios, y monta la campaña por MCP dejándola en pausa para que el trafficker la revise y la active. La estructura aplica a cualquier canal digital (Meta, TikTok, Google); la implementación por MCP es en Meta Ads. Úsala siempre que el usuario quiera crear, armar, montar, subir o lanzar una campaña de Meta (Facebook/Instagram), TikTok o Google, definir la estructura de una campaña nueva, testear ángulos o segmentaciones, o escalar campañas, aunque no diga "skill" ni "campaña". NO evalúa campañas ya activas (eso es optimizador-de-campanas-jads) ni define la estrategia completa de un cliente (eso es estratega-digital-anuncios-jads).
---

# Creador de Campañas — JADS

Monta campañas de Meta Ads con criterio: primero el objetivo correcto, después la estructura, la segmentación, el presupuesto y los anuncios, y al final la implementación por MCP **en pausa**. La consigna de fondo: **la data manda**. Sin data, se testea; con data, se escala.

## Canales
**La estructura de esta skill aplica a cualquier canal digital: Meta, TikTok o Google.** La lógica es la misma (objetivo correcto, testeo antes que escalado, 2–3 segmentaciones o ángulos, mínimo 3 anuncios, presupuesto mínimo por grupo, nomenclatura, resumen antes de implementar). Lo que varía un poco es el nivel de anuncios y los nombres de cada plataforma:
- **Meta:** campaña → conjunto de anuncios → anuncio. Implementación por MCP, en pausa.
- **TikTok:** campaña → grupo de anuncios → anuncio. El presupuesto por grupo equivale al ABO y la optimización del presupuesto de campaña al CBO. Usa los objetivos equivalentes de TikTok y sus formatos (video vertical).
- **Google:** campaña → grupo de anuncios → anuncio. En Google el presupuesto vive en la campaña, no en el grupo; para testear con presupuesto controlado por segmentación, cada segmentación va en su propia campaña. Los anuncios cambian de forma (títulos y descripciones de búsqueda, recursos de Performance Max o YouTube).
- **Si el canal no es Meta y no hay un MCP conectado para ese canal:** la skill entrega el plan completo, con nomenclatura y resumen, para que el trafficker lo monte a mano.

## Regla de oro
Nunca armes una campaña "desde cero" solo porque te la piden. Antes necesitas saber **qué quiere conseguir el negocio** y **qué historial tiene la cuenta**. Si el trafficker no tiene claro el objetivo publicitario, **lo guías obligatoriamente hasta que lo tenga 100% claro**. No avanzas al siguiente paso sin eso.

## Paso 0 — Verificar el MCP de Meta
Antes de pedir cualquier dato, comprueba que el MCP de Meta Ads esté conectado, por ejemplo listando las cuentas publicitarias disponibles.
- **Si está conectado:** confirma con el trafficker en qué cuenta publicitaria se va a trabajar.
- **Si no está conectado:** explícale cómo conectarlo con `references/conectar-mcp-meta.md` y espera a que lo haga. Sin MCP no se implementa nada. Puedes adelantar la planificación (pasos 1 a 6) si el trafficker lo pide.

## Paso 1 — Objetivo del negocio → objetivo de campaña
Pregunta qué quiere conseguir el negocio y recomienda el objetivo publicitario correcto. Usa esta tabla:

| Objetivo del negocio | Objetivo de campaña recomendado | Requisitos que debes verificar |
|---|---|---|
| **Posicionamiento de marca** | Alcance (con frecuencia de ~5 impresiones al día por conjunto) · Tráfico al perfil de Instagram · Interacción con la publicación o reproducciones de video · Interacciones con la página de Facebook (para ganar seguidores) | — |
| **Ventas por mensajes** | Interacción → mensajes a **WhatsApp** o **DM de Instagram** | WhatsApp Business conectado a la página (si es WhatsApp). Messenger no se recomienda. |
| **Leads con formulario nativo** | Clientes potenciales → formulario instantáneo de Meta | 2–3 preguntas filtro, según lo que el área de ventas necesita para considerar calificado a un lead. |
| **Leads con landing page** | Clientes potenciales → sitio web | Pixel instalado con el evento **CompleteRegistration** disparando en la **página de gracias** (no en la landing). La landing debe tener página de gracias. |
| **Venta directa online** | Ventas | Solo para **ecommerce o infoproductos** (tienda virtual, Hotmart, Skool u otra plataforma donde la compra ocurre en la web). **No** para servicios. |

Errores que debes frenar siempre:
- **Campaña de tráfico con un link a WhatsApp:** no sirve para conseguir mensajes. Corrígelo a Interacción → mensajes.
- **Campaña de ventas para un servicio:** el servicio no se compra dentro de la web; usa leads o mensajes.
- **Leads con landing sin pixel o sin página de gracias:** no se lanza hasta tenerlo.

## Paso 2 — Testeo o escalado
Pregunta qué historial tiene la cuenta y decide:

### Escalado (CBO) — solo con data
Solo se escala si el trafficker sabe, con la data de ventas acumulada de los **últimos 3 o 6 meses**:
1. **qué segmentaciones le han traído ventas**, y
2. **qué anuncios le han traído ventas** (y en qué formatos).

Si no tiene claras esas dos cosas, **no se escala**, aunque insista. Explícale que la data manda y que primero tiene que testear segmentaciones y ángulos. Vuelve a proponer una estructura de testeo.

Estructura de escalado:
- Campaña con **CBO** (presupuesto a nivel de campaña).
- La **misma segmentación** que históricamente dio ventas.
- Los **anuncios que históricamente dieron ventas**, en los formatos que mejor le funcionaron.
- Recomienda trabajar con **contenido dinámico** (creativo dinámico) usando los anuncios ganadores.

### Testeo (ABO) — siempre para empezar
Todo lo que no es escalado se testea, y el testeo **siempre** va con **ABO** (presupuesto por conjunto). Elige la variante según el caso:

**A. Cuenta nueva o sin segmentación validada → testear segmentaciones**
- **Mínimo 2–3 conjuntos**, cada uno con una **segmentación distinta** que tú propones (ver Paso 3). Nunca un solo conjunto.
- Cada conjunto lleva **los mismos anuncios**: mínimo **3 anuncios** que cubran los **2–3 ángulos de venta** del inicio. Así lo único que cambia entre conjuntos es la segmentación, y al final se sabe qué público funcionó y qué ángulo funcionó dentro de cada uno.

**B. Ya tiene una segmentación que da ventas → testear ángulos dentro de ella**
- Pregunta: "¿Qué segmentaciones te están dando ventas actualmente?"
- Replica esa segmentación en varios conjuntos. **Cada conjunto = un ángulo de venta**, con **mínimo 3 anuncios del mismo ángulo**.
- Ejemplo: segmentación abierta en los distritos de mayor poder adquisitivo de una ciudad → conjunto 1 con 3 anuncios del ángulo "precio por cuota"; conjunto 2, misma segmentación, con 3 anuncios del ángulo "ubicación y estilo de vida".
- Esta es la única excepción a "mínimo 2–3 segmentaciones": la segmentación validada se repite.

**C. Validar ángulos rápido → un anuncio por conjunto**
- Solo cuando el objetivo explícito es **validar ángulos de venta**.
- **Misma segmentación** en todos los conjuntos; **un anuncio por conjunto**, cada uno con un **ángulo distinto**.
- **Mismo formato en todos** (todos video, o todos imagen, o todos carrusel), para que lo que cambie sea solo el ángulo.
- Presupuesto de **$3–5 diarios por ángulo** (o su equivalente en soles al tipo de cambio del día), para salir rápido de la fase de aprendizaje.

## Paso 3 — Segmentaciones
Propón segmentaciones según el producto o servicio y el historial de la cuenta:
- **Abierta (broad):** solo **ubicación, edad y género**. Aquí **el anuncio hace el trabajo de segmentar**, así que cada anuncio debe tener claros su **ángulo de venta, formato y nivel de consciencia** antes de crearlo. Si falta alguno, no avances.
- **Por intereses:** intereses relacionados con el producto, el problema que resuelve o el perfil del comprador.
- **Personalizada:** públicos propios de la cuenta (interacciones, visitantes, listas de clientes).
- **Lookalike (también llamado LAL o públicos/segmentos similares):** si la cuenta tiene historial, pídelo para no empezar de cero.
  - **Lookalike de compradores:** entre **1% y 3%**.
  - **Lookalike para alimentar la parte alta del funnel (TOFU):** de **4% en adelante**.

## Paso 4 — Presupuesto
- **Recomendado:** **20 soles diarios por conjunto** (o su equivalente en la moneda del trafficker).
- **Mínimo absoluto:** **10 soles diarios por conjunto.** Menos que eso no se acepta: dilo y propone reducir conjuntos en lugar de bajar el presupuesto por conjunto.
- **Validación de ángulos (variante C):** $3–5 diarios por ángulo.
- **Haz la cuenta antes de armar:** presupuesto diario total ÷ conjuntos (o ángulos). Si no alcanza, **reduce la cantidad de conjuntos o ángulos**; nunca repartas de menos. Ejemplo: 10 anuncios con 10 soles diarios en total no se acepta.
- Para empezar, una cuenta debería testear **2–3 ángulos de venta**.

## Paso 5 — Anuncios
Para cada anuncio, el trafficker debe tener claros:
- **Ángulo de venta** al que apunta.
- **Nivel de consciencia** del público al que habla.
- **Formato** (video, imagen o carrusel), consistente dentro de cada ángulo.

Material mínimo que **el trafficker entrega** (la skill no lo inventa):
- **Por cada anuncio: 3 copies (texto principal), 3 títulos y 3 descripciones.** Pueden repetirse entre anuncios.
- Los **videos o imágenes** de cada anuncio.
- El **destino**: número de WhatsApp, cuenta de Instagram, formulario (con sus 2–3 preguntas filtro) o URL de la landing.

Si falta algo, pídelo antes de implementar. Si el trafficker necesita escribir los copies o guiones, deriva a la skill de guionización de anuncios cuando esté disponible.

## Paso 6 — Resumen antes de implementar
Muestra el plan completo y pide confirmación:

```
CAMPAÑA: [nombre con la nomenclatura] · Objetivo: [objetivo] · [ABO testeo / CBO escalado]
Presupuesto: [S/ o $ por conjunto/campaña] · Total diario: [monto]
Seg. [tipo] · [presupuesto] · Anuncios: [Ads1 Formato AV# NC# H# ...]
Leyenda: AV1 = [ángulo], AV2 = [ángulo] · H1 = [hook], H2 = [hook]
Seg. [tipo] · ...
Destino: [WhatsApp / IG DM / formulario / landing]
Requisitos verificados: [pixel + CompleteRegistration en gracias / WhatsApp Business / preguntas filtro]
```

### Nomenclatura obligatoria
Usa siempre esta nomenclatura, para que cualquier persona entienda qué se está probando con solo leer el nombre:

**Campaña:** `Fecha de creación + Objetivo publicitario + Producto o servicio + ABO/CBO`
- Ejemplo: `22-11-2026 Leads Formulario Depas Surco ABO`

**Conjunto de anuncios (segmentación):** `Seg. + palabra que describe la segmentación`
- Ejemplos: `Seg. Abierto` · `Seg. Profesiones` · `Seg. Personalizado` · `Seg. Similar del 1% al 3%`

**Anuncio:** `Ads# + Formato + AV# + NC# + H#`
- **Ads#:** número del anuncio en orden de publicación (Ads1, Ads2, Ads3… según la cantidad de anuncios).
- **Formato:** Video, Imagen, Carrusel, o el que el trafficker considere.
- **AV#:** ángulo de venta (AV1, AV2, AV3… según cuántos ángulos eligió el trafficker).
- **NC#:** nivel de consciencia: **1 = bajo, 2 = medio, 3 = alto**. Equivalencia con los 5 niveles de Schwartz que usa la estratega: **NC1** = inconsciente o consciente del problema · **NC2** = consciente de la solución · **NC3** = consciente del producto o muy consciente (el remarketing "niveles 4–5" de la estratega es NC3 aquí).
- **H#:** hook o gancho (H1, H2… según cuántos hooks esté probando).
- Ejemplo: `Ads1 Video AV1 NC3 H1` · `Ads2 Video AV1 NC1 H2` · `Ads3 Imagen AV2 NC3 H1`

Antes de implementar, confirma con el trafficker qué ángulo corresponde a cada AV y qué hook a cada H, y déjalo anotado en el resumen para que la nomenclatura tenga sentido después.

## Paso 7 — Implementar por MCP (en pausa)
Con la confirmación del trafficker:
1. Sube las imágenes y videos con las herramientas de carga de medios del MCP.
2. Crea la campaña, los conjuntos, los creativos y los anuncios con el MCP de Meta, **todo en estado pausado** (`PAUSED`).
3. **Nunca actives nada.** La skill no publica ni gasta presupuesto.
4. Al terminar, dile al trafficker:
   - Qué se creó, con nombres y IDs.
   - Que en el Administrador de Anuncios lo verá como **pausado** (por la API no existe la pestaña de borradores; pausado cumple la misma función: no gasta nada).
   - Qué revisar antes de activar: segmentación, presupuesto, textos, medios, destino, pixel y evento.
   - Que la activación la hace **él mismo**, desde el Administrador de Anuncios.

Si alguna llamada del MCP falla, explica el error en lenguaje simple y qué hacer; no repitas a ciegas.

## Lo que esta skill NO hace
- No activa campañas ni gasta presupuesto.
- No inventa copies, títulos, descripciones ni creativos: los entrega el trafficker.
- No evalúa campañas activas: eso es `optimizador-de-campanas-jads`.
- No define la estrategia completa del cliente: eso es `estratega-digital-anuncios-jads`.
