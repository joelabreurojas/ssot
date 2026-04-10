# Security Standards & DevSecOps

Security is not a feature; it is a fundamental requirement. We operate under a **"Shift-Left"** philosophy, meaning security checks and reviews happen as early in the development lifecycle as possible. 

The following standards must be adhered to across all repositories, from initial prototypes to enterprise production systems.

---

### 1. The Principle of Least Privilege (PoLP)
Every user, service, and infrastructure component must be granted only the minimum permissions necessary to perform its intended function.

*   **Databases:** Application services must connect to the database using roles restricted to specific tables (e.g., `app_read_write`), never as the root `admin` or `postgres` user.
*   **Cloud Resources:** IAM (Identity and Access Management) roles must explicitly define allowed actions (e.g., `s3:PutObject` on a specific bucket, not `s3:*` globally).
*   **Team Access:** Developers are granted access to production environments only when actively debugging an incident, and access is revoked immediately afterward.

---

### 2. Secrets Management & Credential Hygiene
**Rule #1 of Development: NEVER commit secrets, API keys, passwords, or certificates to version control.**

*   **Local Development:** Use `.env` files. Ensure `.env` is explicitly listed in your `.gitignore`.
*   **Secret Scanning:** We leverage GitHub Advanced Security's **Secret Scanning** to automatically block commits that contain known credential patterns (e.g., AWS keys, Stripe tokens) from entering the repository.
*   **Production Injection:** Secrets must be injected into the application environment at runtime using a secure vault (e.g., AWS Secrets Manager, HashiCorp Vault, GitHub Actions Secrets).
*   **OIDC (OpenID Connect):** For cloud deployments (e.g., deploying from GitHub Actions to AWS/Azure), we use OIDC trust relationships instead of long-lived, static access keys. This ensures temporary, scope-limited credentials are generated only when the pipeline runs.

---

### 3. Application Security (OWASP Top 10)
All code must be written with an awareness of the most critical web application security risks (OWASP).

*   **Injection (SQLi/NoSQLi):** Never concatenate user input directly into database queries. Always use parameterized queries or a trusted ORM/Query Builder.
*   **Cross-Site Scripting (XSS):** All user-provided input must be sanitized and escaped before being rendered in a browser (e.g., using React/Vue's built-in escaping or an HTML sanitizer).
*   **Authentication & Session Management:** 
    *   Passwords must be hashed using strong, salted algorithms (e.g., Argon2, bcrypt).
    *   Session tokens (JWTs or cookies) must have short expiration times, be marked `HttpOnly` and `Secure`, and support immediate revocation (e.g., via a Redis blocklist).
*   **Cross-Site Request Forgery (CSRF):** State-changing endpoints (POST/PUT/DELETE) must require a CSRF token if relying on cookie-based authentication.

---

### 4. Dependency Auditing & Supply Chain Security
Modern applications rely heavily on open-source libraries. An attacker doesn't need to hack your code if they can hack your dependencies.

*   **Dependabot:** We use automated dependency management (e.g., GitHub Dependabot or Renovate). It continuously scans our manifest files (`package.json`, `requirements.txt`, `Cargo.toml`) for known vulnerabilities and automatically opens Pull Requests to update them.
*   **Security Advisories:** Maintainers must subscribe to and monitor security advisories for the core frameworks we use (e.g., Django, Express, React).
*   **Code Scanning (SAST):** We utilize automated Static Application Security Testing (e.g., CodeQL) within our CI pipeline to detect common vulnerabilities in our own code before it merges into `main`.

---

### 5. Contributor Trust & Identity
To ensure the integrity of the commit history, we require strong identity verification for all code authors.

*   **GPG/SSH Commit Signatures:** All contributors are strongly encouraged (and in enterprise repositories, required) to cryptographically sign their Git commits using a GPG key or SSH signature. This proves that the commit actually came from the claimed author.
*   **Organization Security:** Two-Factor Authentication (2FA) is mandatory for all members of the GitHub Organization.
