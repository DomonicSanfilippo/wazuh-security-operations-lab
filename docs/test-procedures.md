# Safe validation procedures

## Guardrails

Run these procedures only in an environment you own or are authorized to test. Use an isolated laboratory endpoint, synthetic test files, and a non-privileged test account where possible. Do not run these tests on employer, customer, school, or household production systems.

## File-integrity tests

1. Confirm that the designated test directory is the only location being evaluated.
2. Record the start time in UTC.
3. Create one harmless text file in the test directory.
4. Modify that same file with non-sensitive text.
5. Delete the file.
6. After each action, review the Wazuh alert details for the action, monitored path, rule, severity, and timestamp.
7. Retain only sanitized evidence; do not upload raw dashboard exports or user-specific paths.

Expected baseline behavior: the original lab generated alerts for creation (rule 554), modification (rule 550), and deletion (rule 553). Rule behavior may differ by version and configuration.

## Authentication tests

1. Use a laboratory Ubuntu endpoint with SSH enabled only within the controlled environment.
2. Perform controlled failed authentication attempts without using real passwords or accounts.
3. Review related Wazuh alerts and correlate them with the endpoint's authorized test record.
4. Do not treat multiple related alerts from one attempt as separate incidents.

Expected baseline behavior: the lab observed authentication alerts involving rules 5710 and 5503.

## Benign-control review

Perform ordinary authorized activities, such as a valid SSH login, read-only access outside the monitored directory, a directory listing, and file creation outside the monitored scope. Review the corresponding time window for incorrect authentication-failure or FIM alerts. This check supports tuning discussions but does not establish a false-positive rate.
