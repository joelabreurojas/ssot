# Request for Design (RFD) Standards

The RFD is the **Technical Specification**. It translates the requirements from the PRD into a concrete engineering plan. It serves as the primary reference for developers during the execution phase. To ensure maintainability, the RFD is stored as a modular folder in `docs/RFD/`.

---

### 📂 Structure of the RFD Folder

Every project must initialize its RFD folder with the following structure:

1.  **`README.md`**: The entry point. Contains the **High-Level Architecture** and the chosen technology stack summary.
    *   *Standard:* Use **Mermaid `graph TD` or `subgraph`** blocks to visualize system components and data flow.
2.  **`01_structure.md`**: Defines the proposed directory structure, core module boundaries, and external dependencies (libraries, frameworks, third-party services).
3.  **`02_data_model.md`**: Details the data layer. 
    *   *Standard:* Use **Mermaid `erDiagram`** blocks to define entities, attributes, and relationships (1:1, 1:N, N:N).
4.  **`03_interface.md`**: Defines how the system interacts with the outside world. Includes API design (endpoints, payloads, status codes) and web route structures.
5.  **`04_logic.md`**: Outlines the business logic layer. Defines core services, significant method signatures, and security implementation.
6.  **`05_ops.md`**: Documents the operational strategy, including testing, deployment, and monitoring.

---

### 🏗️ Key Principles

1.  **Diagrams-as-Code:** We favor **Mermaid.js** over static images. Since diagrams are written in text, they are version-controlled, searchable, and produce clean "diffs" during Pull Requests.
2.  **The Source of Truth:** The RFD is the definitive guide for implementation. If the code and the RFD disagree, the RFD must be followed or formally updated.
3.  **Architecture over Implementation:** Focus on the "How" at a high level. Use pseudocode and method signatures rather than large blocks of implementation code.
4.  **Modular Reviewability:** By splitting the design into files, a change to the database schema only requires a review of `02_data_model.md`.

---

### 🛠️ Maintenance & Evolution

*   **Updating Diagrams:** When the architecture or data model evolves, update the Mermaid code within the relevant `.md` file. 
*   **PR Documentation:** Use the **Pull Request description** to explain why the architectural pivot was necessary.
*   **Keep in Sync:** The RFD must always be aligned with the PRD. If a technical constraint requires a change in product behavior, the PRD must be updated first.
