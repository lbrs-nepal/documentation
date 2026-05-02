# LBRS Core — The Business Registry Engine

The **Core Service** is the functional heart of LBRS. It manages the lifecycle of business entities, handles fiscal year calculations (BS), and orchestrates the complex registration workflows required by local governments.

---

## 📂 Directory & Setup
Core is organized into resource-based modules, ensuring that specific business domains are easy to maintain.

- **`/v1/schema`**: Contains the business logic for core entities:
  - `company`: Registration, details, and tenant management.
  - `organization`: Municipality-level classifications and policies.
  - `member`: Profile management and access level assignments.
- **`/server`**: Initializes the service and registers the global route tree.
- **`@LBRS-Mapping-Audit`**: Strictly enforced across all handlers and repositories.

---

## ⚙️ How it Works
1.  **Registration Pipeline**: Processes business applications from the Dashboard, applying municipal classification rules and calculating registration fees.
2.  **Fiscal Year Engine**: Automatically maps dates to the Nepali Bikram Sambat (BS) calendar, ensuring that renewals and taxes are tracked correctly across fiscal boundaries.
3.  **Data Isolation**: Every transaction is scoped to a specific `organization_id` (Palika), ensuring that municipalities cannot access each other's data.
4.  **Certificate Generation**: Orchestrates the creation of QR-coded certificates upon successful registration approval.

---

## 🏛️ Oracle Governance
The Core service is the primary consumer of the Oracle entity mappings:

- **Structural Linkage**: Linked to `db/schema/company/`, `db/schema/organization/`, and `db/schema/member/`.
- **Behavioral Mapping**: Relies on `oracle/schemas/company/details/details.yml` to define which fields are mandatory for legal business standing.
- **Mandatory Protocol**: Any change to the registration data structure must be audited in Oracle to prevent breaking changes in the Admin Console.

---
© 2026 LBRS Nepal. All rights reserved.
