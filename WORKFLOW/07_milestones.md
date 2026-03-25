# Milestone Standards (The Epic)

A Milestone in this project is a high-level **Epic**. It represents the complete development of a single **Business Module** or **Core Feature set** (e.g., User Management, Billing, Data Engine). 

Instead of grouping random tasks by time (like traditional weeks), our Milestones group tasks by **Domain**. We focus entirely on one area of the system until it is functional from the data layer all the way to the user interface.

---

### 🏛️ Structure of a Milestone

Every Milestone acts as a parent container for a group of related **Issues (Tasks)**. A Milestone is defined by three pillars:

1.  **Narrative Title:** The title must immediately identify the business domain being built.
    *   *Bad:* `Milestone 2` or `Sprint 4`
    *   *Good:* `M1: The Core Foundation`, `M2: User Management Module`, `v1.2: Payment Gateway`
2.  **Definition of Done (DoD):** A Milestone is complete *only* when the high-level objective is met and verified. Closing all child Issues is a prerequisite, but final verification happens at the Milestone level.
    *   *Example:* "The user database is ready, authentication services are implemented, and the Login/Register interface is fully functional and tested end-to-end."
3.  **Vertical Slice Progression:** To fulfill a Module, we build "top-to-bottom" through the architectural layers:
    1.  **Data Layer:** Schemas and models.
    2.  **Logic Layer:** Core business services and rules.
    3.  **Interface Layer:** APIs or Controllers.
    4.  **Presentation Layer:** The User Interface or external consumer.
    5. **Quality Assurance:** Tests and documentation.

---

### 📈 The Roadmap Logic

*   **Focus:** Only one or two Milestones should be "In Progress" at a time to prevent team fragmentation. 
*   **Cohesion:** If a task does not directly serve the Module currently in development, it belongs in the Backlog or a future Milestone.
*   **Visibility:** The Milestone Blueprint (`milestone_blueprint.md`) in the `EXAMPLES/` folder serves as the offline backup and index for all child tasks within an Epic.

---

### 🚀 Selecting Work

When a developer is ready for a new task, they pick the next available Issue within the active Milestone based on the **Execution Order** and **Dependency** rules. This ensures the foundation is always built before the roof. (See [Issue Standards](./08_issue_standards.md)).
