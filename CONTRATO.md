# Contrato entre skills — Arsenal Trafficker AI

Este documento fija qué recibe y qué entrega cada skill del arsenal, para que el trabajo pase de una a otra sin rehacer nada. Cada skill nueva tiene que respetarlo. Si una skill cambia lo que entrega, se actualiza aquí primero.

## El flujo de punta a punta

```
DIAGNÓSTICO                      ESTRATEGIA                         EJECUCIÓN
Auditoría de negocio ─┐
Auditoría de cuenta  ─┼─► Estratega Digital de Anuncios ─► Changuito / Copywriter / Landing
El Rastreador (CIF)  ─┘          ▲                          Revisor de pixel ─► Implementador
Buscador de keywords ────────────┘                                   │
                                  Revisión de campañas ◄─────────────┘ (ciclo semanal)
```

## Piezas compartidas (formato común)

Cada skill entrega su resultado con un bloque final llamado **"Para la siguiente skill"**, con los campos que le tocan de esta lista. Así la siguiente skill lo toma sin preguntar de nuevo.

### Ficha del negocio
- Vertical: real estate / ecommerce / infoproductos / servicios-coaching
- Producto u oferta y ticket (rango de precio)
- Ubicación del público (país, ciudad o zona)
- Objetivo comercial: leads, mensajes o ventas, y si el cliente prioriza **cantidad o calidad**
- Presupuesto mensual de pauta
- Capacidad operativa para atender leads (equipo, WhatsApp API, CRM)
- Ángulo de venta que ya le trajo clientes (si existe) → entra como hipótesis validada

### Benchmark
- Histórico propio de la cuenta (costo por resultado + volumen), o
- Proyectos similares como referencia aproximada si la cuenta es nueva
- Ajustes aplicados por país, ciudad, temporada y tipo de campaña

### Diagnóstico
- Cuello de botella ubicado en el funnel: impresión → clic → lead/mensaje/compra → calificación → venta
- Causa probable y la evidencia que la sostiene
- Nivel de confianza: **Confirmado** (3+ casos) o **Hipótesis**

### Hallazgos de mercado (de El Rastreador)
- Mensajes saturados (con N o %)
- Territorios creativos priorizados
- Objeciones y deseos del cliente

### Plan de acción
- Acciones concretas y replicables, ordenadas por impacto
- Qué se lleva de lo que funciona a lo que no funciona
- Cuándo revisar de nuevo (respetando la cadencia: revisar diario, intervenir cada 2–3 días)

## Qué hace cada skill (y qué NO hace)

| Skill | Recibe | Entrega | No hace |
|---|---|---|---|
| Auditoría de negocio | Datos del cliente | Ficha del negocio | No toca la cuenta publicitaria |
| `auditoria-cuenta-publicitaria` | Acceso o export de una cuenta que heredas | Foto inicial: estructura, tracking, benchmark, diagnóstico | No arma el plan de medios |
| `el-rastreador` | Ficha del negocio + competidores | Hallazgos de mercado | No evalúa anuncios propios |
| Buscador de keywords | Ficha del negocio | Keywords agrupadas para Google | No arma campañas |
| `estratega-digital-anuncios` | Ficha + benchmark + hallazgos | Plan de medios, segmentos, ángulos, objeciones por anuncio | No escribe los guiones |
| Changuito | Ángulo + objeción + nivel de consciencia + etapa | Guiones y copies (hooks, cuerpo, CTA) | No define la estrategia |
| Copywriter | Plan + ficha | Mails y textos de landing | No hace anuncios |
| `landing-ghl-con-claude` | Copy de la landing | Landing publicada en GHL | No escribe el copy desde cero |
| Revisor de pixel y GTM | URL + plataformas | Estado del tracking y correcciones | No crea campañas |
| Implementador | Plan + creativos + tracking OK | Campañas montadas | No decide el ángulo |
| `revision-de-campanas` | Datos de campañas activas + benchmark | Diagnóstico + plan de acción semanal | No hace la foto inicial de una cuenta heredada |

## Reglas que todas las skills respetan
1. **Nunca un indicador solo.** Un CTR o un CPL aislado no dice nada; se contrasta con lo que pasa después en el funnel.
2. **Cada regla lleva etiqueta:** Universal (mecanismo que aplica a cualquier nicho) o Específica de vertical (cifra o variante de un vertical).
3. **Confirmado vs. hipótesis:** una regla es confirmada con 3+ casos reales; si no, se dice que es hipótesis.
4. **Las cifras de un vertical no se cruzan con otro.**
5. **El diagnóstico siempre termina en una acción replicable.**
6. **Sin datos de clientes reales:** los casos de referencia van anonimizados.
