# LBRS Desktop — Administrative Console

The Desktop client is the primary interface for Municipality Administrators and Registry Operators to manage local business registrations.

## 🏗️ How it's shaping up:
*   **Modern Web UI**: Built with React/Next.js for a fast, responsive experience. We utilize a highly modular component architecture where every UI element is reusable across different Palika dashboards.
*   **Secondary Topbar Pattern**: Implementing a standardized navigation system where sub-page settings (like IAM, Classification, Members) are managed via a tabbed secondary bar instead of complex internal component states.
*   **Shared Design System**: Enforcing a premium visual aesthetic with dark mode support, glassmorphism elements, and smooth micro-animations to ensure a professional government-grade experience.

## 🌟 Key Features:
*   **Complex Form Handling**: Multi-step registration forms with real-time field validation, Nepali Unicode support, and instant document upload integration.
*   **Administrative Overviews**: High-level data visualization for Palika administrators, showing registration trends, upcoming renewals, and revenue summaries.
*   **Permission-Based UI**: The interface dynamically hides or shows components based on the user's RBAC role (e.g., Operators cannot see the "Classification Policy" settings).

## 🚀 Current Focus:
Refining Legal Dossier registration and migrating localized IAM components to a route-based directory structure with the Secondary Topbar.

---

## 📈 Feature & Progress Log
| Date | Milestone | Status |
| :--- | :--- | :--- |
| 2026-04-10 | Base Administrative Dashboard UI finalized. | ✅ COMPLETED |
| 2026-04-18 | Secondary Topbar navigation pattern implemented. | ✅ COMPLETED |
| 2026-04-25 | Dynamic RBAC UI visibility logic integrated. | ✅ COMPLETED |
| 2026-04-29 | Classification Policy settings centralized. | ✅ COMPLETED |
| 2026-05-01 | Legal Dossier registration refactoring initiated. | ⏳ IN PROGRESS |
