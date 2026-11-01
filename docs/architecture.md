# Architecture

## Implemented topology

The laboratory ran on an Apple Mac mini using UTM virtualization. A central Ubuntu Server 24.04.5 LTS virtual machine hosted Wazuh Manager, Wazuh Indexer, Wazuh Dashboard, and Filebeat. A second Ubuntu virtual machine and the macOS host were enrolled as Wazuh agents.

The Ubuntu endpoint supplied the validated telemetry for this project:

- SSH and PAM authentication events through system logging.
- Real-time file-integrity events for a designated laboratory test directory.

The macOS agent was enrolled and confirmed active, but this version of the public portfolio does not claim a distinct macOS detection test.

## Data flow

1. Endpoint agents collect configured telemetry.
2. Agents send events to Wazuh Manager over the laboratory network.
3. Wazuh Manager applies decoders and rules, then generates alerts when conditions are met.
4. Filebeat forwards alert data to Wazuh Indexer.
5. Wazuh Dashboard provides agent-health, threat-hunting, and alert-investigation views.

## Boundaries and constraints

- The implementation used one monitoring server; high availability and automated recovery were not implemented.
- The lab was a controlled, shared-NAT virtual environment, not a production network.
- Network addresses, endpoint names, user names, and management URLs are excluded from public documentation.
- The architecture does not include EDR, SOAR, threat-intelligence enrichment, external exposure, honeypot telemetry, or network IDS.
