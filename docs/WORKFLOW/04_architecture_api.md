# Architecture & API Standards

APIs and architectural structures are the formal contracts of a system. To ensure consistency and resilience, we design our systems to be predictable, visually documented, and capable of graceful degradation under stress.

---

### 1. Architectural Visualization & Boundaries
We utilize **Mermaid.js** and the **C4 Model** to ensure the system is comprehensible. Beyond structure, we must define the "Rules of Engagement" for components:

*   **Dependency Boundaries:** Every RFD must explicitly define "Hard Boundaries." Identify which modules are permitted to communicate and, crucially, which imports are strictly prohibited to prevent circular dependencies and "spaghetti" coupling.
*   **State Management:** Systems should be designed as **Stateless** by default. Any persistence of state (session, cache, or permanent storage) must be explicitly delegated to a defined storage layer and documented in the Data Model.
*   **Visualization Levels:** 
    *   *Level 1 (Context):* System interactions with users/external entities.
    *   *Level 2 (Containers):* High-level technical blocks (Web, API, DB).
    *   *Level 3 (Components):* Internal logic flow (Services, Repositories).

    *Rule:* Never try to put all three levels into a single diagram. If a Mermaid diagram requires scrolling to understand, it is too complex and must be broken down.

---

### 2. API Design Principles (REST & GraphQL)

#### For RESTful APIs:
*   **Nouns, Not Verbs:** URLs must represent resources (nouns), not actions. 
    *   *Bad:* `POST /createNewUser`
    *   *Good:* `POST /users`
*   **Pluralization:** Keep resource names plural for consistency (e.g., `/users/123`, not `/user/123`).
*   **Standard HTTP Methods:** 
    *   `GET` (Read), `POST` (Create), `PUT` (Replace), `PATCH` (Update partial), `DELETE` (Remove).
*   **Standard Status Codes:**
    *   `200 OK`, `201 Created`, `204 No Content`.
    *   `400 Bad Request`, `401 Unauthorized`, `403 Forbidden`, `404 Not Found`.
    *   `500 Internal Server Error` (These should trigger immediate alerts).

#### For GraphQL APIs:
*   **Mutations as Verbs:** Name mutations exactly for what they do (e.g., `UpdateUserEmail`, `PublishPost`).
*   **Avoid Deep Nesting:** Protect the database from exponential query complexity by limiting query depth.

---

### 3. Versioning
All public or client-facing APIs **must be versioned** from Day 1. You will always need to make a breaking change eventually.
*   **Standard:** Use URI versioning (e.g., `https://api.domain.com/v1/resource`) or Header versioning (`Accept: application/vnd.domain.v1+json`).
*   **Breaking Changes:** Removing a field, changing a data type, or adding a mandatory request parameter requires a new version (e.g., `v2`).
*   **Non-Breaking Changes:** Adding optional parameters or adding new response fields can be done in place.

---

### 4. Idempotency & Reliability
Network requests fail. Clients will retry them. Our APIs must be designed to handle retries safely without causing duplicate actions (like charging a credit card twice).

*   **Idempotent Methods:** `GET`, `PUT`, `PATCH`, and `DELETE` must be idempotent by definition (calling them 10 times has the same effect as calling them 1 time).
*   **Idempotency Keys:** For critical `POST` mutations (e.g., payments, resource provisioning), clients should provide an `Idempotency-Key` header. The backend must store this key and return the cached successful response if the same key is used again within a given timeframe.

---

### 5. Reliability Engineering (The Resilience Standard)
Architecture must actively anticipate failure. All system boundaries must implement the following resilience patterns:

*   **Strict Timeouts:** Every external network call (Database, 3rd party API, or LLM) must have a defined timeout. No request is permitted to hang indefinitely.
*   **Retries with Backoff:** Implement retry logic for transient failures using **Exponential Backoff and Jitter** to prevent overwhelming a recovering service.
*   **Circuit Breakers:** For high-volume dependencies, implement circuit breakers to stop traffic to a failing service, allowing it time to recover while providing immediate error responses.
*   **Graceful Degradation (Fallbacks):** Every RFD must define a "Plan B" for critical path failures. If a non-essential service (e.g., an AI recommendation engine) fails, the system must degrade to a functional fallback (e.g., a static chronological list) rather than crashing the entire view.

---

### 6. Tool & Automation Contracts
Contracts apply to the entire lifecycle, not just public APIs:
*   **Automation Schemas:** Internal tools, CI/CD scripts, and background workers must define strict Input/Output schemas (arguments, environment variables, and exit codes). 
*   **Boundary Control:** Treat internal automation with the same rigor as an API. Scripts must handle invalid inputs predictably and provide structured logs for failure analysis.

---

### 7. Graceful Degradation
Architecture must define "Plan B" for when primary services fail.
*   **Fallback Logic:** If a high-latency or non-critical service (like an AI generator or recommendation engine) fails, the interface must return a cached result, a simplified default, or a meaningful error message.
*   **Friction Awareness:** Identify points where system latency will impact the user and design "Thinking/Generating" states into the contract.

---

### 8. Standardized Error Handling
Clients should not have to guess how to parse an error. We enforce a consistent, system-wide error envelope (e.g., RFC 7807 Problem Details).

**Required Error Structure:**
```json
{
  "error_code": "RESOURCE_NOT_FOUND",
  "message": "A human-readable explanation.",
  "details": {
    "field": "Specific validation failure reasons, if applicable."
  },
  "trace_id": "uuid-for-logging-correlation"
}
```
*Rule:* Never expose internal stack traces or database errors to the client.
