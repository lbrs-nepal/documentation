# LBRS Database — Schema & Data Governance

The Database repository is the single source of truth for all LBRS SQL schemas, migrations, and shared PostgreSQL functions.

## 🏗️ How it's shaping up:
*   **Modular Schema Isolation**: Every project domain is isolated into its own PostgreSQL schema (`media`, `company`, `location`, `member`). This prevents table-name collisions and allows for granular backup and permission strategies.
*   **Global Functions Library**: We maintain a `public` functions library for cross-module utilities like `update_updated_at_column()` and `set_asset_deleted_at()`, ensuring logic consistency across the entire database.
*   **Migration-First Workflow**: Utilizing a strictly sequential migration pattern to ensure that the production database is always an exact mirror of the local development environment.

## 🌟 Key Features:
*   **Advanced JSONB Usage**: Leveraging PostgreSQL JSONB for "Schema-less" metadata (like media variants and business configuration) without sacrificing indexing speed.
*   **Trigger-Based Automation**: All `updated_at` and `deleted_at` timestamps are managed by database-level triggers, removing the burden from the application code.
*   **Searchable Devanagari**: Specialized indexes for Devanagari script to ensure high-speed fuzzy searching for business and owner names.

## 🚀 Current Focus:
Registering the new `media` schema and implementing retention policy triggers for the 45-day safety window.

---

## 📈 Feature & Progress Log
| Date | Milestone | Status |
| :--- | :--- | :--- |
| 2026-02-15 | Modular schema isolation pattern established. | ✅ COMPLETED |
| 2026-03-01 | Global timestamp management functions implemented. | ✅ COMPLETED |
| 2026-04-10 | Multi-tenant organization scoping triggers finalized. | ✅ COMPLETED |
| 2026-05-01 | `media` schema registration and triggers implemented. | ✅ COMPLETED |
| 2026-05-01 | Migration from raw SQL plans to modular schema files. | ⏳ IN PROGRESS |
