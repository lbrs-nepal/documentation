# LBRS Auth — Identity & Access Management (IAM)

The Auth module provides a centralized, secure identity provider for all LBRS users, ranging from government administrators to business owners.

## 🏗️ How it's shaping up:
*   **Organization-Centric IAM**: Every user is strictly scoped within an Organization (Municipality or Business). This allows for "Zero-Leak" multi-tenant security where a Palika operator can only see data belonging to their specific local government.
*   **RBAC (Role Based Access Control)**: A granular hierarchy of permissions enforced at the Fiber middleware level.
*   **Session Management**: Implementation of secure JWT-based authentication using **Asymmetric RS256 signing**. Supports short-lived access tokens (15 mins) and long-lived refresh tokens (7 days) with automated rotation.

## 🌟 Key Features:

### 1. RBAC Role Definitions
| Role | Permissions | Use Case |
| :--- | :--- | :--- |
| **SuperAdmin** | Full system access, Palika creation, Global settings. | LBRS Central Team. |
| **PalikaAdmin**| Manage Palika members, classification policies, and local audits. | Municipality IT Head. |
| **Operator** | Business registration, renewal, and document uploads. | Registry Front-Desk. |
| **Reviewer** | Approve/Reject registrations, verify legal dossiers. | Legal/Department Head. |
| **Viewer** | Read-only access to registries and reports. | Internal Auditors. |

### 2. Security Protocols
*   **Argon2id Hashing**: Utilizing the Argon2id algorithm (Time: 3, Memory: 64MB, Threads: 4) for maximum resistance against ASIC/GPU attacks.
*   **Brute-Force Protection**: Rate-limiting on login endpoints and automatic account lockout after 5 failed attempts.
*   **Audit Logging**: Every sensitive action (password changes, role updates, login attempts) is recorded with IP address and User-Agent fingerprinting.

### 3. JWT Payload Structure
The system uses a standardized JWT structure to ensure cross-service compatibility:
```json
{
  "sub": "user_uuid",
  "org_id": "a1b2c3-45871",
  "role": "PalikaAdmin",
  "exp": 1714550000,
  "iat": 1714540000
}
```

## 🛠️ Developer Implementation (Go Example)
Developers can protect any route by simply wrapping it with the Auth middleware:

```go
// Example: Protecting a Registry Route
api := app.Group("/v1/registry", auth.Guard())

api.Post("/register", auth.RequireRole("Operator"), handler.RegisterBusiness)
api.Get("/audit-log", auth.RequireRole("PalikaAdmin"), handler.GetAuditLogs)
```

## 🚀 Current Focus:
Standardizing IAM Dashboard architecture to ensure UI parity between Console and Dashboard and implementing the "Secondary Topbar" navigation pattern.

---

## 📈 Feature & Progress Log
| Date | Milestone | Status |
| :--- | :--- | :--- |
| 2026-03-10 | Core JWT issuance and validation logic completed. | ✅ COMPLETED |
| 2026-03-25 | Multi-tenant organization scoping implemented. | ✅ COMPLETED |
| 2026-04-15 | Argon2id password hashing integration. | ✅ COMPLETED |
| 2026-04-28 | RBAC Middleware for Fiber v2 finalized. | ✅ COMPLETED |
| 2026-05-01 | IAM Dashboard UI refactoring initiated. | ⏳ IN PROGRESS |
