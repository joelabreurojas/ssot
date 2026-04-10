# CI/CD, Security Scanning & Releases

Automation is the ultimate enabler of momentum. We rely on Continuous Integration (CI) and Continuous Delivery (CD) to remove human error, enforce our standards, and securely deploy code. A release is the formal snapshot of that verified work.

---

## 1. Continuous Integration (The Quality Gate)
The CI pipeline runs on every Pull Request. **No PR can be merged if the CI pipeline fails.** 

A standard pipeline must execute the following jobs in parallel or sequence:
1.  **Formatting & Linting:** Enforces code style. (If a developer forgets a trailing comma, the pipeline fails, saving human reviewers from arguing about syntax).
2.  **Static Analysis & Type Checking:** Catches logical errors before code execution.
3.  **Automated Testing:** Executes the test suite (Unit, Integration) defined in our [Testing Standards](./06_testing_standards.md).
4.  **Build Verification:** Ensures the application (or container) compiles successfully.

---

## 2. Automated Security & Scanning (DevSecOps)
We leverage platform-native security tools (e.g., GitHub Advanced Security) to continuously protect the repository. These must be enabled at project initialization:

*   **Secret Scanning:** Automatically detects and blocks commits containing API keys, tokens, or passwords.
*   **Dependabot (Vulnerabilities):** Scans `package-lock.json`, `requirements.txt`, etc., for known CVEs and automatically opens PRs to patch them.
*   **Code Scanning (CodeQL / SAST):** Analyzes the source code during the CI run to detect vulnerabilities (e.g., SQL injection, XSS) before they reach `main`.

---

## 3. Continuous Delivery & Environments
Once a PR is merged into `main`, the CD pipeline takes over to deliver the code to the target environments.

*   **Social Preview Environments (Ephemeral Environments):** For UI/Frontend PRs, the CI pipeline should automatically spin up a temporary, isolated deployment of that specific branch. This allows reviewers and stakeholders to visually test the changes before merging.
*   **Staging/Production Deployment:** Merging to `main` should trigger an automatic deployment to the Staging environment. Deployment to Production should be gated by a formal Release or manual approval, depending on the project's risk profile.

---

## 4. The Release Strategy (Semantic Versioning)
A Release is a formal, stable snapshot of the project that is ready for end-users. We strictly adhere to **Semantic Versioning (SemVer)**: `MAJOR.MINOR.PATCH`.

*   **MAJOR:** Incompatible API or architectural changes.
*   **MINOR:** New functionality added in a backwards-compatible manner.
*   **PATCH:** Backwards-compatible bug fixes.

**Git Tagging:** Every release must be marked with a Git Tag (e.g., `v1.2.0`) pointing to the specific commit in `main`.

---

## 5. The Changelog & GitHub Releases
We maintain a human-readable record of changes in `docs/CHANGELOG.md` to communicate value clearly. 

### The Workflow:
1.  **During Development:** As PRs are merged, developers add a one-line summary of their feature/fix to the `[Unreleased]` section of the `CHANGELOG.md`.
2.  **Preparing the Release:** 
    *   The Lead Engineer creates a PR to change `[Unreleased]` to the new version number (e.g., `[1.2.0] - 2026-04-10`).
    *   A new, empty `[Unreleased]` block is added at the top.
3.  **Publishing:** 
    *   The PR is merged.
    *   A **Git Tag** is created.
    *   A formal **GitHub Release** is published. The text from the `CHANGELOG.md` for that version is copied directly into the GitHub Release description.
    *   Release artifacts (e.g., compiled binaries, Docker images) are automatically attached to the GitHub Release by the CD pipeline.
