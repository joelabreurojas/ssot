# The Kanban Process

Our workflow follows a strict left-to-right progression. An issue moves forward until completion, or is paused for specific reasons.

### 1. 🗄️ Backlog
The "idea freezer" for future work.
*   **Entry Criteria:** Any new idea or low-priority task.
*   **Exit Criteria:** Task is prioritized, assigned an Execution Order, added to a Milestone, and moved to `Ready`.

### 2. ✅ Ready
The immediate to-do list for the current Milestone.
*   **Entry Criteria:** Task is essential for the active Milestone and has clear Acceptance Criteria.
*   **Rule:** Pull the lowest **Execution Order** first.
*   **Exit Criteria:** Developer assigns the issue to themselves.

### 3. 🚧 In Progress
Actively being developed.
*   **Entry Criteria:** Developer has moved the task from `Ready`, or it was moved back from `In Review`.
*   **WIP Limit:** Maximum **2 issues** per developer.
*   **Exit Criteria:** Work is code-complete. A Pull Request is opened and linked.

### 4. 🔬 In Review
Waiting for quality verification.
*   **Entry Criteria:** A Pull Request is open and the CI pipeline has started.
*   **Handling Failed Reviews/CI:**
    1. Reviewer or CI provides feedback/error logs.
    2. **Issue is moved back to `In Progress`**.
    3. Developer fixes on the **same branch** and re-pushes. **Do NOT create a new issue for re-work.**
*   **Exit Criteria:** CI is green (✅) and a peer has approved the PR.

### 5. 🛑 Stopped / Blocked
Transparency for stalled work.
*   **Entry Criteria:**
    *   Blocked by an external dependency (e.g., waiting for API keys).
    *   Deprioritized mid-sprint due to changing requirements.
    *   **Requirement:** Developer MUST comment the reason for the stop.
*   **Exit Criteria:** Blocker resolved or priority restored. Move back to `In Progress`.

### 6. 🎉 Done
The archive of success.
*   **Entry Criteria:** The PR has been "Squashed and Merged" into `main`.
*   **Key Rule:** A Milestone is only complete when **ALL** its assigned issues are in this column.
