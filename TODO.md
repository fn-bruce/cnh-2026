# TODO

## Design and plan the project

Theme: build something that makes tech conferences better. No specific app is assigned.

- [ ] Pick the idea. It must fit the theme and be buildable today.
- [ ] Decide which tracks to enter. Each one needs real use of its sponsor's tool:
  - Find the Right Talk (Elasticsearch): search as the core data layer (keyword, vector or hybrid).
  - Conferences for Everyone (Merge Forward): makes conferences more inclusive and accessible (iPad).
  - AI SRE (Radar): app on the kind cluster, real issue investigated with Radar.
  - Stop Flying Blind (Dash0): deep OpenTelemetry, real issue found with Agent0/MCP.
  - Never Merge Broken (Sonar/Gitar): features land via Gitar-reviewed PRs.
- [ ] Sketch the architecture and pick the stack. This unblocks `code-style.md` and `testing.md` below.

## Define specs for `.claude/rules/` files

Go over what each rule file should contain, then create it. `commits.md` (Conventional Commits) is done.

### High priority

- [ ] `git-workflow.md`: branch naming (`feat/…`, `fix/…`), PR-only merges to `main` so Gitar reviews them, PR description format. Supports the Sonar track.
- [ ] `security.md`: no secrets in code or logs, `.env` only, check the diff before committing, treat cluster data as untrusted.

### Default priority

- [ ] `observability.md`: OTel span names, required attributes, service naming. Supports the Dash0 track. Scope to source files with `paths:` frontmatter.
- [ ] `kubernetes.md`: manifest layout (`k8s/`), labels, resource limits, probes, `kind-kind` context only, Radar MCP before `kubectl`. Scope with `paths: ["k8s/**"]`.

### After the stack is picked

- [ ] `code-style.md`: language conventions, formatter, linter, naming. Scope by file extension.
- [ ] `testing.md`: test framework, test location, what to run before a PR.

### Only if entering that track

- [ ] `accessibility.md` (Conferences for Everyone): WCAG basics, keyboard and screen-reader support, iPad layout.
- [ ] `elasticsearch.md` (Find the Right Talk): index naming, mappings, hybrid search pattern.
