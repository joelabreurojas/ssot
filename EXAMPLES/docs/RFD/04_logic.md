# Logic & Services (The Application Core)

This document defines the pure business logic, the domain rules, and the service orchestrators that make up the heart of the application. This layer must remain entirely agnostic to the external interfaces (HTTP, WebSockets) and the specific database implementation (SQL, NoSQL).

---

## 1. Core Domain Services
<!-- 
    Identify the primary "Workers" or "Orchestrators" in your system.
    What are the specialized services that handle specific business domains?
    (e.g., UserService, PaymentProcessor, InventoryManager, RAGOrchestrator).
-->

### Service: `[ServiceName, e.g., OrderFulfillmentService]`
*   **Responsibility:**[What is the single, focused job of this service? e.g., "Manages the lifecycle of an order from payment confirmation to shipping dispatch."]
*   **Key Dependencies:**[What other core services or repositories does this service need to do its job? e.g., PaymentGatewayPort, InventoryRepository, NotificationService.]
*   **Primary Workflows / Use Cases:**
    <!-- Describe the high-level logic for the most important actions this service performs. -->
    1.  `[Action Name, e.g., ProcessNewOrder(order_details)]`:
        *   *Step 1:* Validate payment status via `PaymentGateway`.
        *   *Step 2:* Reserve stock via `InventoryManager`. If stock is unavailable, raise `InsufficientStockError`.
        *   *Step 3:* Persist the new order state via `OrderRepository`.
        *   *Step 4:* Dispatch 'OrderCreated' event via `NotificationService`.

### Service: `[ServiceName]`
*   **Responsibility:**[Description]
*   **Key Dependencies:** [List dependencies]
*   **Primary Workflows / Use Cases:**
    1.  `[Action Name]`:
        *   *Step 1:* [Logic step]
        *   *Step 2:* [Logic step]

---

## 2. Business Rules & Validation
<!-- 
    What are the absolute, non-negotiable rules of your business domain? 
    These rules must be enforced by the services before any data is saved or action is taken.
-->

*   **[Rule Name, e.g., User Age Restriction]:**[e.g., "A user must be 18 years or older to register for a merchant account. This is calculated based on their provided Date of Birth during registration."]
*   **[Rule Name, e.g., Subscription Limits]:**[e.g., "A 'Basic' tier user can only create a maximum of 3 active projects. The `ProjectService` must verify the current count against the user's tier before allowing a new creation."]
*   **[Rule Name, e.g., Password Complexity]:**[e.g., "Passwords must be at least 12 characters, containing at least one symbol and one number. Enforced at the schema validation level before hitting the `AuthService`."]

---

## 3. Background Jobs & Asynchronous Logic
<!-- 
    Not all logic happens instantly during a user request. 
    Define the processes that happen in the background (e.g., via Celery, Cron jobs, or Event queues).
-->

| Job Name / Task | Trigger | Responsibility | Frequency / SLA |
| :--- | :--- | :--- | :--- |
| **[e.g., Generate Daily Reports]** | Scheduled (Cron) | Aggregates daily sales data and emails a PDF to admins. | Runs daily at 02:00 UTC. |
| **[e.g., Process Video Upload]** | Event-Driven (Queue) | Takes a raw uploaded video, compresses it, and generates thumbnails. | Triggered immediately upon upload; must complete within 5 minutes. |
| **[e.g., Cleanup Expired Sessions]**| Scheduled (Cron) | Deletes session tokens older than 30 days from the database to reclaim space. | Runs weekly on Sunday. |

---

## 4. Error Handling & State Management
<!-- 
    How does the core logic communicate failures? 
    Do you use custom Domain Exceptions? Do you return standard Error/Result objects (like in Rust/Go)?
-->
*   **Exception Strategy:**[e.g., "All business rule violations raise specific sub-classes of `AppException` (e.g., `InsufficientFundsError`, `UserNotFoundError`). These are caught at the interface layer and translated into standard HTTP/GraphQL errors."]
*   **State Transitions:**[If your entities have complex lifecycles, define them here. e.g., "An Invoice moves from `DRAFT` -> `ISSUED` -> `PAID` or `VOIDED`. An Invoice cannot move directly from `DRAFT` to `PAID`."]
