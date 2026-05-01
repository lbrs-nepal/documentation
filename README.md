# LBRS — Local Business Registry System (Nepal)

Welcome to the central documentation repository for the **LBRS Ecosystem**. LBRS is a next-generation, high-availability platform designed to digitize local government business registration, fiscal tracking, and media asset management across Nepal.

---

## 🏛️ Project Pillars

The ecosystem is built on **Four Core Pillars** that ensure scalability, security, and architectural integrity:

1.  **The Oracle (Architectural Brain)**: The Single Source of Truth (SSoT) for the entire system.
2.  **Microservice Architecture**: Specialized nodes (Auth, Core, Media, Location) running on a unified port-based hierarchy.
3.  **Data Governance**: Centralized PostgreSQL schemas with strict audit trails.
4.  **Premium UX**: A glassmorphic, real-time administrative console built with Next.js.

---

## 🌐 The LBRS Project Ecosystem

The system is partitioned into specialized modules, each governed by the **Oracle Registry**.

| Module | Purpose | Status | Documentation |
| :--- | :--- | :--- | :--- |
| **`oracle`** | **Single Source of Truth & Governance** | ✅ **Active** | [**Governance Guide**](./oracle/README.md) |
| **`auth`** | Global IAM, RBAC & Multi-Table Security | ✅ **Active** | [**Auth Docs**](./auth/README.md) |
| **`core`** | Business Logic, Fiscal Engine & Approvals | ✅ **Active** | [**Core Docs**](./core/README.md) |
| **`db`** | Centralized Schema Management & Migrations | ✅ **Active** | [**Database Docs**](./db/README.md) |
| **`location`**| Geographical Governance & Palika Mapping | ✅ **Active** | [**Location Docs**](./location/README.md) |
| **`media`** | Intelligent Asset Processing & Delivery | ✅ **Active** | [**Media Docs**](./media/README.md) |
| **`desktop`** | Admin Console & Real-time Dashboard | ✅ **Active** | [**Desktop Docs**](./desktop/README.md) |

---

## 🏗️ Architectural Governance

LBRS utilizes the **"Living Architecture"** protocol. Every critical file in the system is linked to the Oracle registry via the `@LBRS-Mapping-Audit` protocol.

- **Infrastructure Contract**: Managed via `oracle/config/services.yml`.
- **Behavioral Mappings**: Managed via `oracle/schemas/`.
- **Integrity Enforcement**: Any change to code MUST be mirrored in Oracle.

---

## 🚀 Quick Links

- **[Architecture Blueprint](./oracle/README.md)**: Deep dive into the system's brain.
- **[Deployment Registry](../oracle/config/services.yml)**: Official port and URL mappings.
- **[Schema Index](../db/schema/schemas/schemas.sql)**: Database definitions.

---
© 2026 LBRS Nepal. All rights reserved.
