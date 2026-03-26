# Request for Design (RFD) Standards

The RFD is the **Technical Specification**. It serves as the authoritative source for the project's architecture, data contracts, and implementation strategy. To ensure modularity and high-quality technical reviews, the RFD is stored as a modular folder in `docs/RFD/`.

---

### 📂 Structure of the RFD Folder

Every project must initialize its RFD folder with the following structure:

1.  **`README.md`**: The entry point. Contains the **High-Level Architecture** (using Mermaid diagrams) and the **Current Logical State** of the design.
2.  **`01_structure.md`**: Defines the architectural pattern (e.g., MVC, Hexagonal), the directory tree, and the internal/external dependencies.
3.  **`02_data_model.md`**: Details the storage strategy, data dictionary, entity relationships (Mermaid ERD), and indexing strategy.
4.  **`03_interface.md`**: Defines communication protocols (REST, GraphQL, etc.), data contracts (payload shapes), and boundary security.
5.  **`04_logic.md`**: Outlines core domain services, business rules, and asynchronous background jobs.
6.  **`05_ops_and_security.md`**: Documents the testing strategy, deployment pipeline, monitoring, and secrets management.

---

### 🏗️ Key Principles

1.  **Diagrams-as-Code:** We use **Mermaid.js** for all architectural and data diagrams. This ensures they are version-controlled, searchable, and produce clean "diffs" in Pull Requests.
2.  **Just-In-Time (JIT) Design:** Technical specifications are only authored for modules currently in the **"NOW"** column of the Roadmap. This prevents design rot and wasted effort.
3.  **Architecture over Implementation:** Focus on signatures, contracts, and flow. Avoid pasting large blocks of code; use pseudocode or high-level descriptions instead.
4.  **The Source of Truth:** If the code and the RFD disagree, the RFD is the authority. The code must be fixed to match the design, or the design must be formally updated via a PR.

---

### 🛠️ Maintenance & Changes

Technical designs must evolve alongside the project's needs:

*   **State Management:** The status (Proposed/Accepted) lives in the folder's **`README.md`**.
*   **The "Proposed" Trigger:** Any time a technical change is made to a content file (e.g., adding a field to `02_data_model.md`), the developer **must** also update the `README.md` status to **Proposed**.
*   **The "Accepted" Flip:** The status is changed back to **Accepted** only when the PR is approved, signifying technical consensus before the **Squash and Merge**.
*   **Explain the "Why":** Use the **Pull Request description** to explain the technical rationale for architectural pivots or design choices.
*   **Cross-Sync:** If a technical constraint found during the RFD phase requires a change in product behavior, the **PRD** must be updated and approved first.
