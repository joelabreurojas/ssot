# Product Requirements Document (PRD) Standards

The PRD defines the **What** and the **Why** of the project. It focuses on user needs, business goals, and system behavior. To prevent information overload, the PRD is stored as a modular folder in `docs/PRD/`.

---

### 📂 Structure of the PRD Folder

Every project must initialize its PRD folder with the following structure:

1.  **`README.md`**: The entry point. Contains the Executive Summary, a high-level project description, and the table of contents for the PRD module.
2.  **`01_vision.md`**: Defines the product vision, the problem being solved, and the target audience (User Personas).
3.  **`02_user_stories.md`**: Contains detailed user-centric narratives. Each story must include specific **Acceptance Criteria** that define a successful outcome for the user.
4.  **`03_requirements.md`**:
    *   **Functional Requirements:** Specific capabilities the system must have.
    *   **Non-Functional Requirements:** Targets for performance, security, scalability, and reliability.
5.  **`04_context.md`**: Documents project constraints, potential risks with mitigation plans, and the success metrics (KPIs) used to measure the project's impact.

---

### 🎯 Key Principles

1.  **Problem Over Solution:** The PRD describes what the system should do, not how it should be built. It avoids technical implementation details, which belong in the RFD.
2.  **User-Centricity:** All requirements should be traceable back to a specific user need or business goal.
3.  **Atomic Documentation:** Each file represents a specific category of requirements. If a requirement changes, only the relevant file is updated, making the change easy to track and review in Git.
4.  **The "Lock" Rule:** The PRD is considered a "Living Document" but must reach a stable, approved state before the Technical Specification (RFD) phase begins.

---

### 🛠 Maintenance & Changes
Because the PRD is the foundation for the Technical Design (RFD), changes must be handled with discipline:

*   **Logical States:** To maintain simplicity, the state is handled in the **`README.md`** and it will change from **Proposed** to **Accepted** before the **Squash and Merge** with main.
*   **How to change:** If a requirement evolves, update the relevant `.md` file in `docs/PRD/` via a **Pull Request**.
*   **Explain the "Why":** Use the **Pull Request description** to explain the rationale for the change. Do not add "Change Logs" inside the requirements files themselves.
*   **The Ripple Effect:** Once a PRD change is merged, you must immediately check the **RFD** to see if the technical design needs to be updated to match the new requirements.
