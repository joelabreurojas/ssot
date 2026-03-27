# Visual Design (VIEWS) Standards

The `docs/VIEWS/` directory contains the visual representation of the user journey. Its purpose is to provide a common visual reference for stakeholders and developers, ensuring the interface accurately reflects the requirements defined in the PRD and the architecture in the RFD.

---

### 📂 The VIEWS Directory

This directory serves as a gallery for sketches, wireframes, or mockups. 

1.  **Structural Integrity First:** Before high-fidelity design, we prioritize defining the **Information Architecture (IA)** and layout logic.
    *   **Standard:** Use **Mermaid `flowchart`** or **ASCII** blocks directly in Markdown files (e.g., `login_flow.md`) to define component hierarchy and user navigation.
    *   **Benefit:** Text-based wireframes live in Git, allowing for clear "diffs" during structural reviews and version control.
2.  **Visual Assets:** 
    *   Once the structure is approved, visual mockups (Figma, screenshots, or AI-generated images) are added.
    *   Store compressed `.png` or `.jpg` files directly in this folder.
    *   Document links to external canvases (e.g., Figma) in a `README.md` within this directory.

---

### 🎨 Key Standards

1.  **State Representation:** A view is incomplete if it only shows the "Happy Path." Every significant screen should document its various states:
    *   **Initial/Empty State:** What the user sees before data is available.
    *   **Loading State:** How progress is communicated (e.g., spinners).
    *   **Error State:** How validation failures or system errors are displayed.
    *   **Success State:** Confirmation of completed actions.

2.  **File Naming Convention:** To ensure traceability, visual assets must be named based on the User Story they support from the PRD.
    *   *Format:* `[UserStoryID]_[ScreenName]_[Device].ext`
    *   *Example:* `US02_user_login_mobile.png`

3.  **Traceability:** Every view (or a link to it) should be integrated within the relevant User Story in `docs/PRD/02_user_stories.md`.

---

### 🛠 Maintenance & Changes

Visual designs are part of the project specification and must follow the same version control discipline as text documents:

*   **Design Changes:** If the UI layout changes significantly, the asset in `docs/VIEWS/` must be updated via a **Pull Request**.
*   **Approval:** Views must be reviewed alongside the PRD/RFD to ensure technical feasibility and product alignment before Phase 2 (Planning & Orchestration) begins.
