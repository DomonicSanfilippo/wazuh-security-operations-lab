# Case 001 - Authorized laboratory file deletion

## Classification

**Disposition: authorized test activity; not a confirmed security incident.**

## Trigger

During controlled file-integrity validation, Wazuh generated a level 7 file-deletion alert using rule 553. The alert identified the Ubuntu test endpoint and a file in the designated laboratory FIM directory.

## Investigation approach

1. Review the alert's timestamp, endpoint, rule, severity, decoder, and affected path.
2. Compare the record with the documented laboratory test sequence and corresponding terminal record.
3. Confirm whether the action was planned and authorized.
4. Record a disposition and state whether containment or recovery is required.

## Finding

The alert matched the intentional deletion of a synthetic test file during the approved validation sequence. The activity was recorded at approximately 02:43:18 UTC on October 29, 2026. No containment or recovery action was required.

## Detection context

The capstone report recorded the `syscheck_deleted` decoder and ATT&CK mappings T1070.004 and T1485 on the observed alert. These mappings describe the alert context; they do not establish adversary behavior in this laboratory case.

## If the activity had been unauthorized

The next steps would be to review related endpoint records, identify the responsible account or process where feasible, assess affected data and business impact, preserve relevant evidence, and escalate under the applicable incident-response procedure. Any containment must be authorized and appropriate to the environment.

## Lessons learned

The case demonstrates why an alert is an input to an investigation, not a conclusion. Centralized telemetry supported prompt review, but the final classification required correlation with the known test activity.
