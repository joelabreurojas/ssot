# View: [Screen Name]

**Associated User Story:** [e.g., US-XX]  
**Device Target:** [e.g., Desktop / Mobile / Responsive]

---

## 1. Information Architecture (Structure)
<!-- 
    Define the spatial layout and component hierarchy. 
    The ASCII map below provides the blueprint for functional zones.
-->

### 🗺️ Structural Wireframe (Spatial Map)
```text
+---------------------------------------------------------------------------------------+
| [A] BRANDING [B] [Global Search... (Shortcut)]          [Global Utilities] [C] [User] |
+------------+--------------------------------------------------------------------------+
|            |                                                                          |
| [D] PRIMARY| [G] Breadcrumbs > **VIEW TITLE**                   [Actions] [Utilities] |
|    ACTION  |                                                                          |
|            +--------------------------------------------------------------------------+
| [E] MAIN   |                                                                          |
|     NAV    | [H] [Local Search...   ] [Filter V] [Sort V]            [Layout Toggles] |
| > Link 1   |                                                                          |
| > Link 2   | +----------------------------------------------------------------------+ |
| > Link 3   | | DATA HEADER / ATTRIBUTE LABELS                                       | |
|            | |---------------------|---------------|---------------|----------------| |
| ---------- | | [ ] Record Entry A  | [● Status   ] | Data Field    | Metadata       | |
| [F] CONTEXT| | [ ] Record Entry B  | [○ Status   ] | Data Field    | Metadata       | |
|     AREA   | | [ ] Record Entry C  | [● Status   ] | Data Field    | Metadata       | |
| (Recents / | |                                                                      | |
|  Folders)  | +----------------------------------------------------------------------+ |
|            |                                                                          |
| [ < ] COLL.| [Display Summary / Count]             [ < Prev ] [ 1 ]  2  3  [ Next > ] |
+------------+--------------------------------------------------------------------------+
| [vX.X.X]   | [System Status / Environment]                  [Help] [Legal] [Config V] |
+------------+--------------------------------------------------------------------------+
```

### 🧱 Component Inventory & Functional Specification
| ID | Component | Responsibility / Logic |
| :--- | :--- | :--- |
| **A** | **Branding** | Identity/Logo; defines the link back to the primary landing page. |
| **B** | **Global Search** | System-wide search functionality and keyboard access logic. |
| **C** | **User Profile** | Personalization hub; handles settings, profile access, and logout. |
| **D** | **Primary Action** | The highest-priority CTA (Call to Action) for this view's context. |
| **E** | **Main Nav** | Primary navigation links to major modules/domains. |
| **F** | **Context Area** | Sub-navigation or context-specific items (e.g., recents, favorites). |
| **G** | **View Header** | Contextual orientation (Breadcrumbs) and view-level actions. |
| **H** | **View Controls** | Mechanisms for manipulating the specific data set shown in [I]. |
| **I** | **Content Canvas** | The primary payload of the view (e.g., Table, Feed, Graph, Form). |
| **J** | **System Footer** | Metadata (versioning, health) and persistent secondary links. |

---

## 2. Interaction Logic & User Flow
<!-- 
    Describe how the user interacts with the logic of this specific screen.
-->
*   **Initialization:** [What happens when the user lands here? e.g., Trigger fetch for Zone I].
*   **Navigation Flow:** [How does clicking components change the view or state?].
*   **Data Lifecycle:** [How are creates/updates handled within the UI components?].

---

## 3. State Specifications
<!-- 
    Define the UI behavior for the four standard states.
-->
*   **Initial / Empty:** [What is displayed when no data is present in Zone I?].
*   **Loading:** [How is the waiting state represented? e.g., Skeletons, spinners].
*   **Error:** [How are failures (network, validation) displayed to the user?].
*   **Success:** [How is a completed action confirmed?].

---

## 4. Visual Assets
<!-- 
    Link to high-fidelity designs or screenshots here.
-->
*   **High-Fidelity Mockup:** `[Link to Figma Frame / Penpot / Image Asset]`

---
*Maintenance Note: This text-based wireframe is the authority for the Frontend implementation. Spatial changes or functional zone additions must be updated here via Pull Request.*
