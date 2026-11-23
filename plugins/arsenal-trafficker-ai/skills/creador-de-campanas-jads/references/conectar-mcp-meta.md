# Cómo conectar el MCP oficial de Meta Ads a Claude Code

Muéstrale estos pasos al trafficker cuando el MCP no esté conectado. Si algo de la pantalla de Meta no coincide, remítelo a la guía oficial, porque Meta cambia sus pantallas con frecuencia:
https://developers.facebook.com/documentation/ads-commerce/ads-ai-connectors/ads-mcp-server/ads-mcp-server-get-started

## Dirección del servidor
`https://mcp.facebook.com/ads`

## Pasos (con app propia de Meta)
1. Entra a https://developers.facebook.com/apps y crea o abre una app.
2. Agrega el caso de uso **"Create & manage ads with ads MCP server"**.
3. Configura la URL de redirección de la app (en Facebook Login for Business) para que coincida con Claude Code, según la guía oficial.
4. En la terminal, ejecuta (reemplaza `<META_APP_ID>` por el ID de tu app):
   ```bash
   claude mcp add --transport http --client-id <META_APP_ID> meta-ads https://mcp.facebook.com/ads
   ```
5. Abre Claude Code: te llevará al inicio de sesión de Facebook Login for Business. Inicia sesión y aprueba los permisos. No hace falta copiar tokens a mano.

## Permisos necesarios
- `ads_mcp_management`
- `ads_management` (para **crear** campañas; con solo `ads_read` no se puede implementar)
- Opcionales: `business_management`, `pages_show_list`, `instagram_basic`, `catalog_management`

## Sin app propia
Meta indica que también se puede acceder sin tener una app propia, siguiendo su guía "How to set up Meta ads AI connectors". Si el trafficker no quiere crear una app, remítelo a esa guía desde la documentación oficial de Meta.

## Comprobar que funciona
En Claude Code, pide: "lista mis cuentas publicitarias". Si aparecen, el MCP está listo.
