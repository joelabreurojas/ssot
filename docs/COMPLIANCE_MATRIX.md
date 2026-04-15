# 🛡️ ISO Compliance & Standards Mapping

This document maps our engineering Single Source of Truth (SSOT) to international ISO standards. It serves as a continuous verification guide for internal audits, enterprise compliance, and vendor assessments.

We operate on the **PDCA (Plan-Do-Check-Act)** cycle. Our documentation is not static; it is actively enforced by our CI/CD pipelines and architectural gates.

---

## 1. ISO 9001:2015 (Quality Management System)
*Focus: Traceability, continuous improvement, and consistent delivery of value.*

| ISO Clause | SSOT Implementation | Verification Artifact |
| :--- | :--- | :--- |
| **7.1.6 Org. Knowledge** | Preserving "Tribal Knowledge" | `docs/ADR/` & `docs/RFD/` |
| **7.2 Competence** | Standardized Dev Onboarding | Closed `Onboarding` GitHub Issues |
| **7.5 Documented Info.** | Docs-as-Code, Version Control | Git History, Squash & Merge logs |
| **8.2 Requirements Review** | Product Requirements Document | `docs/PRD/02_user_stories.md` |
| **8.3 Design & Dev.** | Request for Design, JIT Eng. | `docs/RFD/`, `docs/VIEWS/` |
| **8.7 Nonconforming Outputs**| **Hard Gate:** CI/CD Pipeline | GitHub Rulesets (Merge Blocked) |
| **9.1 Monitoring & Measure** | APM, Error Tracking, Health Probes | `RFD/05_ops_security_quality.md` |
| **9.2 Internal Audit** | Peer Review Compliance Checks | `pull_request_template.md` Checklists |
| **9.3 Management Review** | Async "State of the Project" | Closed `type:chore` Quarterly Issues |
| **10.2 Corrective Action** | Blameless Culture & Post-Mortems | PR Comments, Updated CI Tests |

---

## 2. ISO/IEC 27001:2022 (Information Security - ISMS)
*Focus: Confidentiality, Integrity, Availability, and Risk Management across distributed teams.*

| ISO Annex A Control | SSOT Implementation | Verification Artifact |
| :--- | :--- | :--- |
| **6.1 Actions to Address Risks**| Embedded Risk Register & KPIs | `docs/PRD/04_context.md` |
| **A.5.8 InfoSec in Project Mgt.**| Security-first Architecture | `docs/RFD/05_ops_security_quality.md`|
| **A.5.15 Access Control (IAM)** | OIDC, RBAC, Quarterly Audits | GitHub Org Audit Logs |
| **A.5.21 Supplier Relationships**| 3rd-Party Vetting & SLA Limits | `docs/RFD/01_structure.md` |
| **A.5.30 ICT Readiness (BC/DR)**| Backup & Recovery Automation | `ci.yml` logs, Restore Scripts |
| **A.8.10 Information Deletion** | Data Lifecycle & Archival Strategy | `docs/RFD/02_data_model.md` |
| **A.8.12 Data Leakage Prevention**| Secret Scanning, Automated Hooks | GitHub Advanced Security |
| **A.8.25 Secure Dev Lifecycle** | DevSecOps, Shift-Left, PoLP | `WORKFLOW/05_security_standards.md`|
| **A.8.28 Secure Coding** | **Hard Gate:** Linter, SAST, CodeQL| `.github/workflows/ci.yml` |

---

## 3. ISO/IEC 25000 (Software Quality - SQuaRE)
*Focus: Measuring the actual software characteristics to ensure it is fit for purpose.*

| Quality Characteristic | SSOT Implementation | Verification Artifact |
| :--- | :--- | :--- |
| **Functional Suitability** | Acceptance Criteria & Traceability | `docs/PRD/`, `issues/` templates |
| **Performance Efficiency** | Latency Budgets & Ceilings | `docs/PRD/03_requirements.md` (SLOs) |
| **Compatibility/Portability** | Containerization, E2E Cross-Browser| `Dockerfile`, E2E Test Configs |
| **Usability** | AI-Driven Prompting, State Specs | `docs/VIEWS/00_template.md` |
| **Reliability** | Timeouts, Circuit Breakers, Fallbacks| `WORKFLOW/04_architecture_api.md` |
| **Security** | Threat Modeling, Blast Radius Check | `docs/RFD/05_ops_security_quality.md`|
| **Maintainability** | Clean Arch. & Complexity Analysis | `WORKFLOW/16_commit_standards.md`, CodeQL |

---
*Audit Note: To verify the execution of these standards, auditors should inspect the Git History of any `docs/ADR/` file to observe the proposal, peer-review, and approval lifecycle, as well as the GitHub Actions tab to verify that 'Nonconforming Outputs' are physically blocked from reaching the production branch.*
