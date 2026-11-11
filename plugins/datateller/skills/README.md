# DataTeller skills

Every skill starts with a local connection recovery instruction, available before OAuth.
Business skills then point to server methodologies:

| Skill | Methodology |
|---|---|
| `dt-create-report` | `catalog_report_guide` |
| `dt-manage-access` | `catalog_access_guide` |
| `dt-create-metric` | `catalog_metric_guide` |
| `dt-collect-candidates` | `catalog_read_candidate_skill` |
| `dt-manage-gtm` | `gtm_guide` |
| `dt-create-agent` | `catalog_agent_guide` |

`dt-setup` is a short pointer to the system-wide `datateller_plugin_setup_guide`.
After OAuth it reads `common` and one client section. Codex declares it as onboardingSkill.
The methodology is shared across the platform and edited in the existing Agent Skills
administration interface; there are no local copies or project overrides.
