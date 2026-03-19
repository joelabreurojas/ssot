# Labeling System

We use a strict, three-part labeling system to categorize every issue. This allows us to filter the Kanban board instantly and provides immediate visual context. Every issue must have at least one label from each category.

---

### 1. Priority (Urgency & Strategic Importance)
Priority labels define the order of attention and the "Critical Path" of the Milestone.

*   🔴 **`priority:critical`** (`#d73a4a`) - Blocks all other development or represents a severe production failure. Must be addressed immediately.
*   🟠 **`priority:high`** (`#f9d0c4`) - Essential for the current milestone. Part of the core delivery.
*   🟡 **`priority:medium`** (`#fef2c0`) - Standard task that should be completed within the current phase.
*   🟢 **`priority:low`** (`#c5def5`) - Optimization, minor polish, or a task that can be deferred if time runs out.

---

### 2. Type (Nature of the Work)
Type labels describe what kind of activity the developer will be performing.

*   ✨ **`type:feature`** (`#a2eeef`) - New functionality or core business logic.
*   🐞 **`type:bug`** (`#d73a4a`) - Correction of unintended or incorrect behavior.
*   🛠️ **`type:chore`** (`#ededed`) - Maintenance, refactoring, or DevOps tasks (no logic changes).
*   🔬 **`type:research`** (`#d4c5f9`) - Time-boxed investigation, Spike, or technical proof-of-concept.
*   🧪 **`type:testing`** (`#006b75`) - Focused exclusively on writing or improving automated tests.
*   📖 **`type:documentation`** (`#0075ca`) - Writing or updating PRDs, RFDs, or user guides.

---

### 3. Module (Technical/Business Domain)
Module labels identify which part of the architecture the task touches. These should remain neutral in color (e.g., default gray or white) to avoid clashing with Priority/Type colors.

*   **`module:api`** - Backend endpoints, controllers, and external integration.
*   **`module:ui`** - Frontend components, templates, and client-side logic.
*   **`module:auth`** - Authentication, authorization, and session security.
*   **`module:database`** - Data models, schemas, and migrations.
*   **`module:devops`** - CI/CD pipelines, Docker, and deployment logic.
*   **`module:observability`** - Logging, metrics, and health monitoring.
*   **`module:general`** - Cross-cutting tasks that apply to the whole project.

---

### 🎨 Key Principle: Visual Scannability
The goal of this system is to look at a list of 50 issues and immediately spot the "Red" (Critical bugs) and the "Cyan" (New features). Always ensure labels are applied correctly before moving an issue from the **Backlog** to **Ready**.
