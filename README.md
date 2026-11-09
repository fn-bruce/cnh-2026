# cnh-2026

Project for the [Cloud Native Hackathon](https://www.wemakedevs.org/hackathons/cnh) (Salt Lake City, Nov 9, 2026).

> Status: pre-kickoff. Only notes and scaffolding exist so far.

## Idea

_TBD: a project to make conferences better._

## Tracks

_TBD: list each track this project enters and the sponsor tool it uses._

## Setup

### Prerequisites

- Docker
- [kind](https://kind.sigs.k8s.io/) and `kubectl`
- Helm
- [Radar](https://radarhq.io) installed in-cluster (namespace `radar`)

### Environment

Copy `.env.example` to `.env` and fill in your values. `.env` is gitignored.

```bash
OTEL_EXPORTER_OTLP_ENDPOINT=<Dash0 OTLP endpoint>
OTEL_EXPORTER_OTLP_HEADERS=Authorization=Bearer <Dash0 token>
```

### Run

_TBD._

## AI assistance

This project uses AI coding assistants, as the hackathon rules allow:

- **Claude Code** (Anthropic) helps write code, docs, and config. It also queries the cluster through the Radar MCP server.

All AI-generated changes are reviewed by a human before merge.
