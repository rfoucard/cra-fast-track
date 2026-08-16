# CRA Severe Incident Reporting Process

## Definitions

**Working days**: Monday to Friday, during normal working hours, excluding weekends and applicable public holidays. Time outside working hours does not count toward the deadline.

**Calendar hours**: All consecutive hours, 24 hours a day and 7 days a week, including nights, weekends, and public holidays. Time continues to count without interruption.

**Internal target**: A best-effort processing target for the Security Team, taking into account the voluntary nature of open-source contributions. It is an internal objective, not a mandatory deadline.

**Regulatory deadline**: A mandatory time limit established by the CRA for the open-source Stewards.

## Flowchart

```mermaid
flowchart TD

    A["<strong>Severe Incident report received</strong> \n(T_received)"] --> B["<strong>Record report, source, evidence and reception timestamp</strong>"]

    B --> C["<strong>Priority triage</strong> \n(internal target: ≤ T_received + 1 Working day)"]

    C --> D{"<strong>CRA-relevant service?</strong> (the affected service has been identified as capable of impacting the security of the TYPO3 CMS product)"}

    D -- "No" --> X["<strong>Return to security report handling process</strong> \n(Record findings and decision)"]

    D -- "Yes" --> E["<strong>Severe incident assessment</strong> \n(internal target: ≤ T_received + 2 Working days)"]

    E --> F["<strong>Security properties affected</strong> (the incident negatively affects or is capable of negatively affecting the availability, authenticity, integrity or confidentiality of sensitive or important data or functions)"]

    E --> G["<strong>Malicious code</strong> (the incident has led or is capable of leading to the introduction or execution of malicious code in TYPO3 CMS or in a user's network or information systems)"]

    F --> J{"<strong>Is at least one criterion satisfied?</strong>"}
    G --> J

    J -- "No" --> X
    J -- "Yes" --> L["<strong>CRA AWARENESS</strong> \n(T_CRA_awareness = earliest point at which sufficient information satisfies at least one severe incident criterion)"]

    L --> M["<strong>EARLY WARNING via ENISA SRP</strong> \n(without undue delay, ≤ T_CRA_awareness + 24 calendar hours)"]

    M --> N["<strong>INCIDENT NOTIFICATION via ENISA SRP</strong> \n(≤ T_CRA_awareness + 72 calendar hours)"]

    N --> X
```
