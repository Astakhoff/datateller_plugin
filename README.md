# DataTeller plugin for Claude and Codex

This repository is the plugin catalog (marketplace) of DataTeller. It holds exactly one plugin,
`datateller`, that connects Claude (claude.ai, Desktop, Claude Code) and Codex / ChatGPT to your
DataTeller workspace through one MCP server: catalog, reports and dashboards, metrics, access and
monitoring for BigQuery, ClickHouse and AWS analytics.

## Install

Claude Code:

```
/plugin marketplace add Astakhoff/datateller_plugin
/plugin install datateller@datateller
```

Codex CLI:

```
codex plugin marketplace add Astakhoff/datateller_plugin
codex plugin add datateller@datateller
```

In Claude (claude.ai / Desktop) and Codex / ChatGPT add the marketplace repository
`Astakhoff/datateller_plugin` in the plugin settings.

On the first call the client opens a browser window: sign in to DataTeller and approve the
connection. You only see the projects and tools your DataTeller roles allow; the plugin grants
nothing by itself.

## What is inside

| Path | Content |
|---|---|
| `.claude-plugin/marketplace.json` | The catalog file; Claude and Codex both read it |
| `plugins/datateller/` | The plugin itself; see its [README](plugins/datateller/README.md) |

There is no executable code, no secrets and no customer data in this repository.

## Links

- Website: https://datateller.ai
- Privacy policy: https://datateller.ai/privacy

## How this repository is maintained

The plugin is developed in the main DataTeller repository and copied here on every release, so
changes made directly in this repository are overwritten by the next release.

## License

MIT, see `LICENSE`.
