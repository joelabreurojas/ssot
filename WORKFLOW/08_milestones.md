# Milestone Standards (The Epic)

A Milestone in this project is a high-level **Epic**. It represents the complete development of a single **Business Module** or **Core Feature set** (e.g., User Management, Billing, Analytics). 

Instead of grouping tasks by time (like traditional weeks), our Milestones group tasks by **Domain**. We focus entirely on one area of the system until it is functional across all architectural layers.

---

### 🏛️ Structure of a Milestone

Every Milestone acts as a parent container for a group of related **Issues (Tasks)**. A Milestone is defined by three pillars:

1.  **Narrative Title:** The title must immediately identify the business domain being built.
    *   *Examples:* `M1: Core Infrastructure`, `M2: User Authentication`, `M3: Payment Integration`.
2.  **The "Now" Requirement:** A Milestone can only be initialized and populated with Tasks once it has moved into the **🟢 NOW** column of the [**Roadmap**](./05_roadmap_standards.md).
3.  **Vertical Slice Progression:** To fulfill a Module, we build through the architectural layers in sequence:
    1.  **Data Layer:** Schemas, models, and migrations.
    2.  **Logic Layer:** Core business services and rules.
    3.  **Interface Layer:** API endpoints, controllers, or contracts.
    4.  **Presentation Layer:** The User Interface (matching the VIEWS).
    5.  **Quality Assurance:** Automated tests and documentation updates.

---

### ✅ Definition of Done (DoD)

A Milestone is considered complete only when it meets the following criteria:

*   **Functional Outcome:** The tangible, real-world state described in the [**Milestone Blueprint**](../EXAMPLES/milestones/milestone_blueprint.md) is achieved (e.g., "Users can successfully log in").
*   **Vertical Slice Checklist:** Every layer of the architecture (Data to UI) is operational and verified.
*   **Technical Integrity:** All child Issues are closed, 100% of the new logic is covered by tests, and all technical pivots are recorded in ADRs.

---

### 🚦 Management & Visibility

*   **Offline Backup:** Every Milestone must have a corresponding folder in the project's planning directory, containing a `README.md` (based on the `milestone_blueprint.md`) and individual Markdown files for each Task.
*   **Issue Tracker Sync:** The "Task Index" within the Milestone folder serves as the master checklist for populating the project's GitHub/GitLab board.
*   **Focus:** To maintain momentum and avoid context-switching, we aim to have no more than two Milestones in the "Active" state at once.

---

### 🚀 Selecting Work
When a Milestone is active, developers pick the next available Task based on the **Execution Order** and **Dependency** logic defined in the [**Issue Standards**](./09_issue_standards.md).
