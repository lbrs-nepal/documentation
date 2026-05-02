# LBRS DB — Data Infrastructure & Governance

The **DB Module** is the foundational layer of the LBRS ecosystem. It manages the physical schemas, connection pooling, and data maintenance scripts for the entire platform.

---

## 📂 Directory & Setup
This module acts as the "Architectural Blueprint" for the PostgreSQL database.

- **`/schema`**: Organized by Postgres schema names (Member, Location, Company, Media). Each directory contains the `CREATE TABLE` and `INDEX` definitions.
- **`/connection`**: Centralized connection management using `pgxpool`. It manages the fallback from environment variables to the **Supabase Transaction Pooler (Port 6543)**.
- **`/update`**: Contains `index.sql`, the master execution list for building the entire database from scratch.
- **`/purge`**: A safety-first utility for clearing core data (excluding location) during development and testing.

---

## ⚙️ How it Works
1.  **Schema Enforcement**: Uses strictly typed PostgreSQL schemas to prevent namespace collisions and enforce data integrity at the database level.
2.  **Shared Functions**: Maintains a library of PL/pgSQL functions (in `schema/functions`) used for automatic `updated_at` timestamps and audit logging.
3.  **Connection Resilience**: The connection module provides real-time logging of the target environment (Production vs. Development) to prevent accidental data loss.
4.  **Transaction Management**: Optimized for high-concurrency via the Supabase pooler, ensuring the system remains stable under heavy registration loads.

---

## 🏛️ Oracle Governance
The DB module is the physical manifestation of the Oracle Registry:

- **Source of Truth**: Every SQL file is directly linked to an `oracle/schemas/` mapping.
- **Audit Verification**: The `db/connection/connection.go` file is audited to ensure it always points to the Oracle-defined database infrastructure.
- **Registry Alignment**: The execution order in `update/index.sql` is designed to respect the foreign key dependencies defined in the Oracle mappings.

---
© 2026 LBRS Nepal. All rights reserved.
