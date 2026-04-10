# Community & Organization Standards

High-quality software is built by high-quality communities. These standards define the "human interface" of the project, ensuring that collaboration is professional, transparent, and welcoming to all contributors. 

---

### 1. Community Profile
We ensure our community health profile is maintaining by the following files at the root of the repository (or in the `.github/` folder):

*   **`README.md`**: The executive summary and onboarding guide.
*   **`CONTRIBUTING.md`**: Step-by-step instructions for environment setup, branching, and PR submission.
*   **`CODE_OF_CONDUCT.md`**: The behavioral expectations for a safe, inclusive environment (e.g., Contributor Covenant).
*   **`LICENSE`**: The legal terms under which the software is distributed.
*   **`SECURITY.md`**: The formal policy for reporting vulnerabilities privately.
*   **Issue & PR Templates**: Automated forms for bug reports, features, and code reviews.

### 2. Governance (`GOVERNANCE.md`)
This document defines the decision-making power structure within the project.
*   **Purpose:** To provide transparency on who makes final decisions regarding architecture, product roadmap, and security.
*   **Standard:** It must explicitly define roles:
    *   **Project Owner:** The final authority on product and technical stalemates.
    *   **Maintainers:** Authorized reviewers and core contributors.
    *   **Contributors:** Everyone who helps improve the project.

### 3. Discussions vs. Issues
To keep our Kanban board clean and focused purely on execution, we strictly separate conversation from action:
*   **Discussions (GitHub Discussions):** Used for Q&A, open-ended feature ideas, architecture brainstorming, and community announcements.
*   **Issues:** Used *only* for actionable tasks with a clear "Definition of Done," an Execution Order, and assignment to a Milestone. (If a Discussion results in a decision to build something, an Issue is created to track the work).

### 4. Wikis vs. Docs-as-Code
*   **Docs-as-Code (`docs/`):** All Product Requirements (PRD), Technical Specs (RFD), and Architecture Decisions (ADR) must live directly in the repository. This ensures they are version-controlled alongside the code they describe.
*   **Wikis (Optional):** If the project requires long-form user manuals, tutorials, or marketing documentation that does not need strict version control synced to code releases, the repository Wiki should be utilized.

### 5. Template Repositories & Organization Management
For teams managing multiple services or microservices:
*   **Template Repository:** This SSOT repository should be configured in GitHub as a "Template Repository." This allows new projects to be initialized instantly with all workflows, labels, and community standards pre-configured.
*   **Organization Management:** Access control (RBAC), SSH key requirements, and OIDC (OpenID Connect) configurations for cloud deployments should be managed at the GitHub Organization level, rather than on a per-repository basis, to ensure uniform security compliance.
