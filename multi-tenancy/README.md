# Local Multitenancy Test Setup

This setup uses Docker Compose to simulate a multi-tenant observability pipeline.

## Components
1. **Flog (A & B)**: Two fake log generators tagged for separate tenants. more
1. **Avalanche** als metric generator
1. **Grafana Alloy**: Log agent pulling logs from Docker daemon and injecting headers based on tags.
1. **Grafana Loki**: Configured with `auth_enabled: true` to enforce `X-Scope-OrgID` parsing.
1. **Prometheus** om de metrics op te vangen en te bekijken
1. **Grafana**: Dashboard interface for mapping tenants.


## How to Test
1. Save all generated configuration files into the same directory.
1. Run `docker compose up -d`.
1. Open Grafana at `http://localhost:3000` (User: `admin` / Pass: `admin`).
1. [Setup grafana orgs](docs/setup.md) 
