# Product Requirements Document (PRD) Standards

The PRD defines the **What** and the **Why** of the project. It serves as the authoritative source for user needs, business goals, and system behavior. To prevent information overload and enable focused reviews, the PRD is stored as a modular folder in `docs/PRD/`.

---

### 📂 Structure of the PRD Folder

Every project must initialize its PRD folder with the following structure:

1.  **`README.md`**: The entry point. Contains the Executive Summary, a high-level project description, the modular index, and the **Current Logical State** of the requirements.
2.  **`01_vision.md`**: Defines the product vision, the specific problem being solved, and the **User Personas** (who we are building for).
3.  **`02_user_stories.md`**: Contains detailed user-centric narratives. Every story must include specific **Acceptance Criteria** that define a successful outcome for the user.
4.  **`03_requirements.md`**:
    *   **Functional Requirements:** Specific capabilities the system must have.
    *   **Non-Functional Requirements:** Targets for performance, security, scalability, and reliability.
5.  **`04_context.md`**: Documents project constraints, known risks with mitigation plans, and the **Success Metrics (KPIs)** used to measure impact.

---

### 🎯 Key Principles

1.  **Problem Over Solution:** The PRD describes what the system should do, not how it should be built. It avoids technical implementation details, which belong in the RFD.
2.  **User-Centricity:** All requirements must be traceable back to a specific user need or business goal.
3.  **Atomic Documentation:** Each file represents a specific category of requirements. If a story changes, only the relevant file is updated, making changes easy to track and review in Git.
4.  **The "Lock" Rule:** While the PRD is a living document, requirements for a specific module are considered **Locked** once that module moves into the **"NOW"** column of the Roadmap. This prevents scope creep during the active development phase.

---

### 🛠 Maintenance & Changes
Because the PRD is the foundation for the Technical Design (RFD), changes must be handled with discipline:

*   **State Management:** The status lives in the **`README.md`**.
*   **The "Proposed" Trigger:** Any time a developer opens a Pull Request to change a content file, they **must** also update the `README.md` status to **Proposed**.
*   **The "Accepted" Flip:** The status is changed to **Accepted** only when the PR is approved, serving as the final confirmation before the **Squash and Merge** into `main`.
*   **Explain the "Why":** Use the **Pull Request description** to explain the rationale for the change. Do not add "Change Logs" or history sections inside the requirements files themselves.
*   **The Ripple Effect:** Once a PRD change is merged, you must immediately check the **Roadmap** and the **RFD** to ensure the technical design and strategic sequence remain aligned.
