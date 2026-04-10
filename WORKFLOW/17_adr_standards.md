# Architecture Decision Records (ADR) Standards

An ADR is a document that captures a **significant technical decision** made during the development process, including the context and the consequences. 

While the RFD provides the initial plan, ADRs record the **pivots and refinements** that happen once coding begins. This ensures that future developers understand the rationale behind the current state of the system.

---

### 📂 The ADR Directory

All records are stored in `docs/ADR/` to serve as a chronological history of the project's evolution.

1.  **File Naming:** Use a sequential three-digit prefix followed by a slug.
    *   *Format:* `NNN_short_description.md`
    *   *Example:* `001_use_postgresql_over_sqlite.md`
2.  **Immutability:** Once an ADR is "Accepted" and merged into `main`, it is a permanent record. If a later decision changes a previous one, a **new** ADR is written, and the old one is marked as "Superseded."

---

### 📝 Key Standards (The Anatomy of an ADR)

Every ADR must follow the `000_template.md` (found in `EXAMPLES/docs/ADR/`) and include:

1.  **Status:**
    *   **Proposed:** The decision is currently under review in a Pull Request.
    *   **Accepted:** The decision has been approved and merged into `main`.
    *   **Superseded:** This decision has been replaced by a later ADR.
2.  **Context:** What is the specific problem, requirement, or constraint that forced this decision?
3.  **Decision:** What is the chosen solution? Use clear, affirmative language.
4.  **Rationale:** Why is this the best choice among the alternatives? What data or research supports this?
5.  **Consequences:** What are the trade-offs? What gets easier, and what gets harder? What must other developers be aware of now?

---

### 🛠️ When to write an ADR

Do not write an ADR for every small change. Reserve them for decisions that:
*   Introduce a new major dependency or library.
*   Change the data model or API contracts defined in the RFD.
*   Select one technical path over another when both have significant trade-offs.
*   Affect the project's security, performance, or scalability posture.

---

### 🚀 Workflow Integration (The Status Flip)

To ensure the repository history is accurate and the `main` branch always reflects the truth, we follow this sequence:

1.  **Propose:** The developer creates the ADR with `Status: Proposed` in a feature branch.
2.  **Discuss:** The team reviews the technical choice within the Pull Request.
3.  **Approve:** The reviewer approves the PR once the decision is validated.
4.  **Flip:** After approval, but **BEFORE** merging, the developer updates the status text to `Accepted`.
5.  **Merge:** The PR is "Squashed and Merged." The ADR now lives in `main` as an official part of the project's architecture.
