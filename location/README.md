# LBRS Location — Geographic Governance Infrastructure

The **Location Service** manages the authoritative geographic hierarchy of Nepal within the LBRS ecosystem. It ensures that every business registration is correctly mapped to its respective Province, District, Palika, and Ward.

---

## 📂 Directory & Setup
The service is structured hierarchically to mirror the administrative divisions of Nepal.

- **`/v1/location`**: Partitioned by administrative level:
  - `provinces`: Management of the 7 Provinces.
  - `districts`: Management of the 77 Districts.
  - `palikas`: Management of Municipalities and Rural Municipalities.
  - `wards`: Granular management of Ward-level data.
- **`/server`**: Entry point that establishes the location API routes.
- **`.env.development` / `.env.production`**: Mirrored configurations from the Oracle registry.

---

## ⚙️ How it Works
1.  **Hierarchical Integrity**: Enforces strict parent-child relationships (e.g., a Ward cannot exist without a valid Palika ID).
2.  **Multilingual Labels**: Stores every location name in both English and Nepali (Devanagari) to support official government reporting.
3.  **Boundary Verification**: Provides lookup services for the Auth and Core modules to verify the jurisdictional scope of government operators.
4.  **Static Persistence**: Once established, the core location data acts as a static reference for all business registration addresses.

---

## 🏛️ Oracle Governance
The Location service provides the "Geographic Anchor" for the Oracle registry:

- **Global Reference**: Linked to the `location` schema in `db/schema/location/`.
- **Mapping Consistency**: Uses `oracle/schemas/location/` to define the ID standards used across the platform.
- **Dependency Source**: Other Oracle mappings (like `company.details`) depend on the IDs generated and managed by this service.

---
© 2026 LBRS Nepal. All rights reserved.
