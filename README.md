# 🏛️ SSOT: Single Source of Truth

> *The definitive starter kit for a world-class engineering culture and development lifecycle.*

This repository contains the blueprints, templates, and modular documentation required to bootstrap any new software project with a professional engineering culture from Day 1. 

Our core philosophy is **Clarity over Complexity, and Momentum over Stagnation.** We favor simple, robust processes that eliminate toil through automation and AI, while ensuring high-quality code, intentional design, and a blameless culture.

---

## 📦 Repository Structure

This SSOT is divided into two main components: **Theory** and **Practice**.

### 1. `WORKFLOW/` (The Theory)
The official manual detailing our 19-chapter engineering "constitution." It defines the rules of the house and the actionable phases of development:
*   **Phase 0: Foundations & Guidelines** (Mindset, Community, Technical Standards)
*   **Phase 1: Inception & Strategic Design** (PRD, Roadmap, RFD, AI-Driven Views)
*   **Phase 2: Planning & Orchestration** (Milestones, Issues, Kanban)
*   **Phase 3: Execution & Tracking** (Branch Flow, Commits, ADRs)
*   **Phase 4: Review, CI/CD & Delivery** (Pull Requests, Release Automation)

👉 **[Read the Workflow Manual here](./WORKFLOW/README.md)**

### 2. `EXAMPLES/` (The Practice)
Blank, "plug-and-play" blueprints that enforce the workflow rules:
*   **`docs/`**: Modular folders for Product Requirements (PRD), Technical Specs (RFD), Decision Records (ADR), and history (Changelog).
*   **`VIEWS/`**: The AI-generation prompt framework for rapid UI/UX design.
*   **`milestones/`**: Structure for "Project Planning as Code" (Epics and Tasks).
*   **`issues/` & `pull_requests/`**: Automated GitHub templates.
*   **`community/`**: Social and security contracts (Contributing, Security Policy, Governance).

---

## 🧭 Core Engineering Pillars

*   **Design-First & JIT Engineering:** we design the "How" (RFD) only for what we are building "Now" (Roadmap) to prevent over-engineering.
*   **Blameless Culture:** We investigate system failures and improve our "insurance layers" (CI/Tests) rather than assigning individual blame.
*   **1 Issue = 1 Branch = 1 PR:** We build in atomic vertical slices to maintain continuous momentum.
*   **Automation & AI Native:** We aggressively use GitHub automation (Rulesets, Scanning, Dependabot) and AI assistants (v0, Google Stitch) to translate ideas into verified code.
*   **Documentation-as-Code:** All requirements and decisions live in the repository and evolve via Pull Requests. **"What's not on paper didn't exist."**

---

## 🚀 How to Bootstrap a New Project

To initialize a new project with these standards, follow these steps:

### Step 1: Establish the Rules
Copy the entire `WORKFLOW/` directory into the root of your new repository. This manual becomes the single source of truth for all team members.

### Step 2: Establish the Community
Copy the contents of `EXAMPLES/community/` to the root of your project. Update the `GOVERNANCE.md`, `SECURITY.md`, and `CODE_OF_CONDUCT.md` with your specific project contacts.

### Step 3: Configure GitHub Automation
1. Create a `.github/` folder in your new repository and copy:
   *   `EXAMPLES/issues/` -> `.github/ISSUE_TEMPLATE/`
   *   `EXAMPLES/pull_requests/standard_pr_template.md` -> `.github/pull_request_template.md`
2. **Enable DevSecOps:** In GitHub Settings, turn on **Secret Scanning**, **Dependabot**, and **CodeQL**.
3. **Enforce Rulesets:** Set `main` to allow **Squash Merges only** and require a passing CI pipeline for all merges.

### Step 4: Start Phase 1 (Design-First)
Copy the `EXAMPLES/docs/` and `EXAMPLES/VIEWS/` folders. Begin defining the **PRD** and the **Roadmap** before writing code.

### Step 5: Mandatory Developer Setup
Every developer must run the following command in their local terminal to enforce our commit standards:
```bash
git config --local commit.template EXAMPLES/commits/git_commit_template.txt
```

---

## 🤝 Evolving the Standards

This SSOT is a living system. If a rule causes friction or a template is missing a field, we fix it. To propose changes, open a PR against this repository with a clear rationale for the improvement.
