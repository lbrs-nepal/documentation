# LBRS Desktop — Administrative Console & Dashboard

The **Desktop Client** is the premium administrative interface for the LBRS ecosystem. Built with Next.js 14+, it provides Municipality Administrators and Registry Operators with a real-time, glassmorphic dashboard to manage the business lifecycle.

---

## 📂 Directory & Setup
The frontend is built for extreme modularity and architectural clarity.

- **`/src/app`**: The Next.js App Router structure, divided into:
  - `(public)`: Guest-facing routes (Login, Console-Register).
  - `(protected)`: Restricted routes for authorized personnel (Dashboard, Settings).
- **`/src/lib`**: The "Frontend Logic" hub:
  - `auth`: Identity and session management.
  - `routes`: Action-based service integrators.
  - `themes`: Centralized design system (tokens, glassmorphism, animations).
- **`/src/components`**: A library of reusable UI atoms, molecules, and organisms.

---

## ⚙️ How it Works
1.  **State Management**: Uses React state and Next.js navigation hooks to provide a fast, "Single Page App" feel with the power of Server-Side Rendering (SSR).
2.  **Service Integration**: Communicates with the Auth, Core, and Media services via a standardized fetcher pattern, injecting JWT tokens automatically for protected routes.
3.  **Real-Time Feedback**: Includes live elements like monotonic clocks and system status indicators to provide a sense of platform vitality.
4.  **RBAC Visibility**: Dynamically renders navigation and action buttons based on the user's role extracted from the session JWT.

---

## 🏛️ Oracle Governance
As the user-facing layer, the Desktop module is the final link in the Oracle chain:

- **Audit Tagging**: The `@LBRS-Mapping-Audit` tag is applied to critical pages and route handlers.
- **Traceability**: Every data field in the registration form is linked back to an Oracle mapping (e.g., `company.details`) to ensure the UI matches the database schema.
- **Protocol Adherence**: The `Protocol: [oracle/docs/README.md]` header ensures that frontend developers follow the same architectural rules as backend engineers.

---
© 2026 LBRS Nepal. All rights reserved.
