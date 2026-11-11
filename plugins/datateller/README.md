# DataTeller plugin

Package version: **0.2.7**.

DataTeller connects your data catalog, metrics, reports, access and BigQuery,
ClickHouse and AWS analytics monitoring through one MCP entry: `https://app.datateller.ai/mcp`.

| Surface | Connection and methodology |
|---|---|
| Claude Code / Codex desktop | Local public package and OAuth; `claude` / `codex` section |
| Claude.ai, desktop or mobile browser | Remote MCP and OAuth; `claude` section, without local hooks |
| ChatGPT, desktop or mobile browser | Custom MCP through ChatGPT's interface and OAuth; `chatgpt` section |

Availability depends on client capabilities and account policy. After connection, the
single `datateller_plugin_setup_guide` provides current steps and readiness boundaries.
Advertised UI support does not prove form display; verify each surface separately.

## In-application setup

Install DataTeller from the public source `Astakhoff/datateller_plugin` using your local
client's native controls. On the installed plugin card, choose **Connect**, personally
complete OAuth, and run `dt-setup` (the offered Setup in Codex). The skill reads the single
system methodology `datateller_plugin_setup_guide`: `common`, then only the selected
`claude`, `codex` or `chatgpt` section.

The methodology is maintained in DataTeller Agent Skills -> core -> plugin_setup.
It distinguishes clients, capabilities and verified readiness. It is unavailable before
OAuth; installation and connection alone do not prove that ratings work.

## Hook requirements

- Claude Code **2.1.308** or later, including the Code tab in Claude Desktop.
- Codex **0.163.0-alpha.11** or later; this version ships with Codex desktop **26.1016**.

Client version is only a prerequisite. Verify form support and personal hook trust using
the current server methodology. A newer version alone does not establish rating readiness.

For rating and data-recording documentation, ask the assistant to read `plugin.feedback-hooks`
in DataTeller Help through `https://app.datateller.ai/help-mcp`.

## Direct MCP connection

Shared entry: `https://app.datateller.ai/mcp`. Access controls are the same; local plugin
hooks are absent. The authorized `datateller_plugin_setup_guide` supplies setup details
and does not promise another client's capabilities to an unknown client.

## Contents

| Component | Purpose |
|---|---|
| `.claude-plugin/plugin.json` | Claude metadata |
| `.codex-plugin/plugin.json` | Codex metadata, hooks and onboardingSkill |
| `.mcp.json` | One shared DataTeller MCP entry |
| `skills/` | Seven local connection checks and pointers to server methodologies |
| `hooks/` | DataTeller tool calls only; no commands or embedded methodologies |
| `assets/logo.svg` | Official DataTeller brand mark |

The package contains no executable code, secrets or customer data. Business methodologies and hook
instructions live on the server; connection recovery instructions are available locally before OAuth. Access can be revoked in the website's MCP section.
Claude and Codex manifest versions are updated together. A changed hook definition may
require another personal review in the client.

## Links

- Website: https://datateller.ai
- Privacy policy: https://datateller.ai/privacy

MIT license; see LICENSE.
