---
name: dt-create-agent
description: DataTeller project agents. Use when the user wants work repeated or automated on a schedule from their own client, or wants to create, take, hand over or stop a DataTeller agent.
---

# DataTeller: create an agent

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

A DataTeller agent is a saved instruction of the project that runs on a schedule from the user's
own client: a cloud task in Claude, a local scheduled task in the Codex app. Use this skill when the user asks to repeat or automate work on a schedule, or to
create, take, hand over or stop a project agent in DataTeller. Do not offer agents on your own.

1. **Enable the tools.** Call `datateller_enable_groups` with `catalog.agents` (Manage
   agents): these tools are not in the starting set. If the group does not exist, agents
   are not available here: tell the user and stop.
2. **Read the method first.** Call
   `catalog_agent_guide(client=<your client: claude | codex | chatgpt | other>)`. Follow the common part and that client's section. The method
   and the ready templates live on the DataTeller server and are maintained there; this skill only
   points to them.
3. **Re-read before every new task.** Before each new task with an agent, request the method
   again instead of relying on a copy read earlier in the chat.

Rules that do not depend on the method version:

- Run the instruction once in the chat and show the result before saving it; save it with
  `interval_minutes` in `expected_schedule` (1440 for daily): overdue is counted from it.
- Use the launcher text the server returns, unchanged; never copy the instruction into the client.
- Leave enabled only the connectors and tools the agent needs; no destructive actions.
- Only a recorded result of `catalog_agent_finish` proves the agent worked.
