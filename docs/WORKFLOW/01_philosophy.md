# Core Philosophy

> *Clarity over Complexity. Momentum over Stagnation.*

Our engineering culture is built on a set of core principles designed to minimize friction, maximize predictability, and keep the team moving forward. Whether writing code, designing architecture, or planning a roadmap, we adhere to the following pillars:

---

### 1. Keep It Simple
Simplicity is our primary metric for success. We favor straightforward, readable solutions over clever, overly abstracted ones. If a process, architectural pattern, or block of code requires a massive cognitive load to understand, it needs to be simplified.
*   **Adaptability:** This manual is a guide that scales with the project. Apply these rules logically based on the project's scale, always solving for today's known requirements, not tomorrow's hypothetical ones.

### 2. Build Atomically
**1 Issue = 1 Branch = 1 PR.**
We break large problems into small, discrete, and testable tasks. We do not mix unrelated changes into a single workspace. Atomic building prevents review fatigue, drastically reduces merge conflicts, and makes rollbacks safe and targeted. A Pull Request should do exactly one thing and do it perfectly.

### 3. The Pipeline is the Gatekeeper
Human error is inevitable; automated systems are relentless. No code reaches the `main` branch unless the automated checks (linting, type checking, security scanning, and testing) are completely green (✅). We trust automation to enforce formatting and stability so human reviewers can focus their energy on high-level business logic and architecture.

### 4. Leverage Automation & AI
We aggressively eliminate toil. If a machine can do it, a human shouldn't. 
*   We rely on native GitHub automation (Rulesets, Dependabot, Secret Scanning) to enforce compliance. 
*   We embrace AI-assisted workflows (e.g., generating structural UI views, boilerplate code, or test scaffolding) to accelerate the translation of ideas into tangible assets. 

### 5. Continuous Momentum (Just-In-Time)
We prioritize delivering working software iteratively. We avoid "Analysis Paralysis" by practicing **Just-In-Time (JIT) Engineering**: we only design the technical architecture for the module we are building *today*. By defining clear "Definitions of Done" and strictly following Execution Orders, we ensure the project never stagnates.

### 6. Collective Ownership
Code is a team effort. Every contribution requires at least one formal peer approval before merging. Reviews are not about criticism; they are a mechanism for catching blind spots, sharing domain knowledge, and ensuring that any developer can step into any part of the codebase with confidence.

### 7. Documentation as a First-Class Citizen
Code tells you *how* the system works; documentation tells you *why* it was built that way. We treat our documentation (PRDs, RFDs, ADRs) with the same discipline as our source code. **"What's not on paper didn't exist."** If a change isn't reflected in the documentation, the task is not "Done."

### 8. Blameless Culture
Mistakes are an inevitable part of building complex systems. We are not interested in identifying *who* made an error; we are interested in identifying *how* the system allowed the error to occur. 
*   **The Mindset:** If a developer makes a mistake, it is a failure of our documentation, our tooling, or our automated checks. 
*   **The Action:** We focus on mitigation and prevention. Every mistake is an opportunity to improve our "insurance" layers to ensure that the same error can never happen again.
