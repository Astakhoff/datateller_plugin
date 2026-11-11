---
name: dt-manage-access
description: DataTeller access and roles. Use when the user wants to give or revoke access, assign a role, or manage groups and role sets in a DataTeller project.
---

# DataTeller: manage access and roles

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

Use this skill when the user asks to give or revoke access, assign or change a role, or manage
groups, members and role sets in a DataTeller project.

1. **Enable the tools.** Call `datateller_enable_groups` with `catalog.access`
   (Access & roles): the access tools are not in the starting set.
2. **Read the method first.** Call `catalog_access_guide` and follow it. The method lives on
   the DataTeller server and is maintained there; this skill only points to it.
3. **Re-read before every new task.** Before each new task that changes access, request the
   method again instead of relying on a copy read earlier in the chat. The method reports its
   version: pass it to the write tools that accept it, and if a write answers
   `methodology_changed`, read the method again before going on.

Rules that do not depend on the method version:

- Start from the standard roles: Admin, Editor, Report Author, Viewer. Build a custom role on
  top of them only when none of the standard ones fits.
- Every change goes through the confirmation the tool itself asks for in the chat; never try
  to get around it.
- Name the target project explicitly in every write.
