# LBRS Core — The Registry Engine

The Core module is the central nervous system of LBRS, handling all business logic, registry operations, and fiscal calculations.

## 🏗️ How it's shaping up:
*   **Fiscal Year Logic**: Built-in support for **Bikram Sambat (B.S.)** fiscal year transitions. This includes a dynamic calculator for historical tax tracking and automatic year-rollover logic.
*   **Registration Workflows**: Unified handlers for business registration, renewal, and classification updates using a state-machine pattern to manage business lifecycles.
*   **Municipality Scoping**: Native multi-tenancy where data is strictly isolated by Local Government (Palika) boundaries. Every database query is automatically filtered by `organization_id`.

## 🌟 Key Features:
*   **Nepali Unicode Support**: Full compatibility for business names and owner details in Devanagari, integrated with standard Unicode fonts.
*   **QR Certificate Generation**: Automated generation of official business certificates (PDF) with unique QR codes for instant verification by law enforcement.
*   **Classification Engine**: Dynamic classification system that allows municipalities to define local tax categories and registration rules.

## 🚀 Current Focus:
Consolidating fragmented classification handlers into a unified Resource-Oriented pattern.

---

## 📈 Feature & Progress Log
| Date | Milestone | Status |
| :--- | :--- | :--- |
| 2026-04-15 | B.S. Fiscal Year calculator logic finalized. | ✅ COMPLETED |
| 2026-04-20 | QR Code verification gateway established. | ✅ COMPLETED |
| 2026-04-25 | Palika-level data isolation architecture implemented. | ✅ COMPLETED |
| 2026-05-01 | Classification system refactoring initiated. | ⏳ IN PROGRESS |
