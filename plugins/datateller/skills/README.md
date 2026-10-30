# Скиллы DataTeller

Три деловых скилла остаются короткими указателями на серверные методики:

| Скилл | Методика |
|---|---|
| `dt-create-report` | `catalog_report_guide` |
| `dt-manage-access` | `catalog_access_guide` |
| `dt-create-metric` | `catalog_metric_guide` |

`dt-setup` — такой же короткий указатель на системный `datateller_plugin_setup_guide`.
После OAuth он читает `common` и одну клиентскую секцию. В Codex он объявлен как
onboardingSkill. Методика единая для всей платформы, правится в существующей
админке Agent Skills; локальных копий и проектных переопределений нет.
