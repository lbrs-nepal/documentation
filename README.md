# LBRS — Local Business Registry System (Nepal)

Welcome to the central documentation repository for the **LBRS Ecosystem**. LBRS is a next-generation, high-availability platform designed to digitize local government business registration, fiscal tracking, and media asset management across Nepal.

---

## 🌟 Project Vision & Public Transparency

LBRS is built with **Public Transparency** at its core. By open-sourcing our architectural governance (The Oracle), we aim to establish a standard for government-grade software that is verifiable, secure, and resilient. 

### Why we are Open Source:
- **Architectural Verifiability**: Citizens and stakeholders can verify the logic governing their data.
- **Developer Empowerment**: We invite the developer community to study our "Living Architecture" and contribute to the modernization of Nepal's digital infrastructure.
- **Security through Clarity**: We believe that clear, documented architecture is the best defense against systemic vulnerability.

---


## 🏛️ Project Pillars

The ecosystem is built on **Four Core Pillars** that ensure scalability, security, and architectural integrity:

1.  **The Oracle (Architectural Brain)**: The Single Source of Truth (SSoT) for the entire system.
2.  **Microservice Architecture**: Specialized nodes (Auth, Core, Media, Location) running on a unified port-based hierarchy.
3.  **Data Governance**: Centralized PostgreSQL schemas with strict audit trails.
4.  **Premium UX**: A glassmorphic, real-time administrative console built with Next.js.

---

## 🛠️ Technical Stack (Global Overview)

LBRS utilizes a modern, performance-oriented stack designed for low latency and high consistency:

- **Backend Logic**: Golang (Fiber/Standard Library) for ultra-fast, concurrent microservices.
- **Frontend Layer**: Next.js 14+ with TailwindCSS and Vanilla CSS for a premium glassmorphic experience.
- **Data Persistence**: PostgreSQL (via Supabase) with the `pgxpool` transaction manager.
- **Object Storage**: MinIO (S3-compatible) for distributed asset management.
- **Media Engine**: FFmpeg & Libvips for real-time asset transformation.

---

## 🔒 Core Security Principles

Security is not an afterthought; it is baked into every layer of the LBRS infrastructure:

1.  **Isolated Credentials**: Passwords and salts are stored in a physically separate table (`member.credentials`) from identity data.
2.  **JWT-Based RBAC**: Role-Based Access Control is enforced via stateless JWT tokens with cross-origin validation.
3.  **Content Verification**: Every media upload is verified via magic number analysis and antivirus scanning.
4.  **Auditability**: Every write operation is logged with a trace back to the initiating member.

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

## 🗺️ How to Explore this Repository

If you are a first-time visitor or a potential contributor, we recommend the following path:

1.  **Understand the Core**: Start with the [**Oracle Governance Guide**](./oracle/README.md). This explains how we prevent architectural drift.
2.  **Explore the Modules**: Dive into [**Auth**](./auth/README.md) for security patterns or [**Media**](./media/README.md) for asset processing logic.
3.  **Inspect the Schemas**: Look at our [**Database Schema**](../db/schema/schemas/schemas.sql) to see how we handle hierarchical location data.
4.  **View the Interface**: See the [**Desktop Docs**](./desktop/README.md) for a look at our Next.js + Glassmorphic design system.

---

## ⚖️ Compliance & Governance Standards

LBRS is designed to exceed the standard requirements for municipal digital systems:

- **Unicode Standard**: Full support for Devanagari script across all document generation and search modules.
- **Fiscal Consistency**: Native support for the Nepali Bikram Sambat (BS) fiscal calendar.
- **Minimization Principle**: We collect only the data necessary for business registration and municipal compliance.
- **Audit Trails**: All administrative actions are traceable to a specific authenticated session.

---

© 2026 LBRS Nepal. All rights reserved.

