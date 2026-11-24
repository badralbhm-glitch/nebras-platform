# Nebras Platform — Smart Academic Library

Monorepo for the Nebras Smart Academic Library platform, engineered by a six-member engineering team to deliver a structured academic reference catalog filtered by major, academic year, and resource type with strict multi-tenant data isolation (`tenant_id`)[cite: 1, 2, 3].

## Repository Structure & Boundaries

- `backend/`: Laravel API service handling authentication, authorization, tenant scoping, and core business logic[cite: 4, 7, 8].
- `frontend/`: Student catalog views, admin dashboard, PDF viewer, and embeddable university widget with RTL support[cite: 4, 5, 7, 8].
- `database/`: Entity-Relationship Diagrams (ERD), migrations, and seeders[cite: 8].
- `automation/`: n8n workflows and Telegram Bot handlers for document intake and review routing via Laravel internal endpoints[cite: 8, 10].
- `docs/`: API contract (`api-contract.md`), architectural decisions, setup guides, and issue/fix tracking[cite: 2, 8, 13].
- `infra/`: Docker Compose configurations and environment setup scripts (`Local` / `Staging` / `Production`)[cite: 8].
- `tests/`: Integration, tenant isolation, permission, and file handling test suites[cite: 8, 13].

## Branching Strategy & Team Workflow

- `main`: Production-ready stable release branch; direct pushes or merges are prohibited[cite: 8].
- `develop`: Shared integration and testing branch for team features[cite: 8].
- Working branches: Branched from the latest `develop` using clear prefixes such as `feature/...` or `fix/...`[cite: 8].
- Pull Requests & Reviews: Changes are merged into `develop` exclusively via Pull Request after peer review and passing tests[cite: 2, 8, 13].
- Secrets Policy: Never commit `.env` files or secrets (API keys, bot tokens, storage credentials, or secret keys); keep `.env.example` updated with variable names only[cite: 6, 8, 9, 10].
