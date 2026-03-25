# ADR [Number]: [Short, Descriptive Title]

<!-- 
  Instructions for the Author:
  1. Copy this template to docs/ADR/.
  2. Name the file sequentially (e.g., 004_use_redis_for_sessions.md).
  3. Fill out the sections below clearly and concisely.
  4. Open a Pull Request for the team to review the decision.
-->

*   **Status:** [Proposed | Accepted | Superseded by ADR-XXX]
*   **Date:** [YYYY-MM-DD]
*   **Author(s):** [Name or GitHub Handle]

---

## 1. Context and Problem Statement

<!-- 
  Describe the specific technical problem, requirement, or constraint that forced this decision. 
  What is the issue we're trying to solve? Why can't we just stick to the original RFD?
  
  Example: "Our current SQLite database is experiencing locking issues under high concurrent load during peak hours, causing 500 errors for users trying to check out."
-->
[Insert context here]

---

## 2. Considered Options

<!-- 
  List the different technologies, patterns, or approaches that were considered to solve the problem. 
  Always include the "Do Nothing" option if applicable.
-->
*   **Option 1:** [e.g., Migrate to PostgreSQL]
*   **Option 2:**[e.g., Implement a queuing system like Celery to serialize database writes]
*   **Option 3:**[e.g., Keep SQLite but use the Write-Ahead Logging (WAL) mode]

---

## 3. Decision Outcome

<!-- 
  State the chosen option clearly and affirmatively. This is the most important section.
-->
**Chosen Option:** [Option X]

### Rationale

<!-- 
  Justify the choice. Why is this better than the alternatives? 
  Reference project principles (e.g., "Keep It Simple"), budget constraints, team skills, or performance benchmarks.
  
  Example: "While migrating to PostgreSQL (Option 1) is the most robust long-term solution, it introduces significant operational complexity (managing a new DB server) that violates our MVP timeline constraints. Enabling WAL mode (Option 3) solves the immediate concurrency issue with zero infrastructure changes."
-->
[Insert rationale here]

---

## 4. Consequences

<!-- 
  What happens now that we've made this decision? Be honest about the trade-offs.
-->

### Positive Consequences
<!-- What gets better? -->
*   [e.g., Immediate resolution of concurrent write errors without infrastructure changes.]
*   [e.g., Zero cost increase.]

### Negative Consequences
<!-- What gets harder? What tech debt did we just accept? -->
*[e.g., SQLite is still not suitable for horizontal scaling if we add a second API server in the future.]

### Neutral / Implementation Consequences
<!-- What needs to happen in the code? -->
*[e.g., We need to update `src/core/database.py` to append `?journal_mode=wal` to the connection string.]
