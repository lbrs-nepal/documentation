# LBRS Media Service — Project Status

The Media Service is currently being refactored from an action-oriented legacy system into a high-performance **Resource-Oriented Architecture**.

## 🏗️ How it's shaping up:
*   **Centralized Gateway**: Moving all asset delivery to a unified `gateway` module that handles both public and protected content. This uses a single entry point for all MinIO streaming, injecting security checks dynamically.
*   **Metadata Integration**: Transitioning to a PostgreSQL-backed metadata system to allow for fuzzy searching and better relationship tracking. This eliminates the need for expensive MinIO listing operations.
*   **Async Engine**: Implementing a robust processing engine using Go routines for automatic image optimization (Lanczos3) and video frame extraction (FFmpeg).
*   **Tenant Isolation**: Enforcing a strict `{organization_id}/{media_type}/{id}` path convention to ensure zero cross-tenant data leakage.

## 🌟 Key Features:
*   **Zero-Trust Sanitization**: Server-side Magic Number detection ignoring client-side MIME headers.
*   **45-Day Retention**: Automated "Safety Window" for soft-deletions before permanent physical removal.
*   **Privacy-First**: Automatic EXIF metadata stripping from all uploaded images.
*   **Unified Access**: A single interface for both Public and Protected (JWT-guarded) media.

## 🚀 Current Focus:
Implementing the `v1/manager` repository and the `v1/gateway` handler.

---

## 📈 Feature & Progress Log
| Date | Milestone | Status |
| :--- | :--- | :--- |
| 2026-04-30 | Initial Fragmented Media Service Analysis. | ✅ COMPLETED |
| 2026-05-01 | Architectural Refactor Plan (Resource-Oriented) Approved. | ✅ COMPLETED |
| 2026-05-01 | Database Metadata Schema (`media.assets`) Implemented. | ✅ COMPLETED |
| 2026-05-01 | 45-Day Retention Policy & Triggers Designed. | ✅ COMPLETED |
| 2026-05-02 | (Planned) MinIO/Postgres Connection Module Implementation. | ⏳ IN PROGRESS |
