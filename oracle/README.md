# LBRS Oracle — Architectural Governance & SSoT

The **Oracle Registry** is the "Brain" of the LBRS ecosystem. It serves as the Single Source of Truth (SSoT) for the entire platform, bridging the gap between static database schemas and active software behavior.

---

## 🏛️ Why Oracle Exists

In a complex microservice environment, documentation often drifts away from the actual code. Oracle solves this by creating a **Living Contract**:
- **Visibility**: Instantly see which API endpoints interact with which database columns.
- **Traceability**: Track a data point from a React component to a Go Repository and down to the SQL table.
- **Integrity**: Prevent accidental breaking changes by enforcing a "Registry-First" update protocol.

---

## 🛰️ Core Components

### 1. Service Registry (`services.yml`)
Located at `oracle/config/services.yml`, this file defines the network infrastructure of the ecosystem:
- **Port Management**: Assigns unique ports (5001-5051) to services to prevent conflicts.
- **Environment Parity**: Synchronizes `development` and `production` URLs.
- **DB Pooling**: Manages connections to the Supabase Transaction Pooler (port 6543).

### 2. Behavioral Mappings (`schemas/`)
Located in `oracle/schemas/`, these YAML files document the "Behavior" of the system:
- **Table Context**: Explains the purpose of each table beyond the SQL comments.
- **Column Mappings**: Maps specific columns to the Backend Repositories and Frontend Components that use them.
- **Sensitivity Levels**: Identifies high-security columns (like `password_hash`) and their access restrictions.

### 3. The Audit Protocol (`@LBRS-Mapping-Audit`)
Every file governed by Oracle contains a header that links it back to its registry entry.
- **Related Schema**: Links to the physical `.sql` structure.
- **Related Mapping**: Links to the behavioral `.yml` mapping.
- **Mandatory Requirement**: Changes to logic MUST be mirrored in the Oracle registry.

---

## ⚖️ The Oracle-First Protocol

All developers and AI agents must follow this workflow:
1.  **Analyze**: Read the Audit Header to find the governing Oracle mapping.
2.  **Plan**: Check the Oracle YAML to see if the proposed change violates any architectural rules.
3.  **Execute**: Apply code changes.
4.  **Synchronize**: Update the Oracle registry to reflect the new state of the system.

---

## 🛠️ Key Tools
- **`oracle/main.go`**: The CLI utility used to verify that every path and file mentioned in the registry actually exists and is properly tagged.

---
© 2026 LBRS Nepal. All rights reserved.
