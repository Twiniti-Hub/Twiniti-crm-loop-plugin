# Twiniti Loop (Cursor plugin)

Wraps the **existing** Twiniti Loop MCP. It does not rebuild or proxy the server.

- Plugin id: `twiniti-loop`
- MCP: Streamable HTTP (no stdio)
- Connection guide (Twiniti-crm): https://github.com/Twiniti-Hub/Twiniti-crm/blob/development/docs/AGENT_CONNECTION.md

## Variables

Set these in Cursor (Plugins → Configure) or when installing locally. Values are not stored in this repo.

| Variable | Default | Notes |
| --- | --- | --- |
| `LOOP_MCP_URL` | `https://loop.eu.twiniti.ai/mcp` | Also `https://loop.us.twiniti.ai/mcp`, `https://loop.uk.twiniti.ai/mcp`, or `http://localhost:4000/mcp` |
| `LOOP_AGENT_TOKEN` | (secret) | From the Loop workspace **Agents** page. Shown once. Prefix `twiniti_agent_` |

Never commit tokens, Neon URLs, or Hexclave server keys.

## Local test (Cursor)

1. Copy or symlink this repo to `~/.cursor/plugins/local/twiniti-loop`.
2. Reload Cursor (Developer: Reload Window).
3. Open **Customize** / Plugins → Twiniti Loop. Set `LOOP_MCP_URL` and `LOOP_AGENT_TOKEN`.
4. Confirm tools such as `search_contacts` appear. Call `tools/list` rather than assuming the catalog.

## Grok Bot

After this repo is on GitHub, Computer connects Grok Bot with the same URL and token (`AddMcpServer`). Do not connect from this scaffold alone.

## Tools (today)

`search_contacts`, `get_contact`, `create_contact`, `upsert_contact`, `update_contact`, `get_contact_timeline`, `list_segments`, `get_segment`, `estimate_segment_size`, `create_campaign_draft`, `get_campaign_status`.

Not in MCP: campaign send; board/kanban (user-only).
