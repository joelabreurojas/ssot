# Anatomy of a Perfect Issue (The Task)

An Issue is a **single Task** that belongs to a Milestone (Epic). It is the atomic unit of work. To maintain a clear path to delivery and prevent blockers, every task must define its exact place in the sequence.

## Required Fields for Sequence & Planning

1.  **Execution Order:** A numeric value (1, 2, 3...) indicating the logical sequence of development within the Milestone.
    *   **ID vs. Order:** The Issue number (e.g., #78) is just a unique identifier created by the issue tracker. The **Execution Order** determines the actual roadmap (e.g., Task Order 1 must be completed before Task Order 2 begins, regardless of their Issue IDs).
2.  **Depends On:** List the Execution Order number(s) of prerequisite tasks.
    *   **None:** This task can be started immediately (Parallel).
    *   **Order #[X]:** This task is a "Hard Dependency" and is blocked until Order #[X] is completed or reaches a stable state.
3.  **Goal:** A one-sentence description of *why* this task exists and the value it adds.
4.  **To-Do List:** The specific technical requirements. One To-Do item usually equals one or more Atomic Commits.
5.  **Acceptance Criteria:** The objective "Definition of Done" for this specific task. How do we test that it works?

### Execution Order vs. Dependencies (Guiding Focus)
It is crucial to understand the difference between these two fields:
*   **Depends On (Technical Reality):** This is a hard technical blocker. You literally cannot write the code for the API if the Database Schema it queries does not exist.
*   **Execution Order (Strategic Focus):** This is a human decision about what matters most *right now* to maintain project momentum. 

**The Edge Case:** You may see a task with `Depends On: None` but an `Execution Order: 2` (or higher). 
*   *Why?* The Project Lead is guiding developer focus. While you *could* technically build the UI (Order 2) on day one, the foundational Database (Order 1) is far more critical to the project's overall risk and architecture. 
*   *The Rule:* Respect the Execution Order. Do not skip ahead to unblocked Order 2 tasks if there are still Order 1 tasks available in the `Ready` column. We build the foundation first, together.

## The Task Lifecycle & Picking Work

To maximize speed and avoid merge conflicts, developers must follow these steps when selecting a new task:

1.  **Check the Milestone Index:** Look at the `milestone_blueprint.md` in the current Milestone.
2.  **Pick the Lowest Order:** Always pick the lowest "Execution Order" number that is not currently assigned.
3.  **Evaluate Dependencies:** 
    *   If the task has a **Hard Dependency** (e.g., "Depends on Order #1"), and Order #1 is not finished, you must coordinate with the person working on #1. You can either assist them, or start your work by branching off their active branch (see [Pull Requests](./06_pull_requests.md) for Stacked PRs).
    *   If the task has **No Dependencies**, you may start immediately, even if someone else is working on a lower Execution Order number.
4.  **Parallel Work:** If multiple tasks share the same "Execution Order" number or belong to different technical modules (e.g., `module:ui` vs `module:database`), they should be worked on simultaneously by different team members.

### Rule of Thumb: Branching
**One Issue = One Branch = One PR.** 
Create a branch from `main` using the convention `[type]/[issue-id]-[description]`. Fulfill the To-Do list using Atomic Commits, and open a Pull Request to merge the Task back into the main codebase.
