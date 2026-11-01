# Roadmap

## Version 1.0 - Capstone baseline

**Implemented and validated.** Central Wazuh deployment; Ubuntu and macOS agent enrollment; Ubuntu authentication and file-integrity telemetry; controlled validation; documented alert investigation.

## Version 2.0 - Detection engineering

**Planned.** Add custom Wazuh rules with a repeatable test case for each rule, negative controls, ATT&CK mappings where substantiated, and a review of expected noise. No custom rules are represented as complete in Version 1.

## Version 3.0 - Isolated Cowrie telemetry

**Planned, subject to a security review.** Deploy Cowrie only in a separate isolated environment with no route to home or production systems. Use synthetic interactions initially. Ingesting Cowrie events into Wazuh and any public exposure are not part of Version 1.

## Version 4.0 - Network telemetry

**Planned.** Evaluate a safe traffic-observation design and correlate controlled network IDS observations with endpoint telemetry.

## Version 5.0 - Repeatability and measurement

**Planned.** Add scripted checks for rule definitions and a measured, documented test suite. Any detection coverage, latency, or false-positive metrics will be published only after an explicit measurement method and results are available.
