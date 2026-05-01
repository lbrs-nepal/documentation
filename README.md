# LBRS Media Service — Global Asset Infrastructure

The **LBRS Media Service** is the centralized hub for managing, processing, and delivering media assets across the entire Local Business Registry System (LBRS) ecosystem. It provides a secure, high-performance gateway for images, videos, and legal documents.

---

## 🚀 Key Capabilities

*   **Intelligent Ingestion**: Automatic validation of file signatures (Magic Numbers) to prevent malicious uploads.
*   **Asynchronous Processing**: High-quality image resizing (Lanczos3) and video frame extraction using FFmpeg.
*   **Privacy First**: Automatic EXIF metadata stripping and support for **Private/Protected** assets.
*   **Unified Gateway**: A single, immutable delivery point at `https://media.npframe.com`.
*   **Enterprise Retention**: Built-in 45-day safety window for all deleted content.

---

## 🛠️ Technology Stack

*   **Backend**: Golang (Fiber)
*   **Storage**: MinIO (S3-Compatible Object Storage)
*   **Metadata**: PostgreSQL
*   **Engine**: FFmpeg & FFprobe

---

## 🌐 The LBRS Project Ecosystem

The Media Service is a core pillar of the LBRS architecture, designed to integrate seamlessly with our other specialized modules:

| Module | Description | Documentation |
| :--- | :--- | :--- |
| **`core`** | Central business logic & fiscal year engine. | [**View Info**](./core/README.md) |
| **`auth`** | Global IAM & RBAC provider. | [**View Info**](./auth/README.md) |
| **`db`** | Centralized schemas & data governance. | [**View Info**](./db/README.md) |
| **`location`**| Geographic governance & Palika mapping. | [**View Info**](./location/README.md) |
| **`desktop`** | Admin console & React dashboard. | [**View Info**](./desktop/README.md) |
| **`media`** | Asset processing & delivery infrastructure. | [**View Info**](./media/README.md) |

---

## 📖 Documentation Reference

For deep technical details, please refer to the specific documentation sub-modules:

1.  **[Architecture](https://github.com/lbrs-nepal/media/tree/main/docs/architecture)**: System design and module logic.
2.  **[API Specification](https://github.com/lbrs-nepal/media/tree/main/docs/api)**: Integration guides and endpoint references.
3.  **[Database Schema](https://github.com/lbrs-nepal/media/tree/main/docs/database)**: Metadata structure and retention policies.

---
© 2026 LBRS Nepal. All rights reserved.
