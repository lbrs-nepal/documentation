# LBRS Media — Global Asset Infrastructure

The **Media Service** is the high-performance asset management hub for the LBRS ecosystem. It manages the ingestion, processing, and secure delivery of images, videos, and legal documents.

---

## 📂 Directory & Setup
The service follows a **Resource-Oriented Architecture** designed for high throughput and security.

- **`/v1/manager`**: Handles asset ingestion, validation, and metadata persistence in PostgreSQL.
- **`/v1/guard`**: Implements specialized JWT middleware for cross-origin media access control.
- **`/v1/gateway`**: The streaming interface that delivers content from MinIO (S3) to the client.
- **`/server`**: The entry point that orchestrates the Fiber application and MinIO connections.
- **`@LBRS-Mapping-Audit`**: Ensures every asset-related change is architecturally tracked.

---

## ⚙️ How it Works
1.  **Secure Ingestion**: Validates file signatures (Magic Numbers) and strips sensitive EXIF metadata before storage.
2.  **Hybrid Metadata**: Stores file details (size, mime-type, org_id) in PostgreSQL to allow for fast searching without querying the object store.
3.  **Monolithic Gateway**: A single delivery point (`media.npframe.com`) that dynamically determines if a file is Public or Protected based on the database state.
4.  **MinIO Integration**: Interfaces with S3-compatible storage using a strictly namespaced path convention: `{organization_id}/{media_type}/{id}`.
5.  **Soft Deletion**: Implements a 45-day retention window where files are marked as `deleted` in metadata before physical removal.

---

## 🏛️ Oracle Governance
The Media service is governed by the **Asset Mappings** in Oracle:

- **Metadata Sync**: Linked to the `media.assets` table via `oracle/schemas/media/assets/assets.yml`.
- **Infrastructure Link**: The production and development URLs are strictly defined in `oracle/config/services.yml`.
- **Atomic Operations**: Any change to how assets are classified or stored must be updated in the Oracle mapping to maintain full-stack traceability.

---
© 2026 LBRS Nepal. All rights reserved.
