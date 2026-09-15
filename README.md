# Twiniti Loop

Cursor plugin that wraps the **existing** Twiniti Loop CRM MCP (Streamable HTTP). It does not rebuild or proxy the MCP server.

- Plugin id: `twiniti-loop`
- Version: `0.1.2`
- License: [MIT](LICENSE-MIT) OR [Apache-2.0](LICENSE-APACHE) (your choice). See [LICENSE](LICENSE).
- Connection guide: [Twiniti-crm `docs/AGENT_CONNECTION.md`](https://github.com/Twiniti-Hub/Twiniti-crm/blob/development/docs/AGENT_CONNECTION.md)

## Install

### Cursor Marketplace (after publish)

Install **Twiniti Loop** from the Cursor Marketplace, then open **Plugins → Configure** and set the variables below.

### Local

1. Clone or copy this repo to `~/.cursor/plugins/local/twiniti-loop`.
2. Reload Cursor (**Developer: Reload Window**).
3. Open **Plugins → Configure** (or Customize) for Twiniti Loop and set variables.

## Configure

| Variable | Default | Notes |
| --- | --- | --- |
| `LOOP_MCP_URL` | `https://loop.eu.twiniti.ai/mcp` | Also `https://loop.us.twiniti.ai/mcp`, `https://loop.uk.twiniti.ai/mcp`, or `http://localhost:4000/mcp` for local API |
| `LOOP_AGENT_TOKEN` | *(secret)* | Create an agent on the Loop workspace **Agents** page. Token is shown once. Prefix `twiniti_agent_` |

Never commit tokens, Neon URLs, or Hexclave server keys.

## Smoke test

1. Confirm MCP tools load (`tools/list`).
2. Call `list_segments` or `search_contacts` with a short query.

Expected tools include: `search_contacts`, `get_contact`, `create_contact`, `upsert_contact`, `update_contact`, `get_contact_timeline`, `list_segments`, `get_segment`, `estimate_segment_size`, `create_campaign_draft`, `get_campaign_status`.

## Known issue (Cloudflare 1010)

Some non-browser MCP clients receive **Cloudflare error 1010** when calling `loop.*.twiniti.ai`. A browser-like `User-Agent` and/or Cloudflare allowlist for the client may be required. Do not change Cloudflare settings without an explicit Twiniti ops yes.

## Safety

- Prefer Loop MCP tools for contacts, segments, and campaign drafts.
- Never query Neon directly.
- Never paste agent tokens into chat or tickets.
- Campaign **send** is not available via MCP yet.
- Board / kanban is user-only.

## Skills

- `loop-mcp` — general Loop MCP usage
- `loop-contacts` — contact tools
- `loop-campaigns` — segments and campaign drafts

## License

Available under the [MIT License](LICENSE-MIT) or the [Apache License 2.0](LICENSE-APACHE), at your option (same dual-license model as [Twiniti-crm](https://github.com/Twiniti-Hub/Twiniti-crm)).
