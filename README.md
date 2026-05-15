# BrandGuard

**BrandGuard** is an AI-powered brand compliance sidekick that integrates seamlessly into Figma, Slack, Google Docs, and Webflow. It ensures your visual and written assets remain consistent with your "living" brand bible by providing real-time scanning, automated fixes, and a private, self-improving LLM trained on your team’s unique tone.

---

## 🏗 Architecture Overview
BrandGuard utilizes a microservices architecture designed for scalability and high-performance image processing. 
*   **Core Engine:** A Go-based backend manages the BrandScore algorithm and the vector-logo extraction pipeline.
*   **AI/ML Pipeline:** A private LLM fine-tuned on user-approved copy to ensure tone-fingerprint accuracy.
*   **Integration Layer:** Webhooks and plugins for third-party platforms (Figma, Slack, GDocs, Webflow) facilitate real-time compliance checks.
*   **Infrastructure:** Deployed on AWS using ECS Fargate, with PostgreSQL for persistent storage and S3 for asset ingestion.

## 🛠 Technology Stack
*   **Frontend:** React, Vite, Tailwind CSS, TanStack Query
*   **Backend:** Go (Golang)
*   **Database:** PostgreSQL
*   **Infrastructure:** AWS (ECS, RDS, S3, Route53), Terraform
*   **Observability:** Prometheus, Grafana, Zap, Sentry

---

## 📊 Project Summary
*   **Total Issues:** 55
*   **Total Phases:** 7
*   **Estimated Effort:** ~300+ Engineering Hours

| Phase | Focus Area | Status |
| :--- | :--- | :--- |
| 1 | Infrastructure & Monorepo Setup | Todo |
| 2 | Core Backend Services | Todo |
| 3 | Frontend Dashboard Development | Todo |
| 4 | Platform Integrations (Figma/Slack/GDocs) | Todo |
| 5 | Testing & Quality Assurance | Todo |
| 6 | Production Deployment & DevOps | Todo |
| 7 | Documentation & Compliance | Todo |

---

## 🚀 Getting Started

### Prerequisites
*   [Go 1.21+](https://go.dev/dl/)
*   [Node.js 18+](https://nodejs.org/)
*   [Docker & Docker Compose](https://www.docker.com/)
*   [Terraform](https://www.terraform.io/)

### Local Development
1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-org/brandguard.git
   cd brandguard
   ```
2. **Setup Environment:**
   Copy the example environment files:
   ```bash
   cp .env.example .env
   ```
3. **Start the stack:**
   ```bash
   docker-compose up --build
   ```
4. **Initialize Workspaces:**
   The project uses npm/yarn workspaces for the frontend and Go modules for the backend. Ensure you run `go mod download` in the `/services` subdirectories.

---

## 📝 Implementation Notes
*   **Vector Logo Extraction:** Our moat is a patent-pending vector logo extractor. Performance is critical here; ensure all image processing is offloaded to the async task queue (SQS).
*   **Security:** As we target Enterprise clients, all sensitive data must be encrypted at rest. Use AWS Secrets Manager for all API keys and database credentials.
*   **Scalability:** We use UUIDs for primary keys across all services to ensure seamless sharding and cross-service reference integrity.
*   **Contributing:** Please follow the branching strategy defined in the project plan (`feat/`, `fix/`, `docs/`, `test/`). Ensure all PRs pass the CI pipeline (linting, unit tests, and security scans).

---

## 🛡 License
© 2023 BrandGuard. All rights reserved. Private & Confidential.