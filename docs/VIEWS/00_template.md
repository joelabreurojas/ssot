# View: [Screen Name]

**Associated User Story:** [e.g., US-01]  
**Device Target:** [e.g., Desktop / Mobile Web / Native App]

---

## 1. AI Generation Prompt (The Master Prompt)
<!-- 
    INSTRUCTIONS: Copy and paste this section directly into your AI UI generator 
    (e.g., Google Stitch, v0.dev, Figma AI, Claude/GPT-4). 
    Adjust the bracketed variables to match your specific screen.
-->

**System Role:** Act as an expert UX/UI designer and frontend developer. Generate a high-fidelity, accessible UI component based on the following structural constraints.

**Design System & Styling:**
*   **Vibe/Theme:** [e.g., Minimalist, SaaS dashboard, high-contrast, modern, enterprise].
*   **Framework/Library:** [e.g., Tailwind CSS, Material UI, Shadcn, plain HTML/CSS].
*   **Color Palette:** [e.g., Primary blue, slate grays for backgrounds, semantic colors for alerts].

**Information Architecture (Layout Logic):**
*   **Container:** [e.g., Full-width screen with a sticky left sidebar and a top navigation bar].
*   **Header Area:** [e.g., Needs a search input (with a Cmd+K shortcut hint), a notification bell, and a user avatar dropdown].
*   **Sidebar Area:** [e.g., Vertical navigation menu with icons for 'Home', 'Projects', and 'Settings'].
*   **Main Content Area:** [e.g., A breadcrumb trail at the top. Below that, a data table with 4 columns: Name, Status, Date, Owner. Include a pagination control at the bottom].

**Interactive Behavior:**
* [e.g., The table rows should have hover states. The 'Status' column should use colored badge indicators].

---

## 2. Component Data Binding (RFD Link)
<!-- 
    Map the UI components generated above to the actual data contracts defined in the RFD.
    This prevents frontend developers from guessing where data comes from.
-->

| UI Component | Action / Event | Data Source (RFD Contract) |
| :--- | :--- | :--- |
| **Global Search** | `onChange` / `onSubmit` | `GET /api/v1/search?q={query}` |
| **Main Data Table** | `onLoad` | `GET /api/v1/resources` (Returns `ResourceList` schema) |
| **Create Button** | `onClick` (Opens Modal) | `POST /api/v1/resources` |

---

## 3. UI State Specifications
<!-- 
    The AI must generate (or the designer must account for) these specific states.
-->
- [ ] **Empty State:** If the API returns no data for the Main Content Area, show an illustration and a prompt to "Create your first record."
- [ ] **Loading State:** When fetching data, the Main Content Area should display skeleton row loaders. The Header and Sidebar remain interactive.
- [ ] **Error State:** If the API fails, display a non-intrusive, dismissible red toast notification at the top right.
- [ ] **Success State:** When the user completes the Primary Action, show a green confirmation badge.

---

## 4. Visual Assets & Output
<!-- 
    Once the AI generates the UI and the team refines it in the design tool,
    link the final, approved asset here.
-->
*   **Approved Figma / Design Link:** `[Insert Link Here]`
*   *(Optional) Static Snapshot:* `![Screen Name Snapshot](./snapshot_US01.png)`

---
*Maintenance Note: This specification is the contract for the Frontend implementation. If the layout structure or data bindings change, this document must be updated via a Pull Request.*
