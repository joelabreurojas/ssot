# Contributing to [Project Name]

First off, thank you for taking the time to contribute! 🎉 

This project follows a strict **Design-First** philosophy and high engineering standards to ensure the codebase remains maintainable and robust.

---

## 🧭 The Golden Rule
Before you write a single line of code, you must familiarize yourself with our [**Project Workflow Manual**](../../WORKFLOW/README.md). It is the single source of truth for how we plan, code, and deliver.

---

## 🚀 How to Get Started

### 1. Identify the Work
*   Browse the [**Kanban Board**](link-to-board).
*   Look for issues in the **`✅ Ready`** column. 
*   **Pick the lowest Execution Order:** To maintain project momentum, always pick the lowest available number that is not currently assigned.

### 2. Set Up Your Environment
*   Clone the repository.
*   Follow the installation steps in the main [**README.md**](../../README.md).
*   **Optional Step:** Configure your local Git commit template:
    `git config --local commit.template EXAMPLES/commits/git_commit_template.txt`

---

## 🛠️ Development Process

We build atomically. Every contribution must follow this lifecycle:

1.  **Branch:** Create a branch from `main`.
    *   *Convention:* `[type]/[issue-id]-[short-description]`
2.  **Code & Document:**
    *   Write **Atomic Commits** following the [Conventional Commits spec](../../WORKFLOW/12_commit_standards.md).
    *   **Logic over Code:** If your change affects logic or architecture, you **must** update the corresponding [PRD](../../WORKFLOW/03_prd_standards.md) or [RFD](../../WORKFLOW/04_rfd_standards.md) files.
3.  **Test:** Ensure all Continuous Integration (CI) checks pass locally (`linter`, `tests`, `typing`).
4.  **Submit:** Open a Pull Request using our [Standard PR Template](../pull_requests/standard_pr.md).

---

## ⚖️ Quality Standards

To have a Pull Request merged, it must meet these criteria:
*   **Atomic Logic:** The PR solves exactly one Issue.
*   **Documentation:** All technical pivots are recorded in an [ADR](../../WORKFLOW/13_adr_standards.md).
*   **Green CI:** The pipeline must be 100% green (✅).
*   **Peer Approval:** At least one Maintainer must approve the architectural approach.

---

## 💬 Communication
If you are unsure about an approach, please open a **Research/Spike** issue or start a discussion in the [Discussions/Slack/Discord] channel before beginning implementation.

**Happy Coding!**
