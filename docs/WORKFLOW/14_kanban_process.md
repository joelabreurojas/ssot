# The Kanban Process

Our work is tracked on a Kanban board that follows a strict left-to-right progression. An issue moves forward until completion or is paused for specific reasons. This system provides real-time transparency for the entire team and prevents bottlenecks.

---

### 1. 🗄️ Backlog
The "idea freezer." Contains all potential future work, feature requests, and long-term ideas that are **not** part of the current, active Milestone.
*   **Entry Criteria:** Any new idea, user story from the PRD, or low-priority maintenance task.
*   **Exit Criteria:** The Project Owner or Lead Architect assigns an **Execution Order**, adds the task to a **Milestone** (Epic), and moves it to `Ready`.

### 2. ✅ Ready
The immediate to-do list for the active Milestone.
*   **Entry Criteria:** The task is essential for the current Milestone and has a complete [Anatomy of a Perfect Issue](./12_issue_standards.md) (Goal, To-Do List, Acceptance Criteria).
*   **Key Rule:** When a developer is free, they **MUST** pull the task with the **lowest Execution Order** from the top of this column.
*   **Exit Criteria:** A developer assigns the issue to themselves and moves it to `In Progress`.

### 3. 🚧 In Progress
Shows what is actively being developed right now.
*   **Entry Criteria:** 
    *   Developer has pulled the task from `Ready`.
    *   **OR** The task was moved back from `In Review` due to requested changes or failed CI.
*   **WIP Limit (Work In Progress):** To maintain focus and quality, a developer should have **no more than 2 issues** in this column at a time.
*   **Exit Criteria:** The work is code-complete on a feature branch, and a Pull Request has been opened and linked to the issue.

### 4. 🔬 In Review
The code is written but waiting for quality verification and peer feedback.
*   **Entry Criteria:** A Pull Request is open and the Continuous Integration (CI) pipeline has started.
*   **Handling Failed Reviews/CI:**
    1.  The reviewer or CI system provides clear feedback or error logs.
    2.  **The Issue is moved back to `In Progress`**.
    3.  The developer makes the necessary fixes on the **same feature branch** and re-pushes.
    4.  **Do NOT create a new issue for re-work.**
*   **Exit Criteria:** The CI pipeline is green (✅) and at least one peer has formally approved the PR.

### 5. 🛑 Stopped / Blocked
Transparency for work that is not actively moving forward.
*   **Entry Criteria:**
    *   The task is blocked by an external dependency (e.g., waiting for a 3rd party API key).
    *   An issue is deprioritized mid-sprint due to changing requirements or strategic shifts.
    *   **Mandatory Step:** The developer **MUST** add a comment to the issue explaining the specific reason for the stop.
*   **Exit Criteria:** The blocker is resolved or priority is restored. Move the issue back to `In Progress`.

### 6. 🎉 Done
The archive of completed, verified, and integrated work.
*   **Entry Criteria:** The associated Pull Request has been successfully "Squashed and Merged" into the `main` branch.
*   **Key Rule:** A Milestone is only considered complete when **ALL** of its assigned issues are in this column.
