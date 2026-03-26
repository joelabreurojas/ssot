# Branch Flow

To protect the stability of our `main` branch, we follow a strict branching and merging policy. The branch serves as the workspace for a single unit of work.

> [!IMPORTANT]
> Before starting any task:
> 1. Ensure you have pulled the latest changes from `main`.
> 2. Create your branch: `git checkout -b [type]/[issue-id]-[description]`.

---

### 1. The Golden Rule
**No direct commits to `main`.** All work must happen on a feature branch. This ensures that every change is peer-reviewed and passes automated CI checks before being integrated.

### 2. Branch Naming Convention
To maintain a clear link between our planning system and our version control, branches must follow this metadata-rich pattern:

`[type]/[issue-id]-[short-description]`

*   **Type:** Use the types defined in the [Labeling System](./10_labeling_system.md) (e.g., `feat`, `fix`, `chore`, `research`).
*   **Issue ID:** The numeric ID assigned by the issue tracker (e.g., `102`).
*   **Description:** 2-3 words summarizing the task, separated by hyphens (e.g., `auth-service`).

**Example:** `feat/102-user-auth-service`

### 3. One Issue = One Branch (Atomic Logic)
To prevent "hostage PRs" and unmanageable merge conflicts, each branch must solve exactly one planned Issue. 
*   Never bundle unrelated changes into a single branch.
*   If you discover a separate bug while working on a feature, do not fix it in the current branch. Instead, create a new Issue and a separate branch for that fix.

### 4. Special Branches
These branches are "free" from the standard Milestone Execution Order, but must still adhere to our core standards (Atomic Commits, CI Checks, and PR Reviews).

*   **Spike/Research (`research/`):** Used for investigations or testing new technologies.
    *   **The Goal:** To answer a specific question or prove a concept.
    *   **The Rule:** Research branches do not always produce production code. To mark a Research Issue as **Done**, the developer must produce a **Knowledge Asset**:
        1.  **An ADR:** If the research leads to a permanent architectural choice.
        2.  **A Prototype PR:** If proving a concept in code.
        3.  **A Final Report:** A detailed comment in the Issue summarizing findings.
*   **Hotfix (`hotfix/`):** Used for critical production bugs that must be fixed immediately.
    *   *Freedom:* Can jump to the front of the queue, ignoring the current Milestone.
*   **Refactor (`refactor/`):** Used for cleaning up code without adding features or changing behavior.
    *   *Rule:* Must have 100% test coverage before merging.

### 5. Merge Strategy: Squash and Merge
We exclusively use the **Squash and Merge** strategy on GitHub. 
*   **The Benefit:** It compresses all incremental, work-in-progress commits from the feature branch into a single, clean, high-level commit on the `main` branch. 
*   **The Outcome:** The history of the `main` branch remains a perfectly clean timeline of completed Tasks, rather than a messy list of "wip" and "typo" commits.
