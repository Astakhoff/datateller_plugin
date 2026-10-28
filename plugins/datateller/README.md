# DataTeller plugin

DataTeller is a descriptive layer over your data: a catalog of tables and metrics,
reports and dashboards, access and roles, and monitoring for BigQuery, ClickHouse
and AWS analytics. This plugin connects Claude (claude.ai, Desktop, mobile, Claude Code)
and Codex / ChatGPT to your DataTeller workspace through **one** MCP server.

## What is inside

| Part | Content |
|---|---|
| `.claude-plugin/plugin.json` | Listing metadata: name, version, description, icon, links |
| `.codex-plugin/plugin.json` | The same metadata for Codex; points Codex to its own hooks file |
| `.mcp.json` | Exactly one remote MCP server — the shared DataTeller entry `https://app.datateller.ai/mcp` |
| `assets/logo.svg` | The DataTeller `dt` mark from the official brand kit |
| `skills/` | Three skill pointers: `dt-create-report`, `dt-manage-access`, `dt-create-metric` (see `skills/README.md`) |
| `hooks/` | Feedback hooks: `hooks.json` for Claude Code, `codex-hooks.json` for Codex. Every hook only calls a DataTeller tool on the same server; no commands, no texts |

There are no commands, no executable code, no secrets and no customer data in this package.
Everything the assistant knows about how to work with DataTeller — including what the hooks
say — lives on the server and is maintained by the DataTeller team.

## Feedback hooks: requirements

The hooks ask the assistant to rate its own confidence in DataTeller results and offer you one
optional question about the suggested data source. They need:

- **Claude Code 2.1.308** or newer (Claude Code tab of Claude Desktop);
- **Codex 0.163.0-alpha.11** or newer (ships with Codex desktop 26.1016). In Codex, approve the
  DataTeller hooks once in `/hooks`.

Without hooks support the plugin works as usual, just without these ratings.

How to answer the question, how to turn the hooks off for yourself, which clients run them
and what is recorded: DataTeller Help, record `plugin.feedback-hooks` (Help connector
`https://app.datateller.ai/help-mcp`; ask the assistant to look it up).

## Connecting

1. Install the plugin in your client. In Claude Code:

   ```
   /plugin marketplace add Astakhoff/datateller_plugin
   /plugin install datateller@datateller
   ```

   In Codex CLI:

   ```
   codex plugin marketplace add Astakhoff/datateller_plugin
   codex plugin add datateller@datateller
   ```

   In Claude (claude.ai / Desktop) and Codex / ChatGPT add the same marketplace repository
   `Astakhoff/datateller_plugin` in the plugin settings.
2. On the first call the client opens a browser window: sign in to DataTeller with your
   usual account and approve the connection.
3. Ask the assistant which projects you can reach — it calls `datateller_whoami` and lists
   them. Every write names the target project explicitly.

You only see the projects and tools your DataTeller roles allow; the plugin grants nothing
by itself. You can revoke the connection at any time in DataTeller, section «MCP».

Direct connection without the plugin works as well, with the same address:

```
codex mcp add datateller --url https://app.datateller.ai/mcp
```

## Links

- Website: https://datateller.ai
- Privacy policy: https://datateller.ai/privacy

## Versioning

The plugin version in `.claude-plugin/plugin.json` and `.codex-plugin/plugin.json` (always the
same) is raised with every release of the package. The version of the server-side
methodologies is reported by `datateller_whoami`.

## License

MIT, see `LICENSE`.
