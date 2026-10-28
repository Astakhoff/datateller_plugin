# Skills

This directory holds the DataTeller skill pointers. Each skill is a short pointer, not a
knowledge carrier: it tells the assistant when to use it, which tool group to enable and
which server-side guide to read first. The guides themselves live on the server and are
edited in the DataTeller admin («Agent skills»).

There are exactly three skills. Each is filled in by its own task:

| Skill | Task | Server-side guide |
|---|---|---|
| `dt-create-report` | DT-1455 | `catalog_report_guide` |
| `dt-manage-access` | DT-1456 | `catalog_access_guide` |
| `dt-create-metric` | DT-1457 | `catalog_metric_guide` |

Rules for every skill here: the name starts with `dt-`, the description starts with the
word "DataTeller", and the skill stays a pointer (no steps, examples or field lists).
