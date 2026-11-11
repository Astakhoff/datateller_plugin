---
name: dt-create-report
description: DataTeller reports and dashboards. Use when the user wants to build, edit, preview or publish a report or a dashboard in DataTeller.
---

# DataTeller: build, edit or publish a report

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

Use this skill when the user asks to build, edit, preview or publish a report or a dashboard
in DataTeller.

1. **Enable the tools.** Call `datateller_enable_groups` with `catalog.reports`
   (Reports & dashboards): the report tools are not in the starting set.
2. **Read the method first.** Call `catalog_report_guide` and follow it. The method lives on
   the DataTeller server and is maintained there; this skill only points to it.
3. **Re-read before every new task.** Before each new task that creates or changes a report,
   request the method again instead of relying on a copy read earlier in the chat. The method
   reports its version: pass it to the write tools that accept it, and if a write answers
   `methodology_changed`, read the method again before going on.

Rules that do not depend on the method version:

- Name the target project explicitly in every write.
- Show the user a preview before publishing, and publish only after they agree.
