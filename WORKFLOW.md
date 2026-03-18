# Project Workflow

> _The single source of truth for our development process, guiding how we plan, execute, and deliver high-quality software._

Welcome to the project! This document outlines the development workflow we use to maintain clarity, momentum, and consistency. Our guiding philosophy is **"Keep It Simple."** This applies to our code, our architecture, and our project management. The goal of this process is to provide clarity, not complexity.

---

## 1. The Kanban Workflow

Our work is tracked on a Kanban board that follows a simple left-to-right progression. This provides a real-time, visual status of all ongoing tasks.

### The Columns

1.  **🗄️ Backlog**
    *   **Purpose:** The "idea freezer." Contains all potential future work, long-term ideas, and low-priority tasks that are not part of the current, active milestone. Nothing in this column is considered committed work.
    *   **Entry Criteria:** Any new idea, feature request, or low-priority task.
    *   **Exit Criteria:** The issue is prioritized and moved into the `Ready` column for an upcoming milestone.

2.  **✅ Ready**
    *   **Purpose:** The immediate to-do list. Contains the fully planned and prioritized tasks for the current milestone. When a developer is free, they should pull the highest-priority issue from the top of this column.
    *   **Entry Criteria:** The issue is essential for completing the current milestone and has a complete "Anatomy of a Perfect Issue."
    *   **Exit Criteria:** A developer assigns the issue to themselves and moves it to `In Progress`.

3.  **🚧 In Progress**
    *   **Purpose:** Shows what is actively being developed right now. This includes initial development as well as re-work based on review feedback.
    *   **Rule:** A developer should have **only one or two issues** in this column at a time to maintain focus.
    *   **Entry Criteria:**
        *   A developer has started working on a task from the `Ready` column.
        *   An issue from `In Review` requires further development or fixes based on feedback.
    *   **Exit Criteria:** The developer has completed the work on a feature branch and opened a Pull Request. The issue is then moved to `In Review`.

4.  **🔬 In Review**
    *   **Purpose:** The work is code-complete and waiting for two things: **automated checks (CI)** and **peer review**. An open Pull Request must be linked to the issue.
    *   **Entry Criteria:** A Pull Request has been opened and is ready for review.
    *   **Handling Failed Reviews/CI:** If a Pull Request does not meet the acceptance criteria:
        1.  The **reviewer** provides clear, actionable feedback directly in the Pull Request comments.
        2.  The **issue is moved back to `In Progress`**.
        3.  A **comment is added to the GitHub Issue** explaining why it moved back and what needs to be addressed.
        4.  The developer makes the necessary changes on the **same feature branch**. **Do NOT create a new issue for re-work.**
    *   **Exit Criteria:** The CI pipeline passes, the Pull Request is approved by a peer, and it is ready to be merged.

5.  **🛑 Blocked / Stopped**
    *   **Purpose:** For issues that are on hold, blocked, or explicitly paused. This provides transparency about work that is not actively moving forward.
    *   **Entry Criteria:**
        *   An issue is blocked by an external dependency (e.g., waiting for API keys, a design decision).
        *   An issue is deprioritized mid-sprint due to changing requirements.
    *   **Exit Criteria:**
        *   The blocker is resolved, and the issue moves back to `In Progress`.
        *   The issue is officially deprecated and moved to `Done` (with a comment indicating its fate).

6.  **🎉 Done**
    *   **Purpose:** Contains all completed work. A task is only "Done" when its code has been successfully merged into the `main` branch.
    *   **Entry Criteria:** The associated Pull Request has been merged.
    *   **Key Rule:** A milestone is considered complete only when all of its committed issues are in this column.

---

## 2. Anatomy of a Perfect Issue

Clarity starts with a well-defined task. Every issue created in this project must follow this structure.

1.  **A Clear, Actionable Title:** e.g., `Configure Docker Environment`.
2.  **A Goal-Oriented Body:**
    *   **Goal:** A one-sentence description of *why* this task is important.
    *   **To-Do List / Requirements:** A checklist of the specific, atomic steps required.
    *   **Acceptance Criteria:** A clear, testable "Definition of Done."
3.  **Correct Fields:** Assign the correct `priority`, `type`, and `module` labels.
4.  **Milestone:** Assign the issue to the relevant milestone.

---

## 3. Branching & Merge Policy

To protect the stability of our main codebase, we adhere to a strict merge policy.

1.  **No Direct Commits to `main`:** The `main` branch is protected.
2.  **All Work on Feature Branches:** Every issue must be worked on in its own branch.
    *   **Branch Naming Convention:** `[type]/[issue-number]-[short-description]`
    *   *Examples:* `feat/102-build-chat-api`, `fix/115-fix-enrollment-bug`
3.  **All Merges via Pull Request (PR):** The only way code enters `main` is by merging an approved PR.
4.  **CI Pipeline is the Gatekeeper:** A PR cannot be merged until all automated CI checks have passed.
5.  **Peer Review is Mandatory:** A PR cannot be merged until at least one other team member has formally "Approved" it.
6.  **Use "Squash and Merge":** Always use the "Squash and Merge" option on GitHub to maintain a clean, linear history on the `main` branch.

---

## 4. The Anatomy of a Perfect Pull Request

A Pull Request is a story about a solution, told to your teammates. It must give reviewers all the context they need to understand the change quickly. Every PR should follow the structure provided by our official `.github/pull_request_template.md`.

*   **1. A Linked Issue:** The PR description **must** link to the primary GitHub Issue it resolves (e.g., `Resolves #102`).
*   **2. A Clear Title:** Concise and in the imperative mood.
*   **3. A "Summary of Changes" Section:** A one-sentence, high-level summary of the main change.
*   **4. A "Problem Addressed / Purpose" Section:** Explain the "why" behind the code.
*   **5. A "Technical Details & Implementation" Section:** Briefly list key technical changes and explain significant design decisions.
*   **6. A "How to Test" Section:** Provide clear, step-by-step instructions for manual verification. This is **non-negotiable**.
*   **7. Visual Aids (if applicable):** For any UI changes, **always** include a screenshot or a short GIF.
*   **8. A Self-Review Checklist:** Use the checklist in the template to confirm your code meets project standards and all tests pass.

---

## 5. The Anatomy of a Perfect Commit

A commit is the smallest atomic unit of work. A clean commit history is essential for debugging and understanding the project's evolution. We adhere strictly to the **Conventional Commits** specification.

*   **1. Atomic and Focused:** One commit should represent **one logical change**.
*   **2. A Well-Formatted Message:** The message must follow this structure:
    ```
    type(scope): subject
    <blank line>
    optional body
    <blank line>
    optional BREAKING CHANGE footer
    ```
    *   **Title:**
        *   **`type`:** `feat`, `fix`, `chore`, `docs`, `refactor`, `test`, `style`, etc.
        *   **`scope` (optional):** The logical domain of the change (e.g., `auth`, `api`), not a file path.
        *   **`!` (optional):** A `!` after the `type` signifies a breaking change (e.g., `feat!(auth):`).
        *   **`subject`:** A short, imperative-mood summary.
        *   **Constraint:** The entire title line **must not exceed 50 characters.**
    *   **Body (optional):**
        *   Explains the **"why"** and **motivation** for the change, not the "how."
        *   For complex changes, list the different actions taken, starting each with a different verb than the title.
        *   **Constraint:** Lines must wrap at **72 characters.**
    *   **Footer (optional):** Must begin with `BREAKING CHANGE:`.

---

## 6. The Anatomy of a Perfect Milestone

A milestone is a **chapter in the project's story**, representing a significant, cohesive phase of development with a clear, narrative goal.

*   **1. A Clear, Narrative Goal:** The title and description should tell a story.
    *   *Examples:* `M1: The Walking Skeleton`, `M2: The Core Engine (Headless)`, `M3: The Minimum Viable Interface`

*   **2. A Definitive "Definition of Done":** A milestone is complete when it achieves a tangible outcome.
    *   *Example for "M3: The Minimum Viable Interface":* "A user can log in, upload a document, ask a question about it, and get a useful answer. The core end-to-end user flow is functional and deployed."

*   **3. Focused and Cohesive:** All issues within a milestone should directly contribute to its narrative goal.

---

## 7. Custom Field System (Labels)

We use a three-part labeling system to categorize every issue.

#### Priority
*   `priority:critical` - Must be fixed immediately; blocks other work.
*   `priority:high` - Essential for the current milestone; a top priority.
*   `priority:medium` - Standard task that should be completed in a timely manner.
*   `priority:low` - A nice-to-have or optimization that can be deferred.

#### Type
*   `type:feature` - A new feature or user-facing functionality.
*   `type:bug` - A bug fix that corrects incorrect behavior.
*   `type:chore` - Maintenance, refactoring, or DevOps tasks.
*   `type:research` - A time-boxed investigation or technical spike.
*   `type:testing` - A task focused exclusively on adding or improving tests.
*   `type:documentation` - A task related to writing or updating documentation.

#### Module
*   `module:api` - Related to FastAPI endpoints and the API layer.
*   `module:ui` - Related to the frontend user interface.
*   `module:auth` - Related to user authentication and authorization.
*   `module:database` - Related to the database schema (SQLAlchemy) or migrations (Alembic).
*   `module:devops` - Related to Docker, CI/CD (GitHub Actions), or deployment.
*   `module:observability` - Related to logging, metrics, or analytics.
*   `module:rag` - Related to the core RAG pipeline.
*   `module:learning` - Related to the Learning Support Module.
*   `module:general` - A task that spans multiple modules or is project-wide.
