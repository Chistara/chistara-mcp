# Changelog

Versions follow the MCP Registry entry `ai.hoghogh/chistara` and the server's `serverInfo.version`.

## 1.1.1 — 2026-11-13
- **Sign in with OAuth:** `https://hoghogh.ai/mcp/connect` — Claude and ChatGPT connect by signing in to Chistara
  (OAuth 2.1, PKCE, dynamic client registration); no personal link to copy. `/mcp` and personal links keep working.
- The registry entry links this repository. Tools unchanged.

## 1.1.0 — 2026-10-27
- Tool calls need the user's personal connection link (a Chistara account with credit); tool listing stays public.
- The optional `Authorization: Bearer <token>` header is documented in the registry entry.
- 23 tools, all read-only.

## 1.0.0 — 2026-08-13
- First listing in the official MCP Registry.
