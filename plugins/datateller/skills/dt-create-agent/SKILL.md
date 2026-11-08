---
name: dt-create-agent
description: DataTeller project agents. Use when the user wants work repeated or automated on a schedule from their own cloud client, or wants to create, take, hand over or stop a DataTeller agent.
---

# DataTeller: create an agent

A DataTeller agent is a saved instruction of the project that runs on a schedule from the user's
own cloud client. Use this skill when the user asks to repeat or automate work on a schedule, or to
create, take, hand over or stop a project agent in DataTeller. Do not offer agents on your own.

1. **Enable the tools.** Call `datateller_enable_groups` with `catalog.agents` (Manage
   agents): these tools are not in the starting set. If the group does not exist, agents
   are not available here: tell the user and stop.
2. **Read the method first.** Call `catalog_agent_guide(client="claude")`, naming your client:
   claude, codex, chatgpt or other. Follow the common part and that client's section. The method
   and the ready templates live on the DataTeller server and are maintained there; this skill only
   points to them.
3. **Re-read before every new task.** Before each new task with an agent, request the method
   again instead of relying on a copy read earlier in the chat.

Rules that do not depend on the method version:

- Run the instruction once in the chat and show the result before saving it.
- Use the launcher text the server returns, unchanged; never copy the instruction into the client.
- Leave enabled only the connectors and tools the agent needs; no destructive actions.
- Only a recorded result of `catalog_agent_finish` proves the agent worked.
