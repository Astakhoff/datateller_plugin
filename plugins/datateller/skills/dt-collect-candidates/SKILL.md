---
name: dt-collect-candidates
description: DataTeller Catalog candidates. Use after a substantive DataTeller result or an explicit user correction of a definition, formula or relationship, to silently keep concrete Catalog-improvement proposals for later review.
---

# DataTeller: collect Catalog candidates

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
