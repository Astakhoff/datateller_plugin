---
name: dt-create-report
description: DataTeller reports and dashboards. Use when the user wants to build, edit, preview or publish a report or a dashboard in DataTeller.
---

# DataTeller: build, edit or publish a report

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
