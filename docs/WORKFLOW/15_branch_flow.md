# Branch Flow & Repository Settings

To protect the stability of our `main` branch, we follow a strict branching and merging policy. The branch serves as the workspace for a single unit of work. Furthermore, we enforce these policies using **GitHub Rulesets and Repository Settings** so that human error cannot compromise the codebase.

---

## 1. The Golden Rule
**No direct commits to `main`.** All work must happen on a feature branch. This ensures that every change is peer-reviewed and passes automated CI/CD checks before being integrated.

---

## 2. Mandatory Repository Settings
When initializing this repository, the Project Owner or Maintainer **must** configure the following settings in GitHub (or GitLab equivalent) to automate compliance:

### Pull Request Rules
*   ✅ **Allow squash merging ONLY:** Disable "Merge commits" and "Rebase merging." This guarantees a clean, linear history on `main`.
*   ✅ **Default commit message for squash merges:** Set to `Pull request title and description`. This ensures the PR context and PR-ID are automatically pulled into the final commit message.
*   ✅ **Automatically delete head branches:** Keeps the repository clean after a PR is merged.

### Branch Protection (Rulesets on `main`)
*   ✅ **Require a pull request before merging:** Bypass is strictly prohibited.
*   ✅ **Require approvals:** Set to at least 1 approval from a Maintainer.
*   ✅ **Require status checks to pass:** The CI pipeline (Linters, Tests, Security Scans) must succeed before merging is allowed.
*   ✅ **Require conversation resolution:** All review comments must be resolved.

---

## 3. Branch Naming Convention
To maintain a clear link between our planning system and our version control, branches must follow this metadata-rich pattern:

`[type]/[issue-id]-[short-description]`

*   **Type:** Use the types defined in the Labeling System (e.g., `feat`, `fix`, `chore`, `research`).
*   **Issue ID:** The numeric ID assigned by the issue tracker (e.g., `102`).
*   **Description:** 2-3 words summarizing the task, separated by hyphens.

**Example:** `feat/102-user-auth-service`

---

## 4. One Issue = One Branch (Atomic Logic)
To prevent "hostage PRs" and unmanageable merge conflicts, each branch must solve exactly **one** planned Issue. 
*   Never bundle unrelated changes into a single branch.
*   If you discover a separate bug while working on a feature, do not fix it in the current branch. Instead, create a new Issue and a separate branch for that fix.

---

## 5. Special Branches
These branches are "free" from the standard Execution Order, but must still adhere to our core standards (Atomic Commits, CI Checks, and PR Reviews).

*   **Spike/Research (`research/`):** Used for investigations or testing new technologies.
    *   *The Rule:* To mark a Research Issue as **Done**, the developer must produce a **Knowledge Asset** (An ADR, a Prototype PR, or a Final Report in the issue comments).
*   **Hotfix (`hotfix/`):** Used for critical production bugs that must be fixed immediately.
    *   *Freedom:* Can jump to the front of the queue, ignoring the current Roadmap.
*   **Refactor (`refactor/`):** Used for cleaning up code without adding features or changing behavior.
    *   *Rule:* Must have 100% test coverage before merging.

---
*Note: For solo projects, the 'Require approvals' setting in GitHub may be disabled to allow merging, but 'Require status checks to pass' remains mandatory. The Pull Request remains the only entry point to main.*
