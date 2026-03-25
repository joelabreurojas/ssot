# UI/UX Views: [Project Name]

> _Visualizing the user journey from structure to aesthetics._

This directory contains the visual specifications for the project. We follow a **Structure-First** approach, ensuring Information Architecture is solid before finalizing visual details.

---

### 🛠️ Design Tooling
*   **Master Design File:** [Link to Figma / Penpot / Other]
*   **Design System / UI Kit:** [Link to reference, if any]

---

### 🎨 Visual Language
<!-- 
    Briefly describe the intended "feel" of the UI.
    Example: Minimalist, Professional, High-Contrast, etc.
-->
[Insert design philosophy here]

---

### 📂 View Index (Linked to User Stories)
<!-- 
    List the views stored in this folder. 
    Ensure they follow the naming convention: [UserStoryID]_[ScreenName]_[Device].
-->

| Source | Description | Supported User Story |
| :--- | :--- | :--- |
| `01_dashboard_desktop.png` | Main user landing view | [US-01](../prd/02_user_stories.md) |
| `02_login_mobile.png` | Authentication screen | [US-02](../prd/02_user_stories.md) |

---

### 🚦 State Checklist
Every view submission must consider the following states to be considered "Done":
- [ ] **Empty State:** No data available.
- [ ] **Loading State:** Data is being fetched.
- [ ] **Error State:** Validation failures or system crashes.
- [ ] **Success State:** Feedback for completed actions.
