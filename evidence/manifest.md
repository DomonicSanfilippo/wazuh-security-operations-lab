# Evidence manifest

## Public evidence policy

The original capstone evidence exists in a private local archive and was reviewed to create this documentation. Raw files are not included here because they contain internal addresses, endpoint names, user paths, browser UI, or other environmental identifiers. This omission protects the lab and does not change the documented validation result.

| Evidence record | What it demonstrates | Public representation |
| --- | --- | --- |
| Wazuh dashboard overview | Central platform was available during lab work | Described in architecture and deployment records |
| Agent-status view | Ubuntu and macOS agents were active | Sanitized architecture diagram and validation table |
| FIM creation, modification, deletion alerts | Three controlled FIM changes detected | Validation table and safe procedures |
| Authentication alert views | Controlled failed SSH/PAM activity detected | Validation table and safe procedures |
| Benign-control view | No incorrect target alerts attributed during observed windows | Validation record with stated scope |
| Alert-investigation view | A file-deletion alert was reviewed and classified | Case 001 |
| Original architecture diagram | Implemented lab components and communication paths | Sanitized SVG in `architecture/` |

## Review standard for future screenshots

Before adding a screenshot, remove or redact address bars, IP addresses, URLs, user names, host names, tabs, timestamps that identify a personal environment, IDs, credentials, and unrelated applications. Keep a private original and label the public derivative as sanitized.
