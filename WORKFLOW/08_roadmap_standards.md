# Roadmap Standards (The Strategic Sequencer)

The Roadmap is the bridge between the Product Requirements (PRD) and the Technical Specification (RFD). Its purpose is to sequence high-level business modules to ensure the team focuses engineering resources only on the immediate priority.

---

### 🏛️ The "Now, Next, Later" Framework

We avoid fixed-date timelines. Instead, we use a status-based sequence to manage expectations and engineering bandwidth:

1.  **🟢 NOW (Active & Designing):** 
    *   **Engineering status:** Actively writing the RFD, drawing VIEWS, or coding the Tasks.
    *   **Rule:** Max 2 Milestones in "Now" at once. Requirements are **Locked**.
2.  **🟡 NEXT (The Queue):** 
    *   **Engineering status:** Requirements are defined in the PRD, but technical design (RFD) has not yet started.
    *   **Rule:** These are the next candidates for the "Now" column.
3.  **🔴 LATER (The Horizon):**
    *   **Engineering status:** Abstract concepts or future goals in the PRD.
    *   **Rule:** Engineering ignores these items to prevent wasted design effort on features that may pivot.

---

### 🚦 The Strategic Gate Rule

**No RFD before its time.**
The engineering team must **never** start the Technical Specification (RFD) or UI Design (VIEWS) for a module that sits in the "Next" or "Later" columns. 

Technical design is an expensive engineering investment. By waiting until a module is in the "Now" column, we ensure the design reflects the most current state of the codebase and the latest business requirements.

---

### 🛠 Maintenance & Changes

Because the Roadmap dictates the team's focus, it must be kept in perfect sync with the PRD:

*   **Logical States:** The current state of the roadmap is handled in the `ROADMAP.md` header.
*   **The "Proposed" Trigger:** Any time the sequence is changed (e.g., moving a feature from "Next" to "Now"), the status must be changed to **Proposed** in the feature branch.
*   **The "Accepted" Flip:** The status is changed back to **Accepted** only when the PR is approved, signifying official strategic alignment.
*   **Linkage:** Each entry in the Roadmap should provide a link to the corresponding high-level requirements in the **PRD folder**.
