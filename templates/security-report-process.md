# Security Report handling Process

## Definitions

**Working days**: Monday to Friday, during normal working hours, excluding weekends and applicable public holidays. Time outside working hours does not count toward the deadline.

**Internal target**: A best-effort processing target for the Security Team, taking into account the voluntary nature of open-source contributions. It is an internal objective, not a mandatory deadline.

## Flowchart

```mermaid
flowchart TD

    A["Security report received via security@typo3.org (T_received)"] --> B["Report immediately imported into dedicated OTOBO instance"]
    B --> C["Immediate notification sent to Security Team"]
    C --> D["First inspection and triage (internal target: ≤ T_received + 2 Working days)"]

    D --> E{"Triage result"}

    E -- "Rejected" --> R["Inform reporter that the report was rejected"]
    E -- "Extension" --- EX[" "]
    EX --- EXT[" "]
    EXT --> H["Inform reporter that the report was accepted and categorized as Extension"]

    E -- "Core" --> F{"Does the report indicate potential active exploitation?"}
    F -- "Yes" --> FP["<a href="https://github.com/rfoucard/cra-fast-track/blob/main/templates/actively-exploited-vulnerability-process.md">Active Exploitation Assessment Process"</a>] 
    F -- "No" --> G["Inform reporter that the report was accepted and categorized as Core"]
    FP --> G

    E -- "Service / Infrastructure" --> SI{"Does the report concern a CRA-relevant service?"}
    SI -- "Yes" --> SIP["Severe Incident Assessment Process"]
    SI -- "No" --> I["Inform reporter that the report was accepted and categorized as Service / Infrastructure"]
    SIP --> I

    H --> H1["Inform extension maintainer by email"]
    G --> G1["Create internal ticket on forge.typo3.org and notify relevant Core Development Team members"]
    I --> I1["Forward confirmed vulnerability to TYPO3 Server Team or TYPO3 GmbH Services Team"]

    H1 --> J["Corresponding team or maintainer works on a fix"]
    G1 --> J
    I1 --> J

    J --> K["Security Team supports in an advisory role (exceptionally provides patches when needed)"]
    K --> L["Security Team reviews fix or patch"]
    L --> M{"Vulnerability resolved?"}

    M -- "No" --> J
    M -- "Yes (Core / Extension)" --> N["Coordinate potential release date with development team or maintainer"]
    M -- "Yes (Infrastructure)" --> IA["Infrastructure vulnerability handling completed"]

    N --> O["Security Team prepares Security Advisory"]
    O --> P["Security Team requests CVE and prepares CVE JSON details"]

    P --> Q["Release day"]

    Q --> S["Release new version of vulnerable component"]
    Q --> T["Publish Security Advisory on typo3.org/security"]
    Q --> U["Publish CVE details on cve.org"]
    Q --> V["Send announcements via email and Slack"]
    Q --> W["Optionally publish FriendsOfPHP security-advisories entry"]

    S --> X["Monitor public issue trackers manually for potential regressions"]
    T --> X
    U --> X
    V --> X
    W --> X

    X --> Y["Inform reporter about the fix"]
    Y --> Z["Inform reporter about potential TYPO3 Bug Bounty reward"]
    Z --> AA["Reward paid from corresponding team budget"]

    style F fill:#fff3cd
    style FP fill:#fff3cd
    style SI fill:#fff3cd
    style SIP fill:#fff3cd
    style EX fill:none,stroke:none
    style EXT fill:none,stroke:none
```
