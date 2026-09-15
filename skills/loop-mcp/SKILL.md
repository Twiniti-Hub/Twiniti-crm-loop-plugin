---
name: loop-mcp
description: Use when working with Twiniti Loop via MCP — contacts, segments, campaign drafts. Always prefer Loop MCP tools; never Neon; never paste agent tokens.
---

# Twiniti Loop MCP

The live Loop MCP is Streamable HTTP (no stdio). This plugin only wraps it.

## Do

- Use MCP tools for contacts, segments, and campaign drafts.
- Match `LOOP_MCP_URL` to the workspace region (EU / US / UK). Local: `http://localhost:4000/mcp`.
- Treat `tools/list` as authoritative. Do not assume a tool exists because it is listed in a prompt.

## Do not

- Never connect to Neon PostgreSQL. Agents use the public MCP/API only.
- Never paste `LOOP_AGENT_TOKEN` / `twiniti_agent_…` into chat, PRs, tickets, or logs.
- Do not send campaigns. There is no campaign-send MCP tool yet — drafts and status only.
- Board / kanban (Contacts/Companies saved views) is **user-only**. Agent credentials have no board-view scopes. Use contact create/update/read for record changes.

## After merge

Grok Bot connect is owned by Computer (`AddMcpServer` with the same URL + token). Do not add the connector from this plugin scaffold.
