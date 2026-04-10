# Architecture & API Standards

APIs are contracts. Once a contract is published and consumed by clients, it is incredibly expensive to change. Therefore, we design our architecture and interfaces with extreme discipline, predictability, and backwards compatibility in mind.

---

### 1. Architectural Visualization (C4 & Mermaid)
We do not use static image files for architecture diagrams. We use **Mermaid.js** embedded directly in our markdown files (RFDs). To ensure diagrams are comprehensible, we loosely adopt the **C4 Model** approach for visualizing software architecture:

*   **Context (Level 1):** The big picture. Show how the system interacts with users and external systems.
*   **Containers (Level 2):** Zoom in. Show the high-level technical containers (e.g., Web App, Mobile App, API Gateway, Database).
*   **Components (Level 3):** Zoom in further. Show the internal structure of a specific container (e.g., Controllers, Services, Repositories).

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

### 5. Standardized Error Handling
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
