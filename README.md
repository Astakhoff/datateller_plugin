# DataTeller plugin for Claude and Codex

This public repository contains one DataTeller plugin: catalog, metrics, reports,
access and monitoring through the shared MCP entry `https://app.datateller.ai/mcp`.

| Surface | Connection and methodology |
|---|---|
| Claude Code / Codex desktop | Local public package and OAuth; `claude` / `codex` section |
| Claude.ai, desktop or mobile browser | Remote MCP and OAuth; `claude` section, without local hooks |
| ChatGPT, desktop or mobile browser | Custom MCP through ChatGPT's interface and OAuth; `chatgpt` section |

Availability depends on client capabilities and account policy. After connection,
the single `datateller_plugin_setup_guide` supplies current steps and readiness boundaries.
Advertised UI support does not prove form display; verify each surface separately.

## In-application connection

Install the package from the public source `Astakhoff/datateller_plugin` using your local
client's native controls. On the installed plugin card, choose **Connect**, personally
complete OAuth, and run `dt-setup` (the offered Setup in Codex). It reads the current
system methodology through `datateller_plugin_setup_guide`: the common section and one
target-client section. Installation alone does not establish rating readiness.

Contents and prerequisites: [Plugin README](plugins/datateller/README.md).

| Path | Contents |
|---|---|
| `.claude-plugin/marketplace.json` | Plugin catalog |
| `plugins/datateller/` | DataTeller package |

This repository contains no executable code, secrets or customer data. The package is
published from DataTeller's main repository; direct edits to this copy are replaced
on the next release.

Website: https://datateller.ai · Privacy: https://datateller.ai/privacy

MIT license; see LICENSE.
