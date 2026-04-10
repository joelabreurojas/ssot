# Testing Standards & Quality Assurance

Testing is not an afterthought; it is a core component of the development process. We do not write code and *then* figure out how to test it. We write code *to be testable*. 

Automated tests are the safety net that allows us to move fast, refactor with confidence, and maintain our **Blameless Culture**.

---

### 1. The Test Pyramid
We follow the standard Test Pyramid to ensure our suite runs quickly and provides the right level of feedback. 

*   **Unit Tests (The Base - 70%):** Fast, highly focused tests. They verify a single function, class, or method in isolation. 
    *   *Rule:* All external dependencies (databases, APIs, file systems) **must** be mocked or stubbed.
*   **Integration Tests (The Middle - 20%):** Slower tests that verify the "wiring" between components. 
    *   *Rule:* These tests interact with real (or test-instance) databases, caches, and internal services to ensure the data flows correctly across boundaries.
*   **End-to-End / E2E Tests (The Peak - 10%):** Slow, comprehensive tests that simulate a real user interacting with the fully deployed system (UI -> API -> DB).
    *   *Rule:* Focus E2E tests only on the "Critical Path" (e.g., Registration, Login, Checkout). Do not use E2E to test edge-case logic that can be covered by a Unit Test.

---

### 2. Test-Driven Development (TDD)
While strict TDD (writing the test *before* the code) is not strictly mandatory for all tasks, we heavily encourage a **Test-Informed** workflow.

*   **The Mindset:** Before writing a function, ask: *"How will I assert that this works?"*
*   **Bug Fixes:** When fixing a `type:bug` issue, you **must** write a failing test that reproduces the bug *before* you write the fix. The fix is complete when the test turns green. This prevents regressions.

---

### 3. Coverage Targets & Metrics
We measure Code Coverage (the percentage of our codebase executed by tests), but we treat it as a tool for discovery, not a vanity metric.

*   **Target Coverage:** We aim for **> 80% coverage on core business logic** (The Application/Domain layer). 
*   **The Pragmatic Exception:** We do not mandate 100% coverage. Testing every getter/setter or UI layout pixel often leads to brittle tests that break on minor refactors. Focus tests on the complex logic defined in the [RFD (04_logic.md)](../EXAMPLES/docs/RFD/04_logic.md).
*   **CI Enforcement:** The CI pipeline will automatically fail if a Pull Request significantly drops the overall project coverage percentage.

---

### 4. Testing Conventions & Best Practices

To ensure our test suite remains readable and maintainable:

*   **Arrange, Act, Assert (AAA):** Every test must clearly visually separate the setup (Arrange), the execution (Act), and the verification (Assert).
*   **Deterministic Execution:** Tests must pass or fail consistently. If a test is "flaky" (fails randomly due to network latency, timing, or shared state), it must be fixed or deleted immediately. Flaky tests destroy trust in the CI pipeline.
*   **Isolated State:** Tests must never depend on the execution order or the data left behind by a previous test. Every test must set up its own state and clean up after itself (e.g., using transaction rollbacks or database truncation fixtures).
*   **Clear Naming:** Test names must describe the behavior being verified, not just the function name.
    *   *Bad:* `test_login()`
    *   *Good:* `test_login_fails_with_invalid_password_and_returns_401()`

---

### 5. Performance & Load Testing (Optional Phase)
For enterprise systems or modules expecting high traffic, the RFD may specify performance targets.
*   **The Tool:** We use tools like K6, Locust, or JMeter.
*   **The Goal:** To establish a baseline (e.g., "The API handles 500 req/sec with < 200ms latency") and ensure subsequent architectural changes do not degrade performance.
