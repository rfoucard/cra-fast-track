# CRA Severe Incident Reporting Process

## Definitions

**Working days**: Monday to Friday, during normal working hours, excluding weekends and applicable public holidays. Time outside working hours does not count toward the deadline.

**Calendar hours**: All consecutive hours, 24 hours a day and 7 days a week, including nights, weekends, and public holidays. Time continues to count without interruption.

**Internal target**: A best-effort processing target for the Security Team, taking into account the voluntary nature of open-source contributions. It is an internal objective, not a mandatory deadline.

**Regulatory deadline**: A mandatory time limit established by the related regulation.

## Flowchart

```mermaid
flowchart TD

    A["<strong>Severe&nbsp;Incident&nbsp;report&nbsp;received</strong> \n(T_received)"] --> B["<strong>Record&nbsp;report,&nbsp;source, evidence and reception timestamp</strong>"]

    B --> C["<strong>Priority triage</strong> \n(internal&nbsp;target:&nbsp;≤&nbsp;T_received + 1 Working day)"]

    C --> D{"<strong>CRA-relevant service?</strong> (the&nbsp;affected&nbsp;service&nbsp;has&nbsp;been identified as capable of impacting the security of the TYPO3 CMS product)"}

    D -- "No" --> X["<strong>Return&nbsp;to&nbsp;security&nbsp;report handling&nbsp;process</strong> \n(Record findings and decision)"]

    D -- "Yes" --> E["<strong>Severe&nbsp;incident&nbsp;assessment</strong> \n(internal&nbsp;target:&nbsp;≤&nbsp;T_received + 2 Working days)"]

    E --> F["<strong>Security&nbsp;properties&nbsp;affected</strong> (the incident negatively affects or is capable of negatively affecting the availability, authenticity, integrity or confidentiality of sensitive or important data or functions)"]

    E --> G["<strong>Malicious&nbsp;code</strong> (the&nbsp;incident&nbsp;has&nbsp;led&nbsp;or&nbsp;is&nbsp;capable of leading to the introduction or execution of malicious code in TYPO3 CMS or in a user's network or information systems)"]

    F --> J{"<strong>Is at least one&nbsp;criterion&nbsp;satisfied?</strong>"}
    G --> J

    J -- "No" --> X
    J -- "Yes" --> L["<strong>CRA AWARENESS</strong> \n(T_CRA_awareness&nbsp;=&nbsp;earliest&nbsp;point at which sufficient information satisfies at least one severe incident criterion)"]

    L --> M["<strong>EARLY WARNING via ENISA SRP</strong> \n(≤&nbsp;T_CRA_awareness&nbsp;+&nbsp;24&nbsp;calendar&nbsp;hours)"]

    M --> N["<strong>INCIDENT NOTIFICATION via ENISA SRP</strong> \n(≤&nbsp;T_CRA_awareness&nbsp;+&nbsp;72&nbsp;calendar&nbsp;hours)"]

    N --> O["<strong>FINAL REPORT via ENISA SRP</strong> \n((≤&nbsp;T_CRA_incident_notification&nbsp;+&nbsp;1&nbsp;month))"]

    O --> X

    L --> U["<strong>INFORM USERS</strong> \n(if&nbsp;necessary,&nbsp;after&nbsp;becoming&nbsp;aware, without undue delay)"]

```
