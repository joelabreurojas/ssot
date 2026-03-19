# Project Lifecycle

The development cycle is a structured, phased approach that moves from abstract ideas to concrete implementation. To maintain high quality and prevent re-work, **Phase 0 must be completed and approved before Phase 1 begins.**

---

### 1. Phase 0: Inception & Design (The Source of Truth)
Before writing code, we define the boundaries of the problem and the architecture of the solution. This phase results in a modular documentation set that acts as the blueprint for the entire project.

*   **PRD (Product Requirements Document):** Defines the "What" and "Why." Focuses on user stories and business logic.
*   **RFD (Request for Design):** Defines the "How." Focuses on the technical specification, data models, and API contracts.
*   **VIEWS:** Visualizes the user experience through sketches or wireframes to align the interface with the requirements.

### 2. Phase 1: Planning
Once the technical "How" is defined, we break the work into manageable, trackable pieces.

*   **Milestones (Epics):** We identify the high-level **Modules** from the RFD. Each Milestone represents a vertical slice of functional value.
*   **Issues (Tasks):** We populate Milestones with discrete tasks. Each task is assigned a numeric **Execution Order** and clear **Dependencies** to create an optimized development roadmap.

### 3. Phase 2: Execution
The actual development phase where the system is built according to the standards established in the previous phases.

*   **Coding:** Developers follow the [Branch Flow](./10_branch_flow.md), working on one Issue at a time.
*   **Atomic Progress:** Work is saved through [Atomic Commits](./11_commit_standards.md) that mirror the Task's To-Do list.
*   **Refinement (ADRs):** When significant technical pivots occur during coding that deviate from the RFD, they are recorded as [Architecture Decision Records](./04_adr_standards.md).

### 4. Phase 3: Review & Delivery
The final gate before code reaches the production environment.

*   **Pull Request:** The developer tells the story of the solution and provides testing instructions.
*   **Peer Review:** A human reviewer verifies logic and architecture, while the CI pipeline verifies style and stability.
*   **Merge:** Successful tasks are "Squashed and Merged" into `main`, and the cycle begins again for the next task in the Execution Order.
