---
name: dt-setup
description: DataTeller plugin installation, updates and setup for Claude, Codex or ChatGPT; connect an account and verify readiness using the current system methodology.
---

# DataTeller: setup

## Connection first

Before OAuth, on confirmed missing authorization or `reauthenticationRequired`, immediately say in the user's language:
"Connect DataTeller through its installed plugin card to continue; if connected before, sign in again."
Use **Connect** only if offered there, or the client's native auth action; never invent controls or links.
Pause dependent calls; request sign-in once per recovery, without retry loops. Do not call this a service failure.
Never suggest a terminal, reinstall, secrets or config edits. If all tools are absent without an auth signal,
say the cause is unknown and ask to check connection status on the card. One missing tool with working whoami
is not an OAuth failure: check groups, selected project, enabled module and permissions first. After connection,
use the available read-only `datateller_whoami` on that same connection, keep the selected project, then resume
the original task and read its method. Do not restart completed setup.

The user signs in personally. The methodology is unavailable until connected; do not invent it.
After OAuth, read `datateller_plugin_setup_guide(section="common")`.
Follow its routing rules to identify the user's target client, then read only one section
of the same tool: `section="claude"`, `section="codex"` or `section="chatgpt"`.
Follow the current returned methodology. Do not replace it with local instructions or
guess an unknown client. Do not declare readiness without verification.
