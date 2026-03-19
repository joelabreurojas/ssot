# The Kanban Process

Our work is tracked on a Kanban board that follows a strict left-to-right progression. An issue moves forward until completion or is paused for specific reasons. This system provides real-time transparency for the entire team.

---

### 1. 🗄️ Backlog
The "idea freezer." Contains all potential future work and ideas that are *not* part of the current, active Milestone.
*   **Entry Criteria:** Any new idea, feature request, or low-priority task.
*   **Exit Criteria:** The Project Lead assigns it an **Execution Order**, adds it to a **Milestone**, and moves it to `Ready`.

### 2. ✅ Ready
The immediate to-do list for the current Milestone.
*   **Entry Criteria:** The task is essential for the active Milestone and has a complete [Anatomy of a Perfect Issue](./07_issue_standards.md).
*   **Key Rule:** When a developer is free, they MUST pull the task with the **lowest Execution Order** from the top of this column.
*   **Exit Criteria:** A developer assigns the issue to themselves and moves it to `In Progress`.

### 3. 🚧 In Progress
Shows what is actively being developed right now.
*   **Entry Criteria:** 
    *   Developer has pulled the task from `Ready`.
    *   **OR** The task was moved back from `In Review` due to requested changes or failed CI.
*   **WIP Limit (Work In Progress):** A developer should have **no more than 2 issues** in this column to maintain focus and speed.
*   **Exit Criteria:** Work is code-complete on a feature branch. A Pull Request is opened and linked to the issue.

### 4. 🔬 In Review
The code is written, but waiting for quality verification.
*   **Entry Criteria:** A Pull Request has been opened and the Continuous Integration (CI) pipeline has started.
*   **Handling Failed Reviews/CI:**
    1.  The reviewer or CI provides clear, actionable feedback or error logs.
    2.  **The Issue is moved back to `In Progress`**.
    3.  The developer makes the necessary fixes on the **same feature branch** and re-pushes.
    4.  **Do NOT create a new issue for re-work.**
*   **Exit Criteria:** The CI pipeline is green (✅) and a peer has formally approved the PR.

### 5. 🛑 Stopped / Blocked
Transparency for work that is not actively moving forward.
*   **Entry Criteria:**
    *   The task is blocked by an external dependency (e.g., waiting for API keys).
    *   The task is deprioritized mid-sprint due to changing requirements.
    *   **Requirement:** The developer MUST add a comment to the issue explaining the reason for the stop.
*   **Exit Criteria:** The blocker is resolved or priority is restored. Move the issue back to `In Progress`.

### 6. 🎉 Done
The archive of completed and verified work.
*   **Entry Criteria:** The associated Pull Request has been successfully "Squashed and Merged" into the `main` branch.
*   **Key Rule:** A Milestone is only considered complete when **ALL** of its assigned issues are in this column.
