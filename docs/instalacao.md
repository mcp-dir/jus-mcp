# Instalação detalhada

Jus MCP é um servidor MCP remoto. Aponte seu cliente pra `https://api.mcp.ai/jus`. Snippets rápidos: [INSTALL.md](../INSTALL.md).

| Cliente | URL | Auth |
|---|---|---|
| Claude Desktop | `https://api.mcp.ai/jus` | nenhuma (grátis) |
| Cursor | `https://api.mcp.ai/jus` | nenhuma |
| VS Code (Copilot) | `https://api.mcp.ai/jus` | nenhuma |

A config JSON é a mesma em todos: só a URL, sem headers.

## Desinstalar

Remova o bloco `mcpServers.jus` (ou `servers.jus` no VS Code) do config do cliente e reinicie.
