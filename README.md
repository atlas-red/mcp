# Atlas Red — mind map MCP server

The official [Model Context Protocol](https://modelcontextprotocol.io) server of
[Atlas Red](https://atlas-red.com), a browser-based mind mapper you buy once
(Pro $99 one-time; Free edition, no card). The server is **hosted** — there is
nothing to install or run — and it is **free and never metered**.

- **Endpoint:** `https://app.atlas-red.com/mcp` (Streamable HTTP, OAuth 2.0)
- **Registry:** `com.atlas-red/mind-map` in the [official MCP Registry](https://registry.modelcontextprotocol.io/v0.1/servers?search=atlas-red)
- **Docs:** [atlas-red.com/mind-map-mcp](https://atlas-red.com/mind-map-mcp) · [connection steps](https://atlas-red.com/mind-map-mcp#connect)
- **ChatGPT:** also available as an app in the [ChatGPT plugin directory](https://atlas-red.com/chatgpt-mind-map)
- **Privacy policy:** https://app.atlas-red.com/privacy · **Terms:** https://app.atlas-red.com/terms

## Connect

Any MCP client that speaks Streamable HTTP with OAuth:

| Client | How |
|---|---|
| Claude (web, desktop, mobile) | Settings → Connectors → *Add custom connector* → `https://app.atlas-red.com/mcp` |
| Claude Code | `claude mcp add --transport http atlas-red https://app.atlas-red.com/mcp` |
| ChatGPT | Install the Atlas Red app from the plugin directory, then mention **@Atlas Red** |
| Cursor, Windsurf, VS Code, others | Add a remote MCP server with the URL above; sign in when prompted |

Sign-in uses your Atlas Red account (Free is enough). Step-by-step per client:
https://atlas-red.com/mind-map-mcp#connect — the same steps with screenshots
are in the app under Help, which needs a sign-in.

## What the assistant can do

27 tools, every one annotated (`readOnlyHint` / `destructiveHint`):

- **Maps:** `list_maps`, `create_map`, `get_map`, `rename_map`, `delete_map`, `set_map_settings`, `update_schema`, `list_templates`
- **Nodes and links:** `add_node`, `update_node`, `delete_node`, `add_link`, `update_link`, `delete_link`, `get_context`
- **Structure:** `add_subtree`, `replace_subtree`, `extract_subtree`
- **Import / export:** `import_map` (Markdown, OPML, FreeMind, XMind, YAML, plain text), `export_map` (Markdown, OPML, XMindMark, FreeMind, JSON, HTML and more)
- **Images:** `set_image`, `get_image`, `remove_image`
- **Safety:** `undo`, `redo`
- **Feedback:** `send_feedback`, `reply_feedback`

Everything the assistant builds is a real, editable map in your account — not a
picture — and every map exports on every tier, including Free.

## Example prompts

- "Turn this meeting transcript into a mind map with decisions, owners and open questions as branches."
- "Open my *Q4 plan* map and restructure the marketing branch by channel."
- "Export the *Thesis outline* map as OPML so I can open it in OmniOutliner."

## About this repository

Atlas Red itself is closed source; this repository is the public home of the
MCP server's metadata (`server.json`, as published to the registry) and
connection documentation. Issues and questions: open an issue here or write to
hello@atlas-red.com.
