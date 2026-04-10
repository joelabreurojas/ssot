# Issue Standards (The Task)

An Issue is a **single Task** that belongs to a Milestone (Epic). It is a discrete unit of work that a developer picks up to implement a specific part of a module. To maintain a clear roadmap and prevent team friction, every task must define its exact place in the sequence.

---

### 📝 Required Fields for Planning

When creating a Task for a Milestone, use the [**Task Template**](../milestones/issue_task_template.md), where the following fields are mandatory:

1.  **Execution Order:** A numeric value (1, 2, 3...) indicating the **Strategic Priority**.
    *   *The Rule:* Developers should always focus on the lowest available numbers in the `Ready` column.
    *   *ID vs. Order:* The Issue ID (e.g., #180) is a random identifier. The **Execution Order** is the actual roadmap (e.g., Order 1 must be prioritized before Order 5).
2.  **Depends On:** A list of Execution Order numbers that act as **Hard Technical Blockers**.
    *   **None:** This task can be started immediately (Parallelizable).
    *   **Order #[X]:** This task cannot be finished until Task [X] is stable or merged.
3.  **Goal:** A one-sentence description of *why* this task exists and the value it adds to the module.
4.  **To-Do List:** A checklist of atomic technical requirements. 
    *   *Link to Commits:* One To-Do item should ideally correspond to one or more **Atomic Commits**.
5.  **Acceptance Criteria:** Objective points that define the "Definition of Done" for this specific task.
    *   *Micro-Check:* Unlike the Milestone DoD, these criteria only verify the internal logic of this specific task.

---

### 🚦 Coordination & Parallel Execution

By using both **Order** and **Dependencies**, team members can coordinate work without constant meetings:

*   **Strategic Focus:** If Order 1 and Order 2 are both unblocked, two developers should take them to complete the module's foundation as fast as possible.
*   **Parallelism:** If a developer sees that the next task (Order 3) is blocked by Order 1, but a later task (Order 4) has `Depends On: None`, they can skip to Order 4 to maintain momentum.
*   **The "Stacked" Branch Technique:** If a developer must start a blocked task (e.g., Order 2 depends on Order 1), they coordinate with the owner of Order 1 and branch off their active feature branch instead of `main`. Use the `stacked_pr_template.md` for the resulting Pull Request.

---

### 🔄 The Task Lifecycle

To ensure code quality and a clean project history, every Task follows this flow:

1.  **Branching:** One Issue = One Branch. Create a branch from `main` (or a parent branch if stacked).
2.  **Execution:** Fulfill the To-Do list through **Atomic Commits** (one logical change per commit).
3.  **Verification:** Ensure all **Acceptance Criteria** are met and local tests pass.
4.  **Submission:** Open a **Pull Request**. Once approved and CI is green, the task is **Squashed and Merged** into `main`.
