# Commit Standards

A commit is the smallest atomic unit of work in our project. A clean commit history is essential for debugging, understanding feature evolution, and maintaining the codebase. We adhere strictly to the **Conventional Commits** specification.

---

### 1. Atomic Commits
Each commit must represent **one logical change**. 
*   **The Rule:** If a commit contains changes that require two different descriptions, it is too big and must be split.
*   **Link to Tasks:** Every commit should fulfill one or more items from the Issue's **To-Do List**. This allows for granular tracking of progress within a feature branch.
*   **The Benefit:** Atomic commits make `git blame` more useful, code reviews easier, and allow for safe rollbacks or cherry-picking.

### 2. Formatting the Message
We follow a strict structure for all commit messages:

```text
type(scope): subject

<body>

<footer>
```

#### **The Title (The First Line)**
*   **Type:** Describes the *nature* of the work. Use the types defined in the [Labeling System](./13_labeling_system.md) (e.g., `feat`, `fix`, `chore`, `refactor`, `test`, `research`).
*   **Scope:** A **free-form topic** identifying the logical area or component being changed (e.g., `sidebar`, `api-auth`, `db-init`). Do not use file paths or extensions.
*   **Breaking Change:** Add a `!` after the type (e.g., `feat!(ui):`) to signal an incompatible change.
*   **Subject:** A short, **lowercase**, imperative-mood summary (e.g., "add," "fix," "refactor").
*   **Constraint:** The entire title line **must not exceed 50 characters.**

#### **The Body & Footer (Optional)**
*   **Body:** Separated from the title by a blank line. Explain **"Why"** and **"What"**, not "How." Wrap lines at **72 characters**.
*   **Footer:** Use for `BREAKING CHANGE: <description>` or to link the task: `Resolves #12`.

---

### 3. The `main` Branch History
Because we use **Squash and Merge**, the incremental commits of a feature branch are compressed into a single entry on the `main` branch. 

To ensure perfect traceability, the final commit title in `main` must include the **Pull Request ID**.

**Format:** `type(scope): subject (#PR-ID)`

**Example of a final history entry:**
```text
feat(ui): implement collapsible sidebar (#136)
```

---

### 4. Examples
*   **Simple:** `fix(ui): correct alignment of sidebar icons`
*   **Complex:**
    ```text
    refactor(api): decouple logic from repository

    Move validation logic into the service layer to allow
    for easier unit testing.

    - Relocate email validation to AuthService.
    - Remove redundant checks from UserRepository.

---

> [!NOTE]
> To ensure consistency, use the provided template in `.github/commits/git_commit_template.txt`. 
>
> Configure your local repository:
`git config --local commit.template .github/commits/git_commit_template.txt`
