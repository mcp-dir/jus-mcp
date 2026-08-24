# Security Policy

Jus MCP é **read-only e sem login** pra uso básico (dados públicos). Ainda assim, trate qualquer token de conta (se você optar por logar pra limites maiores) como credencial.

- Prefira **OAuth 2.1** quando o cliente suportar: o token nunca passa pelo chat.
- No fluxo **agent-auth**, o JWT passa pelo provedor LLM (Anthropic / OpenAI / Cursor) — ative retenção zero (Claude "Improve Claude" off, Cursor Privacy Mode) e rotacione.
- Este MCP **não move dinheiro nem altera dados** — é 100% leitura.

## Reportar vulnerabilidades

**NÃO abra issue pública.** Mande e-mail pra **[jus@mcp.ai](mailto:jus@mcp.ai)** com descrição, passos de reprodução e versão do cliente/SO. Resposta em até 72h úteis.
