# CLAUDE.md

Context for Claude Code working in this repo.

## What this is

Entry for the **Cloud Native Hackathon** (WeMakeDevs), Mon Nov 9, 2026, The Shop Workspace, Salt Lake City.
Theme: build something that makes tech conferences better.
This repo is **public** on GitHub. Treat everything committed as published.

- Hackathon: https://www.wemakedevs.org/hackathons/cnh
- Rules: https://www.wemakedevs.org/hackathons/cnh/rules
- Resources: https://www.wemakedevs.org/hackathons/cnh/resources

## Hackathon rules (hard constraints)

- Main coding starts **after kickoff**. Before kickoff, only the README, `.gitignore`, notes and sketches are allowed. If unsure whether kickoff has happened, ask before writing app code.
- The README must have setup instructions and keep its "AI assistance" disclosure section up to date.
- AI coding assistants are allowed but must be disclosed (see README).

## Secrets

Never commit tokens: Radar (`rhc_` / `rhp_`), Dash0, OpenAI, or any other credential.

- Secrets go in `.env` (gitignored). Keep `.env.example` in sync with placeholder values only.
- `.mcp.json` is gitignored. MCP tokens live in `~/.claude.json` (local scope), never in the repo.
- Before any commit, check the diff for secrets.

## Environment

- Local Kubernetes: `kind` cluster, context `kind-kind`, 1 node.
- Radar is installed in-cluster via Helm (namespace `radar`) and connected to Radar Cloud.
- The Radar MCP server is configured in Claude Code. Prefer Radar MCP tools over `kubectl` for reading cluster state and debugging.
- Telemetry goes to Dash0 over OTLP. Configure it with `OTEL_EXPORTER_OTLP_ENDPOINT` and `OTEL_EXPORTER_OTLP_HEADERS` from `.env`.

## Tracks (what judges score)

A project enters every track whose tool it genuinely uses.

| Track | Sponsor | Judges want |
|---|---|---|
| Never Merge Broken | Sonar (Gitar) | Features land via Gitar-reviewed PRs all day; custom review rules; CI fix via auto-apply |
| Stop Flying Blind | Dash0 | Deep OpenTelemetry instrumentation; Agent0/MCP finding a real issue; dashboard or SLO bonus |
| AI SRE | Radar | App on Kubernetes with Radar; use UI + MCP while building; AI investigation of a real issue |
| Find the Right Talk | Elasticsearch | Elasticsearch as the core data layer; smart keyword/vector/hybrid search |
| Conferences for Everyone | Merge Forward | Makes conferences more inclusive and accessible (iPad) |

## How to work here

- Gitar (Sonar) is installed on this repo. Land features through PRs from feature branches, not direct pushes to `main`, so Gitar reviews them.
- Add OpenTelemetry instrumentation as features are built, not at the end.
- Deploy the app to the kind cluster so Radar can see it.
- When a real bug or incident happens, investigate it with the Radar MCP or Dash0 and note it for the demo.
