<h1 align='center'>
    🏛️ SSOT
</h1>

<p align='center'>
    <em>A living Single Source of Truth for professional development lifecycles.</em>
</p>

<h6 align='center'>
   <a href="/LICENSE">
      <img alt='MIT License' src='https://img.shields.io/static/v1.svg?label=License&message=MIT&logoColor=d9e0ee&colorA=302d41&colorB=3094FF'/>
   </a>
   <a href="/docs/WORKFLOW/README.md">
      <img alt='RTFM' src='https://img.shields.io/static/v1.svg?label=Guide&message=Workflow&logoColor=d9e0ee&colorA=302d41&colorB=3094FF'/>
   </a>
   <a href="/docs/">
      <img alt='See Documentation' src='https://img.shields.io/static/v1.svg?label=Docs&message=Folder&logoColor=d9e0ee&colorA=302d41&colorB=3094FF'/>
    </a>
</h6>

&nbsp;

### ✨ Overview

The **SSOT (Single Source of Truth)** is an opinionated engineering standard designed to bootstrap new software projects with a lean, secure and effective workflow.

**This helps teams to:**
- Establish non-negotiable standards for APIs, Security, and Testing before writing code.
- Use "Just-In-Time" design to focus engineering effort only on immediate Roadmap priorities.
- Leverage AI-driven UI generation and GitHub automation to accelerate development.
- Operate under a **Blameless Culture** that prioritizes system improvements over individual blame.
- ...and more!

&nbsp;

### 🚀 Quickstart

To initialize your new project using this engineering standard:

1. Click the green **"Use this template"** button at the top of this repository to create your new project.
2. Update markdown files in the project root with the project name and contact details.
3. Enable **GitHub Discussions** for brainstorming and **Wikis** for long-form manuals.
4. In GitHub Settings, enable **Secret Scanning**, **Dependabot**, and **CodeQL Analysis**.
5. Set `main` to allow **Squash Merges only** and require a green CI pipeline for all merges.


> [!NOTE]
> Every contributor must run this command in their local terminal to enforce atomic commit standards:
> ```bash
>  git config --local commit.template .github/commits/git_commit_template.txt
> ```

&nbsp;

### 🏛️ Pillars

This project is governed by 19 chapters of modular documentation following a strict development lifecycle.

<div align="center">

| Pillar | Strategy | Goal |
| :--- | :--- | :--- |
| **Blameless** | System-First Mindset | Fix the automation, not the person. |
| **Design-First** | JIT Engineering | Technical design only for what we build **NOW**. |
| **Atomic** | 1 Issue = 1 Branch | Maintain momentum via vertical functional slices. |
| **Contract-Led** | Pure Interfaces | Enforce strict API versioning and idempotency. |
| **Quality** | Test Pyramid | Mandatory 80% coverage on business logic with automated CI gatekeepers. |
| **Security** | DevSecOps | Secret scanning and OIDC trust relationships baked into the lifecycle. |
| **AI-Assisted**| Structured Prompting | Leverage AI for UI generation and test scaffolding. |
| **Pipeline-Gated** | Static & Logic Analysis | Continuous verification as the ultimate merge authority. |


</div>

&nbsp;

### 📚 Scaffolding

The system is modularized to prevent information rot and cognitive load:

**1. Workflow**
The official 19-chapter manual that defines our constitution.
*   **Phase 0: Foundations & Guidelines** (Mindset, Community, Technical Standards)
*   **Phase 1: Inception & Strategic Design** (PRD, Roadmap, RFD, AI-Driven Views)
*   **Phase 2: Planning & Orchestration** (Milestones, Issues, Kanban)
*   **Phase 3: Execution & Tracking** (Branch Flow, Commits, ADRs)
*   **Phase 4: Review & Delivery** (Pull Requests, Release Automation)

> [!IMPORTANT]
> 👉 **[Read the Workflow Manual here.](/docs/WORKFLOW/README.md)**

**2. Blueprints**
"Plug-and-play" templates for project planning:
*   **[PRD](/docs/PRD/):** Modular Product Requirements (The What).
*   **[ROADMAP](/docs/ROADMAP.md):** Strategic sequencing (Now, Next, Later).
*   **[RFD](/docs/RFD/):** JIT Technical specifications (The How).
*   **[VIEWS](/docs/VIEWS/):** AI-driven UI design framework.
*   **[Milestones](/docs/milestones/):** Project Planning as Code (Epics and Tasks).
*   **[ADR](./docs/ADR/):** Chronological record of technical pivots.
*   **[CHANGELOG](/docs/CHANGELOG.md):** Human-readable history of value delivered.

&nbsp;

### 📌 Disclaimer: What SSOT is NOT

To maintain clarity and prevent the misuse of this framework, understand that:

*   **NOT a Runtime Framework:** This is metadata scaffolding. It provides the "constitution" and the "folders," but the business logic is entirely yours to write.
*   **NOT Stack-Dependent:** It is technology-agnostic. It works for embedded C++, cloud microservices, or mobile apps.
*   **NOT Waterfall:** We do not design the entire project upfront. We design only what is in the **NOW** column of the Roadmap.
*   **NOT a Passive Reference:** It is an active operating system. If the team ignores the Branch Flow or Commit Standards, the SSOT ceases to exist.
*   **NOT a Replacement for Talent:** High-quality templates do not fix poor architecture. This is a **force multiplier** for skilled engineers.

&nbsp;

### 👐 Contribute

- Have a question or an idea? Feel free to open a new [discussion](https://github.com/joelabreurojas/SSOT/discussions)!
- Found a bug? Report it following our [Security Policy](/SECURITY.md).

Please, read our [Contribution Guidelines](/CONTRIBUTING.md) to take part in the project.
