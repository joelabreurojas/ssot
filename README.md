# 🏛️ Project Engineering Standards

> *The definitive starter kit and single source of truth for our software development lifecycle.*

This repository contains the blueprints, templates, and documentation required to bootstrap a new software project with a world-class, professional engineering culture. 

---

## 📦 What's Included?

This starter kit provides a zero-friction way to standardize your repository. It includes:

1. **`WORKFLOW.md`**: The definitive guide to our Kanban process, branching strategy, and definitions of "Done."
2. **Issue Templates**: Pre-configured GitHub Issue templates for Features, Bugs, Chores, and Research Spikes that enforce clear requirements and acceptance criteria.
3. **Pull Request Templates**: Standardized PR structures that ensure reviewers have all the context they need (including a specialized template for Stacked PRs).
4. **Commit Message Template**: A `.txt` blueprint to enforce the Conventional Commits specification directly in the developer's terminal.
5. **Milestone Blueprint**: A structural guide for planning cohesive phases of development.

---

## 🧭 The Core Pillars of Our Workflow

If you only read one section, read this. For the full details, consult [`WORKFLOW.md`](./WORKFLOW.md).

*   **1 Issue = 1 Branch = 1 PR:** We build atomically. Keep your branches focused on solving a single problem to prevent review fatigue and deployment bottlenecks.
*   **The CI Pipeline is the Gatekeeper:** No code merges into `main` unless the automated CI checks (linting, typing, testing) are green (✅).
*   **Conventional Commits Only:** We use prefixes like `feat:`, `fix:`, and `chore:` to create a machine-readable, easily searchable project history.
*   **Labels over Prefixes (For Issues):** We rely on GitHub's powerful labeling system (`type:feature`, `priority:high`, `module:api`) to organize work, keeping Issue titles clean and readable. 
*   **Peer Review is Mandatory:** Code is a team effort. Every PR requires at least one formal approval before merging.

---

## 🤝 Proposing Changes to the Standards

These standards are meant to be a living breathing process. If a workflow rule is slowing the team down, we want to fix it.

To propose a change to these standards:
1. Open a new Pull Request modifying the relevant template or the `WORKFLOW.md` file.
2. Tag the engineering leadership for review. 
3. Provide a clear rationale for *why* the change improves clarity or momentum.
