# Security Policy

O acesso ao Olist Tiny ERP é via token (OAuth access_token ou JWT do agent-auth). **O token equivale a uma senha** — não compartilhe, não cole em chats públicos/issues/pastebins.

- Prefira **OAuth 2.1** quando o cliente suportar: o token nunca passa pelo chat.
- No fluxo **agent-auth**, o JWT passa pelo provedor LLM (Anthropic / OpenAI / Cursor) — ative retenção zero (Claude "Improve Claude" off, Cursor Privacy Mode) e rotacione.
- Este MCP **altera dados no ERP**: 106 das 179 ferramentas são de escrita (criar e alterar pedidos, lançar estoque, emitir e cancelar NF-e, baixar contas a receber). Quem tem o token pode fazer tudo isso na sua conta Olist. Revogue o acesso em `app.mcp.ai` se o token vazar.

## Reportar vulnerabilidades

**NÃO abra issue pública.** Mande e-mail pra **[olist@mcp.ai](mailto:olist@mcp.ai)** com descrição, passos de reprodução e versão do cliente/SO. Resposta em até 72h úteis.
