# Issue Standards (The Task)

An Issue is a **single Task** that belongs to a Milestone (Epic). It is the discrete unit of work that a developer picks up to implement a specific part of a module. To maintain a clear roadmap and prevent team friction, every task must define its exact place in the sequence.

---

### 📝 Required Fields for Planning

When creating a Task (using the `issue_task_template.md`), the following fields are mandatory:

1.  **Execution Order:** A numeric value (1, 2, 3...) indicating the **Strategic Priority**.
    *   *Rule:* Developers should always focus on the lowest available numbers in the `Ready` column.
    *   *Note:* The Issue ID (e.g., #180) is just a random identifier. The **Order** is the actual roadmap.
2.  **Depends On:** A list of Execution Order numbers that are **Technical Blockers**.
    *   *None:* This task can be started immediately (Parallelizable).
    *   *Order #[X]:* This task cannot be finished until Task [X] is stable or merged.
3.  **Goal:** A one-sentence description of *why* this task exists and the value it adds.
4.  **To-Do List:** A checklist of atomic technical requirements. One To-Do item usually corresponds to one or more **Atomic Commits**.
5.  **Acceptance Criteria:** Objective points that define the "Definition of Done" for this specific task.

---

### 🚦 Coordination & Parallel Work

By using both **Order** and **Dependencies**, coworkers can work efficiently without stepping on each other:

*   **Strategic Focus:** If Order 1 and Order 2 are both unblocked, two developers should take them to finish the high-priority foundation faster.
*   **Parallel Execution:** If a developer sees that Order 3 is blocked by Order 1, but Order 4 has `Depends On: None`, they can skip to Order 4 to maintain momentum while Order 1 is being built.
*   **The "Stacked" Technique:** If a developer must start a blocked task (e.g., Order 2 depends on Order 1), they should coordinate with the owner of Order 1 and branch off their work-in-progress branch instead of `main`.

---

### 🔄 The Task Lifecycle

To ensure code quality and a clean history, every Task follows this technical flow:

1.  **Branching:** One Issue = One Branch. Created from `main` (or a parent branch if stacked).
2.  **Execution:** Fulfill the To-Do list through **Atomic Commits** (one logical change per commit).
3.  **Verification:** Ensure all **Acceptance Criteria** are met and tests pass.
4.  **Submission:** Open a **Pull Request**. Once approved, the task is **Squashed and Merged** into `main`.
