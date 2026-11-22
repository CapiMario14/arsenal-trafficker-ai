# Arsenal Trafficker AI — La Jungla de los Ads

Las skills de Claude para traffickers que trabajan Meta, Google y TikTok Ads. Cubren todo el trabajo, desde el diagnóstico del negocio hasta la campaña corriendo y optimizada.

## Instalación (2 comandos)

Abre Claude Code en cualquier carpeta de tu computadora y pega:

**1. Agrega el marketplace**
```
/plugin marketplace add https://github.com/CapiMario14/arsenal-trafficker-ai.git
```

**2. Instala el arsenal**
```
/plugin install arsenal-trafficker-ai@jungla-de-los-ads
```

Listo. Cuando publiquemos skills nuevas o mejoras, se actualizan desde aquí.

¿Ves la versión vieja? Corre `/plugin marketplace update jungla-de-los-ads`.

¿Todavía no tienes Claude Code? Revisa el módulo de Claude Code dentro de la comunidad en Skool.

## Las skills por fase

| Fase | Skill | Para qué sirve | Estado |
|---|---|---|---|
| 1. Diagnóstico | Auditoría de negocio | Leer el negocio antes de pautar | Próximamente |
| | `auditoria-cuenta-publicitaria` | Foto inicial de una cuenta que heredas | ✅ |
| 2. Investigación | `el-rastreador` | Investigación de mercado y competencia (CIF) | ✅ |
| | Buscador de keywords | Keywords para Google Ads | Próximamente |
| 3. Estrategia | `estratega-digital-anuncios` | Onboarding, criterio de éxito, plan de medios, buyer persona y objeciones | ✅ |
| 4. Producción | Changuito | Guiones y copies de anuncios por ángulo de venta | Próximamente |
| | Producción de anuncios | Dirección y generación de creativos | Próximamente |
| | Copywriter | Mails y textos de landing | Próximamente |
| | `landing-ghl-con-claude` | Construir y publicar landings en GoHighLevel | ✅ |
| 5. Implementación | Revisor de pixel y GTM | Revisar pixel, eventos y Tag Manager (Meta y Google) | Próximamente |
| | Implementador de campañas | Subir la estructura de campañas | Próximamente |
| 6. Optimización | `revision-de-campanas` | Diagnóstico periódico de rendimiento y decisiones | ✅ |
| Complementarias | `domador-de-objeciones` | Responder objeciones y armar propuestas para cerrar clientes | ✅ |
| | `ghostwriting-linkedin` | Posts de LinkedIn de marca personal por fase de funnel | ✅ |

## Cómo se conectan las skills

Cada skill entrega un bloque "Para la siguiente skill" con un formato común. El detalle está en [CONTRATO.md](CONTRATO.md).

## MCPs recomendados

Algunas skills necesitan conexiones para funcionar al 100%:
- **El Rastreador:** Apify (bibliotecas de anuncios) + Supadata (transcripción de videos).
- **Landing GHL:** Claude in Chrome.
- **Auditoría y revisión de campañas:** el MCP de Meta Ads (opcional: también funcionan con exports o capturas).

## Soporte

Dudas con la instalación o las skills: dentro de la comunidad de La Jungla de los Ads en Skool.
