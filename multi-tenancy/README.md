# Local Multitenancy Test Setup

This setup uses Docker Compose to simulate a multi-tenant observability pipeline.

## Components
1. **Flog (A & B)**: Two fake log generators tagged for separate tenants.
2. **Grafana Alloy**: Log agent pulling logs from Docker daemon and injecting headers based on tags.
3. **Grafana Loki**: Configured with `auth_enabled: true` to enforce `X-Scope-OrgID` parsing.
4. **Grafana**: Dashboard interface for mapping tenants.

## How to Test
1. Save all generated configuration files into the same directory.
2. Run `docker compose up -d`.
3. Open Grafana at `http://localhost:3000` (User: `admin` / Pass: `admin`).
4. Follow the setup steps listed in the text response to configure Orgs and data sources.
