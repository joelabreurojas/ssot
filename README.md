# 🏛️ SSOT: Single Source of Truth

> *Engineering Standards & Workflow for our software development lifecycle.*

This repository contains the blueprints, templates, and documentation required to bootstrap any new software project with a world-class, professional engineering culture from Day 1. 

Our core philosophy is **Clarity over Complexity, and Momentum over Stagnation.** We favor simple, robust processes that get out of the developer's way while ensuring high-quality, auditable code and a blameless culture.

---

## 📦 Repository Structure

This starter kit is divided into two main components: Theory and Practice.

### 1. `WORKFLOW/` (The Theory)
The official manual detailing our development rules, from inception to deployment. It is organized into 5 phases:
*   **Phase 0:** Mindset & Rules (Philosophy, Community Standards)
*   **Phase 1:** Inception & Design (PRD, RFD, Views)
*   **Phase 2:** Planning & Orchestration (Milestones, Kanban, Labels)
*   **Phase 3:** Execution & Tracking (Branching, Commits, ADRs)
*   **Phase 4:** Review & Delivery (Pull Requests)

👉 **[Read the Workflow Manual here](./WORKFLOW/README.md)**

### 2. `EXAMPLES/` (The Practice)
Blank, ready-to-use templates that enforce the workflow rules. 
*   `docs/`: Modular templates for Product Requirements (PRD), Technical Specs (RFD), Visuals (VIEWS), and Decisions (ADR).
*   `milestones/`: The offline project planning templates (Epics and Tasks).
*   `issues/` & `pull_requests/`: Standardized GitHub templates.
*   `commits/`: The Conventional Commits terminal blueprint.
*   `community/`: Governance, Code of Conduct, and Contributing guides.

---

## 🚀 How to Bootstrap a New Project

When starting a new repository, use this SSOT as your foundation:

### Step 1: Establish the Rules
Copy the entire `WORKFLOW/` directory into the root of your new project, or link to this repository as a submodule.

### Step 2: Establish the Community
Copy the contents of `EXAMPLES/community/` to the root of your new project. Fill in the specific project details.

### Step 3: Establish the Design (Phase 0)
Copy the `EXAMPLES/docs/` folder to the root of your new project. Begin filling out the `PRD/` and `RFD/` folders to define the "What" and the "How" before writing any code.

### Step 4: Establish GitHub Automation
Copy `EXAMPLES/issues/` and `EXAMPLES/pull_requests/` into a `.github/` folder in your new repository to automate your task formatting.

### Step 5: Developer Setup
We provide a template that can be enabled by running this command to enforce atomic, conventional commits in their terminal:
```bash
git config --local commit.template EXAMPLES/commits/git_commit_template.txt
