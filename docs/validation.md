# Validation record

## Scope

Validation was performed on October 28-29, 2026 in the controlled laboratory. Results below reflect the specific endpoints, test actions, monitoring configuration, and observed windows used for the capstone. They do not measure enterprise performance or detection coverage.

## Acceptance results

| Acceptance criterion | Observed result | Status |
| --- | --- | --- |
| Two connected agents | Ubuntu and macOS agents active in the Wazuh dashboard | Pass |
| Authentication detection | 3 of 3 controlled SSH login-failure trials generated corresponding alerts | Pass |
| File-integrity detection | Controlled file creation, modification, and deletion generated expected alerts | Pass |
| Benign controls | Four actions executed; no incorrect authentication-failure or FIM alerts attributed to them during observed windows | Pass |
| Alert investigation | File-deletion alert reviewed and classified against the documented test activity | Pass |

## Positive detection evidence

| Test | Expected detection | Observed rule / level |
| --- | --- | --- |
| FIM 1 | File creation | Rule 554, level 5 |
| FIM 2 | File modification | Rule 550, level 7 |
| FIM 3 | File deletion | Rule 553, level 7 |
| Authentication trials | Failed SSH and PAM authentication activity | Rules 5710 and 5503 observed |

The final authentication view showed 12 related alert records across controlled testing. That is not interpreted as 12 independent incidents because one login attempt can generate more than one related alert.

## Benign controls

The observed benign controls were an authorized SSH login, reading `/etc/hosts`, listing the monitored test directory, and creating a file outside the monitored directory. This was a small qualitative check, not a statistical false-positive assessment.

## Validation focus

- Version 1 validation used two active agents.
- Validation concentrated on authentication and file-integrity telemetry.
- The next measurement phase will compare local-log and centralized investigation workflows.
- Resilience, throughput, and larger false-positive assessments are planned as future test work.
