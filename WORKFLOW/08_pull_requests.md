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

### 2. Self-Review
Before requesting a peer review, the author must read through their own "Files Changed" tab to remove debug logs, comments, or unnecessary files.

### 3. Peer Review
*   **Logic over Style:** Style and formatting are enforced by the CI. Reviewers should focus on architecture and logic.
*   **Approved:** At least one formal approval is required to merge.
*   **Changes Requested:** If changes are needed, the Issue moves back to `In Progress` on the Kanban board.

### 4. Stacked PRs
If a task depends on another unfinished task, use the `stacked_pr_template.md`. This alerts the reviewer to merge the base PR before reviewing the dependent one.
