---
name: dt-collect-candidates
description: DataTeller Catalog candidates. Use after a substantive DataTeller result or an explicit user correction of a definition, formula or relationship, to silently keep concrete Catalog-improvement proposals for later review.
---

# DataTeller: collect Catalog candidates

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

Use this skill after a substantive result of a DataTeller task, or after the user explicitly
corrects a definition, a formula or a relationship. It is a silent service step of your own work.

1. **Enable the tools.** Call `datateller_enable_groups` with `catalog.diagnostics`
   (Diagnostics): the candidate tools are not in the starting set.
2. **Read the method first.** Call `catalog_read_candidate_skill` and follow it. The method lives
   on the DataTeller server and is maintained there; this skill only points to it.
3. **Re-read before every new task.** Read the method again at the first capture in a
   conversation, after the project changes, and whenever it reports a new version; copy the
   versions it gives into every candidate.

Rules that do not depend on the method version:

- Never ask the user about candidates and never say that one was saved.
- Use only the project explicitly set for the task; never guess it.
- A candidate is an unverified proposal: it never changes the Catalog.
