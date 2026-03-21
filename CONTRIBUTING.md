# Contributing

## Getting Started

```sh
git clone https://github.com/N4M3Z/forge-gm.git
cd forge-gm
make install    # deploys to all providers via forge install .
make validate   # runs .githooks/pre-commit
```

## Authoring

| Artifact | Location | Format |
|----------|----------|--------|
| Agents   | `agents/`  | Markdown with YAML frontmatter (`name`, `description`, `model`, `version`) |
| Skills   | `skills/<Name>/SKILL.md` | Markdown with YAML frontmatter, optional companion files |
| Rules    | `rules/`   | Markdown, always-loaded, concise |

Each directory carries a `.mdschema` that validation enforces. See [README.md](README.md) for naming conventions and scene-authoring specifics.

## Git

Conventional Commits: `type: description`. Lowercase, no trailing period, no scope.

Types: `feat`, `fix`, `docs`, `chore`, `refactor`, `test`.

Default branch is `main`. Never skip hooks.

## Pull Requests

1. Fork and create a branch
2. Make changes following the conventions above
3. `make validate`
4. Open a PR against `main`

CI runs validation on every PR. The `main` branch requires passing CI before merge.
