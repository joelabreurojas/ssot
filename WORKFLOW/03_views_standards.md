# UI/UX View Standards

The `docs/VIEWS/` directory contains the visual representation of the user journey. Its purpose is to provide a common visual reference for stakeholders and developers, ensuring that the interface reflects the requirements defined in the PRD.

---

### 📂 The VIEWS Directory

This directory serves as a gallery for sketches, wireframes, or mockups. 

1.  **Structural Integrity First:** Before high-fidelity design, we define the **Information Architecture (IA)**. 
    *   *Standard:* Use **Mermaid `flowchart`** or **ASCII** blocks to define component hierarchy and layout logic (e.g., "Top Nav contains Logo, Search, and Profile").
    *   *Benefit:* Text-based wireframes live in Git and allow for clear "diffs" during architecture reviews.
2.  **Visual Assets:** 
    *   Once the structure is approved, visual mockups (Figma, screenshots, or AI-generated images) are added.
    *   Store compressed `.png` or `.jpg` files directly in this folder.
    *   Document links to external canvases (e.g., Figma) in a `README.md` within this directory.

---

### 🎨 Key Standards

1.  **State Representation:** A view is incomplete if it only shows the "Happy Path." Every significant screen should document its various states:
    *   **Initial/Empty State:** What does the user see before data is added?
    *   **Loading State:** How is progress communicated?
    *   **Error State:** How are failures displayed?

2.  **File Naming Convention:** Assets must be named based on the User Story they support from the PRD.
    *   *Format:* `[UserStoryID]_[ScreenName]_[Device].ext`
    *   *Example:* `02_user_login_mobile.png`

3.  **Traceability:** Every view should be linked within the relevant User Story in `docs/PRD/02_user_stories.md`. 

---

### 🛠️ Maintenance & Changes

Visual designs are part of the project specification and must follow the same version control discipline as text documents:

*   **Design Changes:** If the UI layout changes significantly, the asset in `docs/VIEWS/` must be updated via a **Pull Request**.
*   **Approval:** Views must be reviewed alongside the PRD/RFD to ensure technical feasibility and product alignment before Phase 2 (Execution) begins.
