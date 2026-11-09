# Commit messages

Use [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/).

```
<type>(<scope>): <summary>

<body>

<footer>
```

## Header

- `type` (required), one of:
  - `feat`: new user-facing feature
  - `fix`: bug fix
  - `docs`: README, CLAUDE.md, notes
  - `refactor`: code change with no behavior change
  - `test`: add or fix tests
  - `build`: dependencies, Dockerfiles, build tooling
  - `ci`: CI workflows
  - `chore`: anything else (config, .gitignore)
  - `perf`: performance improvement
- `scope` (optional): area touched, e.g. `search`, `k8s`, `otel`, `api`, `ui`.
- `summary`: imperative mood ("add", not "added"), lowercase, no trailing period, max 72 characters for the whole header.
- Breaking change: add `!` after type/scope, e.g. `feat(api)!: rename talk endpoint`.

## Body

- Optional. Wrap at 72 characters.
- Explain why the change was made, not what the diff shows.

## Footer

- `BREAKING CHANGE: <description>` when applicable.
- Reference issues as `Closes #12` / `Refs #12`.
- Commits written with Claude Code end with:
  `Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>`

## Rules

- One logical change per commit.
- Never commit secrets. Check the diff first (see CLAUDE.md, Secrets).

## Examples

```
feat(search): add hybrid keyword and vector talk search
fix(otel): export spans when Dash0 endpoint has trailing slash
docs: add setup instructions to README
chore: ignore .env and .mcp.json
```
