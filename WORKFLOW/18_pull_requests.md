# Pull Requests

A Pull Request (PR) is more than a request to merge code; it is a **story about a solution** told to your teammates. Its purpose is to provide reviewers with all the context they need to understand the change, verify its quality, and maintain the project's long-term health.

---

### 1. Mandatory Structure
Every PR must follow the standard structure established in the project templates (found in `EXAMPLES/pull_requests/`). The following sections are non-negotiable for a professional PR:

*   **Summary of Changes:** A high-level, one-sentence summary of the technical change.
*   **Associated Issue:** A direct link to the task identifier (e.g., `Resolves #102`).
*   **Problem Addressed / Purpose:** Explain the "Why." What real-world problem does this solve? What is the goal?
*   **Technical Details & Implementation:** 
    *   **Changes Made:** Key architectural shifts or new components.
    *   **Design Decisions:** Why this specific approach was chosen over alternatives.
    *   **Trade-offs:** Any known limitations or future improvements.
*   **How to Test / Reproduce:** Clear, step-by-step instructions to verify the work. **A PR without testing instructions is not ready for review.**
*   **Visual Aids:** For any UI-facing changes, you MUST include a screenshot or a short GIF.
*   **Checklist:** A final verification of standards, CI status, and documentation updates.

---

### 2. The PR Lifecycle

#### **Step 1: The Self-Review**
Before requesting a peer review, the author must perform a critical self-audit:
1.  Read through the "Files Changed" tab on GitHub to catch typos, debug logs, or commented-out code.
2.  Confirm the **Continuous Integration (CI)** pipeline is completely green (✅).
3.  Ensure that all documentation (PRD, RFD, ADR) affected by this change has been updated and is included in the PR.

#### **Step 2: Peer Review**
Reviewers are the guardians of the codebase.
*   **Focus:** Reviewers focus on logic, security, architecture, and edge cases. 
*   **Automation First:** Formatting and style should be enforced by the CI, not by human comments.
*   **Approval:** At least one formal "Approval" is required to merge.
*   **Changes Requested:** If a reviewer requests changes, the Issue remains in the `In Review` column on the Kanban board. The author pushes fixes to the same branch until approval is reached.

#### **Step 3: The Squash and Merge**
Once approved and CI passes, the PR is merged using the **Squash and Merge** strategy. 
*   **Final Traceability:** Per our [Commit Standards](./16_commit_standards.md), the final commit title in `main` must include the PR ID (e.g., `feat(ui): add new widget (#45)`).

---

### 3. Stacked PRs
In cases where a task has a **Hard Dependency** on another unfinished task:
1.  Branch off the prerequisite task's branch.
2.  Use the `stacked_pr_template.md` template for your Pull Request.
3.  Clearly indicate which PR must be merged first. This allows reviewers to see only the relevant "diff" for your specific task and prevents large, unreviewable PRs.
