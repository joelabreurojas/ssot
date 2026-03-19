# Architecture Decision Records (ADR) Standards

An ADR is a document that captures a **significant technical decision** made during the development process, including the context and the consequences. 

While the RFD is the initial blueprint, ADRs record the **pivots and refinements** that happen once coding begins.

---

### 📂 The ADR Directory

All records are stored in `docs/ADRs/` to serve as a chronological history of the project's evolution.

1.  **File Naming:** Use a sequential three-digit prefix followed by a slug.
    *   *Format:* `NNN_short_description.md`
    *   *Example:* `001_use_postgresql_over_sqlite.md`
2.  **Single Source of Truth:** Once an ADR is "Accepted" and merged into the `main` branch, it is part of the system's specification. 

---

### 📝 Key Standards (The Anatomy of an ADR)

Every ADR must follow the `adr_template.md` (found in `EXAMPLES/docs/`) and include:

1.  **Status:**
    *   **Proposed:** The decision is currently under review in a Pull Request.
    *   **Accepted:** The decision has been approved and merged into `main`.
    *   **Superseded:** This decision has been replaced by a later ADR.
2.  **Context:** What is the specific problem or requirement that forced this decision?
3.  **Decision:** What is the chosen solution? Use clear, affirmative language.
4.  **Rationale:** Why is this the best choice among the alternatives? 
5.  **Consequences:** What are the trade-offs? What must other developers be aware of now?

---

### 🛠️ When to write an ADR

Do not write an ADR for every small change. Reserve them for decisions that:
*   Introduce a new major dependency or library.
*   Change the data model or API contracts defined in the RFD.
*   Select one technical path over another when both have significant trade-offs.

---

### 🚀 Workflow Integration (The Status Flip)

To ensure the repository history is accurate, we follow this sequence:

1.  **Propose:** The Developer creates the ADR with `Status: Proposed` in a feature branch.
2.  **Discuss:** The team reviews the ADR within the Pull Request.
3.  **Approve:** The Reviewer approves the PR once the decision is validated.
4.  **Flip:** After approval, but **before merging**, the Developer updates the status to `Accepted`.
5.  **Merge:** The PR is merged. The ADR now lives in `main` as a permanent record of an accepted decision.
