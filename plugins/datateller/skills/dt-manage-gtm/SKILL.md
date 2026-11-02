---
name: dt-manage-gtm
description: DataTeller Google Tag Manager. Use when the user wants to audit, configure, publish or roll back GTM tags, triggers, variables, workspaces or container versions in DataTeller.
---

# DataTeller: manage Google Tag Manager

Use this skill when the user asks to audit, configure, publish or roll back tags, triggers,
variables, workspaces or container versions of a Google Tag Manager container in DataTeller.

1. **Name the context.** Agree with the user on the DataTeller project and the GTM container
   before any call; work only with containers selected for that project.
2. **Read the method first.** Call `gtm_guide` (group `gtm.start`, visible from the start)
   and follow it. The method lives on the DataTeller server and is maintained there; this
   skill only points to it.
3. **Enable rare groups only for the task.** `gtm_guide(topic="groups")` says which groups
   are visible from the start. Enable any other group the task needs with
   `datateller_enable_groups` at the start, and hide it with `datateller_disable_groups`
   when the task is done.
4. **Re-read before every new task.** Before each new task that changes GTM, request the
   method again instead of relying on a copy read earlier in the chat. The method reports
   its `methodology_version`; a plan made under an older version is stale: make a new plan.

Rules that do not depend on the method version:

- Destructive changes go as plan first, then the user's confirmation in the chat; never try
  to get around the confirmation the tool itself asks for.
- Publish only the way `gtm_guide(topic="publish_and_rollback")` names, as plan first and
  then the user's confirmation in the chat; never work around it.
- If a write answers `write_not_enabled`, that change is off for this project: tell the user
  and do not make it with a tool the method does not name for it.
