# Contributing to the Project

First off, thank you for taking the time to contribute! 🎉 

This project follows a strict **Design-First** philosophy and a **Blameless Engineering Culture**. We prioritize system improvements and collective learning over individual blame.

---

## 🧭 The Golden Rule
Before you write a single line of code, you must familiarize yourself with our [**Project Workflow Manual**](/docs/WORKFLOW/README.md). It is the single source of truth for how we plan, design, code, and deliver.

---

## 🚀 How to Get Started

### 1. Understand the Vision
Review the **[PRD](/docs/PRD/)** and the **[ROADMAP](/docs/ROADMAP.md)** to understand what we are building and what is currently prioritized as **NOW**. Do not work on features that are in the 'Later' column without prior discussion.

### 2. Identify the Work
*   Browse the [**Kanban Board**].
*   Look for issues in the **`✅ Ready`** column. 
*   **Pick by Order:** To maintain momentum, always pick the task with the lowest **Execution Order** that is not currently assigned.
*   **Check Dependencies:** Verify that any tasks listed in the `Depends On` field are already completed or coordinated.

### 3. Set Up Your Environment
*   Follow the installation steps in the main [**README.md**](/README.md).
*   Configure your local Git commit template:
    `git config --local commit.template .github/commits/git_commit_template.txt`

---

## 🛠️ The Development Cycle

We build atomically. Every contribution must follow this lifecycle:

1.  **Design First:** If your task requires a technical pivot or a new architectural choice not covered in the **[RFD](/docs/RFD/)**, you must first propose an [**ADR**](/docs/ADR/000_template.md).
2.  **Branch:** Create a branch from `main`: `[type]/[id]-[short-description]`.
3.  **Code & Document:**
    *   Write **Atomic Commits** following our [Commit Standards](/docs/WORKFLOW/16_commit_standards.md).
    *   **Logic over Code:** If you change system behavior, you **must** update the corresponding **[PRD](/docs/PRD/)** or **[RFD](/docs/RFD/)** files within the same Pull Request.
4.  **Verify:** Ensure CI checks pass locally (e.g., `linter`, `tests`, `typing`).
5.  **Submit:** Open a Pull Request using our [Standard Template](/.github/PULL_REQUEST_TEMPLATE/standard_pr_template.md).

---

## 🤝 Blameless Culture
If you introduce a bug or break the build, don't worry. We focus on **mitigation, not finger-pointing.** We work together to identify how our documentation or automated checks failed to catch the error, and we improve the system to prevent it from happening again.

---

## ⚖️ Quality Standards

To have a Pull Request merged, it must meet these criteria:
*   **Atomic Logic:** The PR solves exactly one Issue.
*   **Documentation:** All technical pivots are recorded in an [ADR](/docs/WORKFLOW/17_adr_standards.md).
*   **Green CI:** The pipeline must be 100% green (✅).
*   **Peer Approval:** At least one Maintainer must approve the architectural approach.

---

## 💬 Communication
If you are unsure about an approach, please open a **Research/Spike** issue or start a [discussion](https://github.com/joelabreurojas/SSOT/discussions) before beginning implementation.

**Happy Coding!**
