# LBRS Auth — Identity & Access Management (IAM)

The **Auth Service** is the security gateway of the LBRS ecosystem. It handles multi-tenant authentication, role-based access control (RBAC), and session management for all system nodes.

---

## 📂 Directory & Setup
This module follows a strictly decoupled **Handler-Repository** pattern to ensure that business logic and data access are separated.

- **`/v1`**: Contains versioned API logic (Registration, Login, Password Management).
- **`/server`**: The entry point that initializes the Fiber application and registers routes.
- **`/guard`**: JWT middleware and security enforcement logic.
- **`.env.development` / `.env.production`**: Environment-specific configurations (JWT Secrets, DB URLs).

---

## ⚙️ How it Works
1.  **Authentication**: Users provide credentials which are verified against the `member.credentials` table (Argon2id hashing).
2.  **JWT Issuance**: Upon successful login, the service issues a stateless JWT containing the `member_id`, `org_id`, and `role`.
3.  **RBAC Enforcement**: The `auth.Guard()` middleware intercepts every incoming request to other services, verifying the token's validity and the user's permissions.
4.  **Multi-Tenancy**: The `org_id` in the token ensures that users (like Palika operators) are strictly limited to their own data scope.

---

## 🏛️ Oracle Governance
As a critical security node, the Auth service is tightly integrated with the **Oracle Registry**:

- **Governance Header**: Every repository and handler starts with the `@LBRS-Mapping-Audit` tag.
- **Mapping Reference**: Links directly to `oracle/schemas/member/credentials/credentials.yml` and `members.yml`.
- **Mandatory Sync**: Any change to the JWT payload or role hierarchy MUST be mirrored in the Oracle registry first.

---
© 2026 LBRS Nepal. All rights reserved.
