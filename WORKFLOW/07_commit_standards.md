# Commit Standards

We follow the **Conventional Commits** specification. Clean commits are essential for debugging and understanding the project's evolution.

### 1. Atomic Commits
Each commit must represent **one logical change**. Do not bundle unrelated changes (e.g., a style fix and a logic change) in the same commit.

### 2. Formatting the Message
`type(scope): description`

*   **Title:** Max 50 characters, lowercase, imperative mood ("add" not "added").
*   **Scope:** The logical domain (e.g., `auth`, `api`). Do not use file paths.
*   **Body:** (Optional) Wrap at 72 characters. Explain **"Why"** and **"What"**, not "How". Use lists for complex changes.
*   **Footer:** (Optional) Use for `BREAKING CHANGE:` or `Resolves #12`.

### 3. Examples
*   **Simple:** `fix(ui): correct alignment of sidebar icons`
*   **Complex:**
    ```text
    refactor(api): decouple logic from repository

    Move validation logic into the service layer to allow
    for easier unit testing.

    - Relocate email validation to AuthService.
    - Remove redundant checks from UserRepository.
    ```
