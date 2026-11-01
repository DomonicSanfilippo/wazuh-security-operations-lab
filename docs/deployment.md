# Deployment record

## Purpose

This record describes the verified baseline needed to understand the capstone lab. It is not intended to be a copy-and-paste production installation guide.

## Implemented components

| Component | Role | Status |
| --- | --- | --- |
| UTM on Mac mini | Host virtualization and isolated lab networking | Implemented |
| Ubuntu Server 24.04.5 LTS | Central Wazuh services | Implemented |
| Wazuh 4.14.9 | Manager, Indexer, Dashboard, Filebeat | Implemented |
| Ubuntu endpoint | Authentication and FIM validation source | Implemented |
| macOS host | Enrolled monitoring endpoint | Implemented |

## Deployment sequence used

1. Provision the Ubuntu Server virtual machine and install the Wazuh central components.
2. Verify service availability and authenticated dashboard access.
3. Deploy and enroll the Ubuntu endpoint agent.
4. Deploy and enroll the macOS agent.
5. Confirm that both agents are active in the dashboard.
6. Configure the Ubuntu endpoint's designated test directory for real-time FIM.
7. Verify collection of Ubuntu SSH/PAM authentication telemetry.
8. Run controlled positive and benign validation procedures.

## Reproduction safeguards

Use a separate, non-production environment. Replace every site-specific setting with a local value. Do not reuse dashboard credentials, agent keys, certificates, host names, address ranges, or the original VM disks. The sample FIM configuration is intentionally non-deployable until an operator selects an appropriate directory and validates the configuration in their own test environment.

## Operational checks

- Confirm Wazuh services are healthy before testing.
- Confirm each expected agent is active.
- Confirm the monitored directory exists and is writable only for the controlled test account.
- Record the expected test time in UTC before triggering an event.
- Review event details and supporting endpoint records before assigning a disposition.
