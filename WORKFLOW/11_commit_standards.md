# Commit Standards

A commit is the smallest atomic unit of work. We follow the **Conventional Commits** specification to ensure our history is a searchable, machine-readable narrative of the project's evolution.

---

### 1. Atomic Commits
Each commit must represent **one logical change**. 
*   **Rule:** If a commit contains changes that require two different descriptions, it is too big.
*   **Link to Tasks:** Every commit should fulfill one or more items from the Issue's **To-Do List**. This allows for granular tracking of progress within a branch.

### 2. Formatting the Message
We follow this structure for all commits:

```text
type(scope): subject

<body>

<footer>
```

#### **The Title (The First Line)**
*   **Type:** Describes the *nature* of the work. Use the types defined in the [Labeling System](./08_labeling_system.md) (e.g., `feat`, `fix`, `chore`, `refactor`).
*   **Scope:** A **free-form topic** identifying the logical area of the code being changed (e.g., `sidebar`, `api-auth`, `landing-page`). Do not use file paths or extensions.
*   **Breaking Change:** Add a `!` after the type (e.g., `feat!(ui):`) to signal an incompatible change.
*   **Subject:** A short, **lowercase**, imperative-mood summary.
*   **Constraint:** The entire title line **must not exceed 50 characters.**

#### **The Body & Footer (Optional)**
*   **Body:** Separated by a blank line. Explain **"Why"** and **"What"**, not "How." Wrap lines at **72 characters**.
*   **Footer:** Use for `BREAKING CHANGE: <description>` or to link the task: `Resolves #12`.

---

### 3. Examples
*   **Simple:** `fix(ui): correct alignment of sidebar icons`
*   **Complex:**
    ```text
    refactor(api): decouple logic from repository

    Move validation logic into the service layer to allow
    for easier unit testing.

    - Relocate email validation to AuthService.
    - Remove redundant checks from UserRepository.

---

### 4. The `main` Branch History (Resulting Entry)
Because we use **Squash and Merge**, the many incremental commits of a feature branch are compressed into a single entry on the `main` branch. 

To ensure perfect traceability, the final commit title in `main` must include the **Pull Request ID**.

**Format:** `type(scope): subject (#PR-ID)`

**Example of a final history entry:**
```text
feat(ui): implement collapsible sidebar (#136)
```

---

> [!NOTE]
> To ensure consistency, use the provided template in `EXAMPLES/commits/git_commit_template.txt`. 
>
> Configure your local repository:
`git config --local commit.template EXAMPLES/commits/git_commit_template.txt`
