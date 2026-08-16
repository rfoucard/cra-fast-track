# Security Reporting Process

## Flowchart

```mermaid
flowchart TD

    A["Security report received via security@typo3.org"] --> B["Report imported into dedicated OTOBO instance"]
    B --> C["Immediate notification sent to Security Team"]
    C --> AE{"Does the report indicate potential active exploitation?"}
    AE -- "Yes" --> AEP["Active Exploitation Assessment Process"](./actively-exploited-vulnerability-process.md)
    AE -- "No" --> D["First inspection and triage (usually within 24–48 hours, potentially longer on weekends and holiday periods)"]
    AEP --> D

    D --> E{"Triage result"}

    E -- "Rejected" --> R["Inform reporter that the report was rejected"]

    E -- "Core" --> G["Inform reporter that the report was accepted and categorized as Core"]
    E -- "Extension" --> H["Inform reporter that the report was accepted and categorized as Extension"]
    E -- "Infrastructure" --> I["Inform reporter that the report was accepted and categorized as Infrastructure"]

    G --> G1["Create internal ticket on forge.typo3.org and notify relevant Core Development Team members"]
    H --> H1["Inform extension maintainer by email"]
    I --> I1["Forward confirmed vulnerability to TYPO3 Server Team or TYPO3 GmbH Services Team"]

    G1 --> J["Corresponding team or maintainer works on a fix"]
    H1 --> J
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
```
