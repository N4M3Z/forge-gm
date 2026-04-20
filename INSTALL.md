# forge-gm

> RPG session prep toolkit — scene writing conventions, multi-phase review, art/music scouting, lore integrity, and GM adaptation agents.

*This file follows the [install.md](https://github.com/mintlify/install-md) standard — structured instructions for AI agents to execute autonomously. Human readers: see [README.md](README.md) for conventional documentation.*

I want you to install forge-gm for me. Execute all the steps below autonomously.

## OBJECTIVE

Deploy forge-gm skills, agents, and rules to all AI providers via Makefile.

## DONE WHEN

- `make validate` passes
- `ls ~/.claude/skills/SceneReview/SKILL.md` confirms skill deployment
- `git config core.hooksPath` returns `.githooks`

## Prerequisites

- Claude Code (or another AI provider CLI)
- forge-cli — [N4M3Z/forge-cli](https://github.com/N4M3Z/forge-cli)

## TODO

- [ ] Clone the repository
- [ ] Install forge-cli if missing
- [ ] Run `make install` to deploy
- [ ] Verify skill deployment
- [ ] Verify git hooks are active

## Steps

### Clone

```sh
git clone https://github.com/N4M3Z/forge-gm.git
cd forge-gm
```

If already cloned, pull latest:

```sh
git pull
```

### Check prerequisites

```sh
command -v forge
```

If missing, install forge-cli:

```sh
git clone https://github.com/N4M3Z/forge-cli.git
cd forge-cli
make install
cd ../forge-gm
```

### Install

```sh
make install
```

### Verify skill deployment

```sh
ls ~/.claude/skills/SceneReview/SKILL.md
```

### Verify git hooks

```sh
git config core.hooksPath
```

Should return `.githooks`. Pre-commit hooks validate markdown schemas and shell scripts when staged files match.

EXECUTE NOW: Complete the above TODO list.
