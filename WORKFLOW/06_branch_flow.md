# Branch Flow

To protect the stability of our `main` branch, we follow a strict branching and merging policy. The branch serves as the workspace for a single unit of work.

### 1. The Golden Rule
**No direct commits to `main`.** All work must happen on a feature branch.

### 2. Branch Naming Convention
To maintain a clear link between our planning system (GitHub) and our version control (Git), branches must follow this pattern:

`[type]/[issue-id]-[short-description]`

*   **Type:** Use the types defined in [Labeling System](./04_labeling_system.md) (e.g., `feat`, `fix`, `chore`, `research`).
*   **Issue ID:** The numeric ID assigned by the issue tracker.
*   **Description:** 2-3 words summarizing the task.

**Example:** `feat/12-user-auth-service`

### 3. One Issue = One Branch
To maintain atomic logic and prevent "hostage PRs," each branch should solve exactly one task. While it may feel repetitive to identify the task again in the branch name, this metadata is essential for developers working in the terminal to identify the context of the code.

### 4. Special Branches
These branches are "free" from the standard Milestone Execution Order, but must still adhere to our core standards (Atomic Commits, CI Checks, and PR Reviews).

*   **Spike/Research (`research/`):** Used for investigations or testing new technologies.
    *   **The Goal:** To answer a specific question or prove a concept (e.g., "Is this library compatible with our system?").
    *   **The Rule:** Research branches do not always produce production-ready code. Therefore, to mark a Research Issue as **Done**, the developer must produce a **Knowledge Asset**:
        1.  **An ADR (Architecture Decision Record):** If the research leads to a permanent architectural choice.
        2.  **A Prototype PR:** If the research produces a "proof of concept" to show the team.
        3.  **A Final Report:** A detailed comment in the GitHub Issue summarizing the findings (Pros/Cons/Recommendation).
*   **Hotfix (`hotfix/`):** Used for critical production bugs that must be fixed immediately.
    *   *Freedom:* It can jump to the front of the queue, ignoring the current Milestone.
    *   *Rule:* It still requires a PR and a passing CI pipeline.
*   **Refactor (`refactor/`):** Used for cleaning up existing code without adding features.
    *   *Freedom:* Often not planned in the initial Milestone roadmap.
    *   *Rule:* Must not change system behavior and must have 100% test coverage.

### 5. Merge Strategy: Squash and Merge
We exclusively use the **Squash and Merge** option on GitHub. 
*   **Clarity:** It ensures the `main` history is a clean, high-level timeline where one commit equals one completed Issue/Task.
