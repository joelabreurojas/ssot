# Pull Requests

A Pull Request (PR) is a story about a solution. Its purpose is to give the reviewer context and ensure the highest possible code quality.

### 1. Mandatory Structure
Every PR must follow the project template (`standard_pr_template.md`). The following sections are non-negotiable:

*   **Summary of Changes:** A one-sentence, high-level summary of the main change.
*   **Associated Issue:** A link to the ticket (e.g., `Resolves #102`).
*   **Problem Addressed / Purpose:** 
    *   **Problem:** The "Why" behind the change.
    *   **Goal:** The ultimate objective.
*   **Technical Details & Implementation:** 
    *   **Changes Made:** Key technical shifts/new files.
    *   **Design Decisions:** Why this approach was chosen.
    *   **Potential Trade-offs:** Known limitations or future improvements.
*   **How to Test / Reproduce:** 
    *   Step-by-step instructions (Setup + Commands).
    *   **Expected Outcome:** What the reviewer should see.
*   **Visual Aids:** Screenshots or GIFs for any UI changes.
*   **Author Checklist:** Verification of standards, CI, and test coverage.

### 2. The PR Lifecycle

#### **Step 1: The Self-Review**
Before requesting a peer review, the author must perform a critical self-audit:
1.  Read through the "Files Changed" tab on GitHub to catch typos, debug logs, or commented-out code.
2.  Confirm the **Continuous Integration (CI)** pipeline is completely green (✅).
3.  Ensure that all documentation (PRDs, RFDs, ADRs) affected by this change has been updated.

#### **Step 2: Peer Review**
Reviewers are the guardians of the codebase.
*   **Focus:** Reviewers should focus on logic, security, architecture, and edge cases. 
*   **Automation First:** Formatting and style should be enforced by the CI, not by human comments.
*   **Approval:** At least one formal "Approval" is required to merge.
*   **Changes Requested:** If a reviewer requests changes, the Issue remains in the `In Review` column on the Kanban board until the author pushes the fixes to the same branch.

#### **Step 3: The Squash and Merge**
Once approved and CI passes, the PR is merged using the **Squash and Merge** strategy. 
*   **Final Link:** Per our [Commit Standards](./12_commit_standards.md), the final commit title in `main` must include the PR ID (e.g., `feat(ui): add new widget (#45)`).

---

### 3. Stacked PRs
In cases where a task has a **Hard Dependency** on another unfinished task:
1.  Branch off the prerequisite task's branch.
2.  Use the `stacked_pr_template.md` for your Pull Request.
3.  Clearly indicate which PR must be merged first. This allows reviewers to see only the relevant "diff" for your specific task.
