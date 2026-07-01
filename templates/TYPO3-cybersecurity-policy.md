# Cybersecurity Policy
## Open Source Software Steward
### TYPO3 Association, Inc.

**EU Cyber Resilience Act (Regulation 2024/2847) Compliant**

**Based on the [OWASP CRA Template](https://github.com/OWASP/CRA/blob/main/oss-steward-cybersecurity-policy.md), licensed under CC BY 4.0. Modified by the TYPO3 Association.**

---

| Document Information | |
|---------------------|---|
| **Version:** | 1.0 |
| **Effective Date:** | 11/09/2026 |
| **Last Review:** | 01/07/2026 |
| **Next Review:** | [Date + 1 year] |
| **Owner:** | [TYPO3 Association Security Team / Compliance Officer] |
| **Approved By:** | [TYPO3 Association Board] |

---

## 1. Purpose and Scope

### 1.1 Purpose

This Cybersecurity Policy establishes the security framework for TYPO3 Association, Inc. in its role as an Open Source Software Steward under the EU Cyber Resilience Act (Regulation 2024/2847, Article 24). This policy is designed to:

- Foster the development of secure products with digital elements
- Enable effective handling of vulnerabilities by project developers
- Promote voluntary vulnerability reporting within the open source community
- Ensure timely sharing of discovered vulnerabilities
- Facilitate cooperation with market surveillance authorities

### 1.2 Scope

This policy applies to all open source projects stewarded by TYPO3 Association, Inc. that qualify as products with digital elements intended for commercial activities under the CRA. This includes:

- The TYPO3 CMS Core project
- All committers, contributors, and maintainers of this project
- Infrastructure and systems used for development of if this project

### 1.3 Legal Basis

This policy fulfills the requirements of **Article 24(1)** of Regulation (EU) 2024/2847 (Cyber Resilience Act), which requires open source software stewards to put in place and document in a verifiable manner a cybersecurity policy.

---

## 2. Security Organizational Structure

### 2.1 Steward Security Team

The Steward Security Team is responsible for coordinating security activities across all stewarded projects. Responsibilities include:

- Triaging and redirecting vulnerability reports to appropriate project teams
- Providing guidance on vulnerability management best practices
- Coordinating disclosure timelines across projects
- Maintaining relationships with CSIRTs and regulatory authorities
- Managing the single reporting platform communications (Article 14/16)

**Contact:** security@typo3.org

### 2.2 Project Security Team

The stewarded project maintains a Project Security Team responsible for:

- Receiving and assessing vulnerability reports for their project
- Developing and testing security patches
- Coordinating disclosure with the Steward Security Team
- Publishing security advisories
- Maintaining project-specific security documentation (SECURITY.md)

---

## 3. Vulnerability Management

### 3.1 Vulnerability Reporting Channels

Vulnerabilities can be reported through the following channels: 

- **Email:** security@typo3.org (encrypted with PGP preferred)
- **GitHub Security Advisories** (for projects hosted on GitHub)
- **Project-specific mechanisms** as documented in SECURITY.md files
- **CSIRT/ENISA coordination** (incoming notifications)

### 3.2 Vulnerability Handling Process

#### 3.2.1 Receipt and Acknowledgment

- All vulnerability reports acknowledged within **48 hours**
- Initial triage completed within **5 business days**
- Reporter kept informed of progress throughout the process

#### 3.2.2 Assessment and Prioritization

- Severity assessed using **CVSS 4.0** methodology
- Impact analysis considering affected users and downstream dependencies
- Assignment to appropriate Project Security Team

#### 3.2.3 Remediation

**Target remediation timelines based on severity:**

| Severity | CVSS Score | Target Timeline |
|----------|------------|-----------------|
| Critical | 9.0–10.0 | 7 days |
| High | 7.0–8.9 | 30 days |
| Medium | 4.0–6.9 | 90 days |
| Low | 0.1–3.9 | Next regular release |

Additional requirements:
- Security patches developed and tested in private branches
- Fixes reviewed by at least one other security-aware committer

#### 3.2.4 Disclosure

- Coordinated disclosure following **ISO/IEC 29147** principles
- Standard embargo period: **90 days maximum**
- Security advisories published at time of fix release
- CVE identifiers requested for significant vulnerabilities

---

## 4. Mandatory Reporting to Authorities

In accordance with **Article 24(3)** referencing **Article 14**, the following reporting obligations apply:

### 4.1 Actively Exploited Vulnerabilities

When the steward becomes aware of an actively exploited vulnerability in a stewarded product (to the extent involved in development):

| Report Type | Deadline |
|-------------|----------|
| Early warning notification | Within **24 hours** of awareness |
| Vulnerability notification | Within **72 hours** with general information |
| Final report | Within **14 days** of corrective measure availability |

Reports submitted via the **ENISA Single Reporting Platform** (Article 16) to the designated CSIRT coordinator.

### 4.2 Severe Security Incidents

For severe incidents affecting network and information systems provided by the steward for development (Article 14(3) and (8)):

- Immediate internal escalation to Steward Security Team
- Notification to CSIRT and ENISA per Article 14 timelines
- Notification to affected users with risk mitigation measures

### 4.3 Designated CSIRT

The TYPO3 Association is established in Switzerland.

Until further regulatory guidance is issued regarding the designation of a coordinating CSIRT for Open Source Stewards established outside the European Union, the TYPO3 Association designates the following CSIRT as its primary coordinator. This designation is based on the fact that Germany represents the largest concentration of the TYPO3 ecosystem, including its commercial ecosystem and user base within the European Union.

> **CERT-Bund (BSI)**  
> Federal Office for Information Security (BSI)  
> https://www.bsi.bund.de/EN

The TYPO3 Security Team supports both the TYPO3 Association and TYPO3 GmbH. Using the same designated CSIRT promotes a consistent vulnerability reporting process, facilitates coordination between the Steward and the Manufacturer, and reduces the administrative burden associated with maintaining separate reporting procedures.

This designation will be reviewed if future guidance issued by the European Commission, ENISA, or the relevant national authorities provides a different interpretation or identifies another coordinating CSIRT.

---

## 5. Secure Development Practices

### 5.1 Security Requirements for Projects

Stewarded projects are encouraged to implement the following security practices:

- Maintain a **SECURITY.md** file with vulnerability reporting instructions
- Enable dependency scanning and automated vulnerability detection
- Require code review for all changes
- Sign releases with verified cryptographic signatures
- Maintain a **Software Bill of Materials (SBOM)** for releases
- Document security considerations in project documentation

### 5.2 Infrastructure Security

The steward maintains secure infrastructure for project development:

- Multi-factor authentication required for all privileged access
- Regular security assessments of hosted infrastructure
- Incident response procedures for infrastructure compromises
- Backup and disaster recovery capabilities

---

## 6. Vulnerability Information Sharing

### 6.1 Community Sharing

In accordance with **Article 24(1)**, we promote sharing of discovered vulnerabilities within the open source community through:

- Publication of security advisories in standardized formats (OSV, CSAF)
- Participation in coordinated disclosure with downstream projects
- Contribution to public vulnerability databases
- Sharing of security best practices and lessons learned

### 6.2 Voluntary Reporting (Article 15)

We encourage and facilitate voluntary reporting of:

- Vulnerabilities discovered in stewarded projects
- Cyber threats that could affect risk profiles of products
- Security incidents and near-misses

---

## 7. Cooperation with Market Surveillance Authorities

In accordance with **Article 24(2)**, TYPO3 Association, Inc. commits to:

- Cooperate with market surveillance authorities upon request
- Work to mitigate cybersecurity risks in stewarded products
- Provide this policy documentation upon reasoned request
- Make documentation available in the requested language where feasible
- Respond to authority inquiries in a timely manner

---

## 8. Records and Documentation

To demonstrate **verifiable compliance**, the following records are maintained:

- Vulnerability tracking records (reports received, actions taken, timelines)
- Security advisory publication records
- CSIRT/ENISA notification records
- Policy review and update history
- Security training records for team members

**Retention period:** Minimum of 5 years or as required by applicable law.

---

## 9. Policy Review and Updates

This policy is reviewed and updated:

- **Annually** at minimum
- Following significant security incidents
- When regulatory requirements change
- When organizational structure or processes change materially

All updates are documented with version history and approved by [Approving Authority].

---

## 10. References

- **Regulation (EU) 2024/2847** (Cyber Resilience Act)
- **ISO/IEC 29147:2018** (Vulnerability Disclosure)
- **ISO/IEC 30111:2019** (Vulnerability Handling Processes)
- **CVSS 4.0 Specification** (First.org)
- **OpenSSF Best Practices**
- **CRA Open Source Steward Guidance** (ORC Working Group)

---

## Approval

**Approved:**

_______________________________________

**[Name, Title]**

**Date:** ________________

---

## Appendix A: SECURITY.md Template for Projects

Projects stewarded by TYPO3 Association, Inc. should include a SECURITY.md file with the following information:

```markdown
# Security Policy

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| x.x.x   | :white_check_mark: |
| x.x.x   | :x:                |

## Reporting a Vulnerability

Please report security vulnerabilities to:

- **Email:**security@typo3.org
- **PGP Key:** [Key ID or link]

Or use GitHub Security Advisories if available for this repository.

### What to include:
- Description of the vulnerability
- Steps to reproduce
- Affected versions
- Any potential mitigations you've identified

### What to expect:
- Acknowledgment within 48 hours
- Regular updates on remediation progress
- Credit in the security advisory (if desired)

## Disclosure Policy

We follow coordinated disclosure with a standard 90-day timeline.
```

---

## Appendix B: CRA Reporting Timeline Quick Reference

### For Actively Exploited Vulnerabilities (Article 14):

```
Day 0: Become aware of actively exploited vulnerability
       |
       v
Day 1: Early warning to CSIRT + ENISA (within 24h)
       - Indicate affected Member States (if known)
       |
       v
Day 3: Vulnerability notification (within 72h)
       - General information about product
       - Nature of exploit and vulnerability
       - Corrective/mitigating measures taken
       - Measures users can take
       - Sensitivity indication
       |
       v
Day X: Fix released
       |
       v
Day X+14: Final report (within 14 days of fix)
          - Vulnerability description, severity, impact
          - Information on malicious actors (if available)
          - Remediation/mitigation details
```

### Reporting Platform

All notifications via **ENISA Single Reporting Platform** (Article 16)

---

## Appendix C: Key CRA Article 24 Text Reference

> **Article 24 – Obligations of open-source software stewards**
>
> 1. Open-source software stewards shall put in place and document in a verifiable manner a cybersecurity policy to foster the development of a secure product with digital elements as well as an effective handling of vulnerabilities by the developers of that product. That policy shall also foster the voluntary reporting of vulnerabilities as laid down in Article 15 by the developers of that product and take into account the specific nature of the open-source software steward and the legal and organisational arrangements to which it is subject. That policy shall, in particular, include aspects related to documenting, addressing and remediating vulnerabilities and promote the sharing of information concerning discovered vulnerabilities within the open-source community.
>
> 2. Open-source software stewards shall cooperate with the market surveillance authorities, at their request, with a view to mitigating the cybersecurity risks posed by a product with digital elements qualifying as free and open-source software. Further to a reasoned request from a market surveillance authority, open-source software stewards shall provide that authority, in a language which can be easily understood by that authority, with the documentation referred to in paragraph 1, in paper or electronic form.
>
> 3. The obligations laid down in Article 14(1) shall apply to open-source software stewards to the extent that they are involved in the development of the products with digital elements. The obligations laid down in Article 14(3) and (8) shall apply to open-source software stewards to the extent that severe incidents having an impact on the security of products with digital elements affect network and information systems provided by the open-source software stewards for the development of such products.
