# 🏛️ SSOT: Single Source of Truth

> *The definitive starter kit for a world-class development lifecycle.*

This repository contains the blueprints, templates, and documentation required to bootstrap any new software project with a professional engineering culture from Day 1. 

Our core philosophy is **Clarity over Complexity, and Momentum over Stagnation.** We favor simple, robust processes that get out of the developer's way while ensuring high-quality code, intentional design, and a blameless culture.

---

## 📦 Repository Structure

This SSOT is divided into two main components: **Theory** and **Practice**.

### 1. `WORKFLOW/` (The Theory)
The official manual detailing our development rules and the "Law" of the project. It is organized into a 16-chapter narrative following the project lifecycle:
*   **Phase 0: Mindset & Rules** (Philosophy, Lifecycle, Community)
*   **Phase 1: Inception & Strategic Design** (PRD, Roadmap, RFD, Views)
*   **Phase 2: Planning & Orchestration** (Milestones, Issues, Kanban)
*   **Phase 3: Execution & Tracking** (Branching, Commits, ADRs)
*   **Phase 4: Review & Delivery** (Pull Requests)

👉 **[Read the Workflow Manual here](./WORKFLOW/README.md)**

### 2. `EXAMPLES/` (The Practice)
Blank, "plug-and-play" blueprints that enforce the workflow rules:
*   **`docs/`**: Modular templates for Product Requirements (PRD), Technical Specs (RFD), UI Gallery (VIEWS), Strategic Sequencing (ROADMAP), and Decisions (ADR).
*   **`milestones/`**: The "Project Planning as Code" templates for Epics and Tasks.
*   **`issues/` & `pull_requests/`**: Automation templates for GitHub/GitLab.
*   **`commits/`**: Terminal-based blueprint for Conventional Commits.
*   **`community/`**: Social contracts (Contributing, Code of Conduct, Governance).

---

## 🚀 How to Bootstrap a New Project

To initialize a new project with these standards, follow these steps:

### Step 1: Establish the Rules
Copy the entire `WORKFLOW/` directory into the root of your new repository. This manual becomes the authority for all team members.

### Step 2: Establish the Community (Social Contract)
Copy the contents of `EXAMPLES/community/` to the root of your project. Update the `GOVERNANCE.md` and `CODE_OF_CONDUCT.md` with your specific project contacts.

### Step 3: Start Phase 1 (Design-First)
Copy the `EXAMPLES/docs/` folder to your project. 
1.  Define the **PRD** (The What).
2.  Sequence the work in the **ROADMAP** (The When).
3.  Perform **Just-In-Time (JIT) Engineering** by writing the **RFD** for the first module in the 'NOW' column.

### Step 4: Configure GitHub Automation
Create a `.github/` folder in your new repository and copy:
*   `EXAMPLES/issues/` -> `.github/ISSUE_TEMPLATE/`
*   `EXAMPLES/pull_requests/standard_pr.md` -> `.github/pull_request_template.md`

### Step 5: Developer Setup
Use the following command to enforce our commit standards:
```bash
git config --local commit.template EXAMPLES/commits/git_commit_template.txt
```

---

## 🧭 Core Engineering Pillars

*   **Design-First:** We design the "How" (RFD) only for what we are building "Now" (Roadmap).
*   **1 Issue = 1 Branch = 1 PR:** We build in vertical slices to prevent "hostage code" and maintain momentum.
*   **Atomic Commits:** Every commit is a single logical change, mapped to the task's To-Do list.
*   **Blameless Culture:** We investigate system failures rather than assigning individual blame.
*   **Documentation-as-Code:** All requirements and technical decisions (ADR) live in the repository and evolve via Pull Requests.

---

## 🤝 Evolving the Standards

This SSOT is a living system. If a rule causes friction or a template is missing a field, we fix it. To propose changes, open a PR against this repository with a clear rationale for the improvement.
