# Labeling System

We use a strict, three-part labeling system to categorize every issue. This provides immediate visual context on the Kanban board. Every issue must have at least one label from each of the three categories below.

---

### 1. Priority (Urgency & Strategic Importance)
Priority labels define the order of attention and the "Critical Path" of the Milestone.

*   🔴 **`priority:critical`** (`#d73a4a`) - Blocks all other development or represents a severe production failure. Must be addressed immediately.
*   🟠 **`priority:high`** (`#f9d0c4`) - Essential for the current milestone. Part of the core delivery.
*   🟡 **`priority:medium`** (`#fef2c0`) - A standard task that should be completed within the current phase.
*   🟢 **`priority:low`** (`#c5def5`) - An optimization, minor polish, or a task that can be deferred if time runs out.

---

### 2. Type (Nature of the Work)
Type labels describe the specific activity the developer will be performing. These map 1:1 to the prefixes used in our [Commit Standards](./13_commit_standards.md).

*   ✨ **`type:feature`** (`#a2eeef`) - New functionality or core business logic.
*   🐞 **`type:bug`** (`#d73a4a`) - Correction of unintended or incorrect behavior.
*   🛠️ **`type:chore`** (`#ededed`) - Maintenance, refactoring, or DevOps tasks (no logic changes).
*   🔬 **`type:research`** (`#d4c5f9`) - Time-boxed investigation, Spike, or technical proof-of-concept.
*   🧪 **`type:testing`** (`#006b75`) - Focused exclusively on writing or improving automated tests.
*   📖 **`type:documentation`** (`#0075ca`) - Writing or updating PRDs, RFDs, or user guides.

---

### 3. Module (Technical/Business Domain)
Module labels identify which part of the architecture the task touches. To avoid clashing with the Priority and Type colors, all Module labels must use **neutral colors** (e.g., default gray `#ededed` or white `#ffffff`).

*   **`module:api`** - Backend logic, endpoints, and controllers.
*   **`module:ui`** - Frontend components, templates, and client logic.
*   **`module:auth`** - Authentication, authorization, and security logic.
*   **`module:database`** - Data models, schemas, and migrations.
*   **`module:devops`** - CI/CD pipelines, Docker, and infrastructure.
*   **`module:observability`** - Logging, metrics, and health monitoring.
*   **`module:general`** - Cross-cutting tasks that apply to the whole project.

---

### 🎨 Key Principle: Visual Scannability
The goal of this system is to look at a board of 50 issues and immediately spot the "Red" (Critical bugs) and the "Cyan" (New features). 

*   **Before Moving to Ready:** Ensure all three labels are applied.
*   **No Redundant Titles:** Do not include `[FEAT]` or `[BUG]` in the Issue title itself; the labels provide this information automatically.
