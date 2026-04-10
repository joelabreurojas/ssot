# Visual Design (VIEWS) & AI Generation

The `docs/VIEWS/` directory contains the visual representation of the user journey. Its purpose is to provide a common reference for stakeholders and developers, ensuring the interface accurately reflects the requirements defined in the PRD.

To maximize momentum, we aggressively eliminate toil by leveraging **AI-driven UI generation** (e.g., Google Stitch, v0.dev, Figma AI). Instead of manually drawing wireframes, we write highly structured definitions that act as **Master Prompts** for the AI.

---

### 1. The "Structure-First" AI Workflow

We do not ask AI to "design a dashboard." We provide it with strict architectural constraints based on our PRD. 

The workflow is as follows:
1.  **Define the Data (The Markdown):** Use the `VIEWS/00_template.md` to define the Information Architecture (IA). What data must be displayed? What buttons exist? 
2.  **Generate (The AI):** Feed the markdown specification and the associated PRD User Story into the UI generation tool.
3.  **Refine (The Human):** Export the generated layout to your design system (e.g., Figma) to align colors, typography, and brand constraints.
4.  **Commit (The SSOT):** Save the permanent link to the Figma file (or a static image export) back into the `VIEWS/` markdown file.

---

### 2. The View Specification (The Master Prompt)

Every screen must have a markdown file in the `VIEWS/` directory. This file serves as the technical requirement for the Frontend implementation and the prompt for the AI.

It must include:
*   **Component Inventory:** A strict list of all functional zones (e.g., Global Search, Sidebar, Main Data Grid).
*   **Data Contracts:** What backend data is driving this view? (Linked to the RFD API design).
*   **Interaction Logic:** What happens when the user clicks the primary action? (e.g., "Triggers a POST request and shows a success toast").

---

### 3. State Specifications (Mandatory)

AI tools are biased toward the "Happy Path." As engineers, we must explicitly prompt the AI to design for failure and latency. Every view specification **must** demand designs for the following states:

*   **Initial/Empty State:** What the user sees before data is available (e.g., "Upload your first document").
*   **Loading State:** How progress is communicated (e.g., Skeleton loaders, spinners).
*   **Error State:** How validation failures or system errors are displayed (e.g., Inline red text, global alert banners).
*   **Success State:** Confirmation of completed actions.

---

### 4. Traceability and File Naming

To ensure every screen is justified by a business need, visual assets and markdown specs must be named based on the User Story they support from the PRD.

*   **Format:** `[UserStoryID]_[ScreenName]_[Device].md`
*   **Example:** `US02_user_login_mobile.md`

Every view file must contain a hyperlink back to the PRD (`docs/PRD/02_user_stories.md`), ensuring bi-directional traceability between the Business Requirement and the Visual Interface.
