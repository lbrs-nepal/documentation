# LBRS Location — Geographic Governance Infrastructure

The Location module is the definitive source for all geographic and administrative boundaries within the LBRS ecosystem, covering all levels of government from Provinces to Wards.

## 🏗️ How it's shaping up:
*   **Hierarchical Data Model**: A strict parent-child relationship model ensuring that every Ward belongs to a Palika, every Palika to a District, and every District to a Province.
*   **Administrative Scoping**: Provides the technical foundation for the "Palika-Isolation" security model used in the Core and Auth modules.
*   **Localized Data**: Native support for both English and Nepali (Devanagari) names for all geographic entities.

## 🌟 Key Features:
*   **Province & District Management**: Pre-populated with Nepal's 7 Provinces and 77 Districts.
*   **Palika Directory**: A searchable database of all Municipalities and Rural Municipalities.
*   **Ward-Level Precision**: Granular tracking for business addresses at the Ward level.
*   **Boundary Validation**: API-level validation to ensure business addresses match existing geographic data.

## 🚀 Current Focus:
Standardizing the `location` schema in the central database and implementing hierarchical lookup services.

---

## 📈 Feature & Progress Log
| Date | Milestone | Status |
| :--- | :--- | :--- |
| 2026-05-01 | Initial architectural plan for Location module defined. | ✅ COMPLETED |
| 2026-05-01 | Hierarchical data model documentation completed. | ✅ COMPLETED |
| 2026-05-05 | (Planned) Database migration for Provinces and Districts. | ⏳ PLANNED |
