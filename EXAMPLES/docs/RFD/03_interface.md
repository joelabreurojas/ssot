# Interface & API Design

## 1. Interface Strategy & Protocols
<!-- 
    What are the primary methods this system uses to communicate with external clients 
    (web apps, mobile apps, other microservices, or third-party webhooks)?
    Justify the choice of protocols (e.g., REST, GraphQL, gRPC, WebSockets, Server-Sent Events).
-->
*   **Primary Interface Paradigm:** [e.g., RESTful API / GraphQL / gRPC / Server-Driven UI (SDUI)]
    *   *Rationale:*[Why is this paradigm the best fit? (e.g., REST for simplicity and caching; GraphQL for flexible client queries; SDUI for rapid mobile layout updates without app store releases).]
*   **Real-Time / Asynchronous Interfaces:**[e.g., WebSockets / Server-Sent Events (SSE) / Webhooks]
    *   *Rationale:*[What requires real-time data? (e.g., Chat messages, live notifications, processing status updates).]
*   **Internal Service Communication (if applicable):**[e.g., Event Bus (Kafka/RabbitMQ) / gRPC / Direct HTTP]
    *   *Rationale:*[How do microservices or decoupled modules talk to each other?]

---

## 2. Architecture & Routing
<!-- 
    How are requests routed and managed before they hit the core business logic?
    Are we using an API Gateway, a Backend-for-Frontend (BFF), or direct client-to-service communication?
-->
*   **Gateway / Routing Layer:**[e.g., Nginx, AWS API Gateway, Traefik, Custom BFF]
    *   *Purpose:*[e.g., Handles SSL termination, rate limiting, and routes `/api/users` to the User Service.]
*   **Backend-for-Frontend (BFF) Pattern (if applicable):**
    *   *Purpose:*[If using a BFF, explain its role (e.g., Aggregating multiple microservice calls into a single JSON payload for the mobile app, handling session cookies securely).]

---

## 3. Core Data Contracts (The API Schema)
<!-- 
    Define the most critical interactions. You do not need to list every single CRUD endpoint.
    Focus on the complex, high-value contracts.
    
    - For REST: List Endpoints, Methods, and Payload shapes.
    - For GraphQL: Define the primary Queries, Mutations, and core Types.
    - For gRPC: Define the key RPC methods and Protobuf message structures.
    - For SDUI: Define the JSON schema that dictates the UI components.
-->

### Interaction: `[Action Name, e.g., Create Order, Authenticate User, Subscribe to Feed]`
*   **Protocol/Method:**[e.g., `POST /api/v1/orders` | `Mutation: createOrder` | `WebSocket Subscribe`]
*   **Purpose:** [What does this interaction achieve?]
*   **Request Payload (or Query Parameters):**
    ```json
    // Example Payload Shape
    {
      "item_id": "uuid",
      "quantity": "int",
      "discount_code": "string (optional)"
    }
    ```
*   **Response / Expected Behavior:**
    ```json
    // Example Success Response
    {
      "order_id": "uuid",
      "status": "pending",
      "estimated_delivery": "timestamp"
    }
    ```
*   **Failure Modes:**[e.g., 400 Bad Request if quantity <= 0; 404 if item_id invalid; 402 Payment Required.]

*(Repeat block for key interactions)*

---

## 4. Authentication, Authorization & Security
<!-- 
    How is the interface secured at the boundary?
-->
*   **Authentication Mechanism:**[How do we know WHO is making the request? e.g., JWT Bearer Tokens, Session Cookies, API Keys (for server-to-server), OAuth2.]
*   **Authorization Strategy:**[How do we know WHAT they are allowed to do? e.g., Role-Based Access Control (RBAC), Attribute-Based Access Control (ABAC), Scope-based token validation.]
*   **Rate Limiting & Throttling:**[How do we protect the interface from abuse or DDoS? e.g., Token bucket algorithm via Redis, 100 requests/minute per IP, 1000 requests/minute per authenticated user.]
*   **Data Protection (In Transit):**[e.g., TLS 1.3 enforced on all endpoints; Payload encryption for highly sensitive fields.]

---

## 5. Versioning & Evolution Strategy
<!-- 
    How will this interface change over time without breaking existing clients?
-->
*   **Versioning Method:**[e.g., URI Path (`/v1/`), Header-based (`Accept: application/vnd.myapi.v1+json`), or Schema Evolution (GraphQL deprecation directives).]
*   **Deprecation Policy:** [How long are old versions supported before being retired? e.g., 6 months notice with sunset headers.]
