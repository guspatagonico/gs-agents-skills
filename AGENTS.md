# AGENTS.md

Skills repository for OpenCode agents. Each subdirectory is a standalone, installable skill.

## Skills structure

Every skill follows this layout:
```
<skill-name>/
  SKILL.md          # Hub file: triggers, workflow, safety rules, output contract
  README.md         # Human-facing install/usage docs
  references/       # Scoped to the skill, loaded on demand via SKILL.md's progressive disclosure
  scripts/          # Standalone bash helpers that also work outside the skill
```

`SKILL.md` frontmatter sets `name`, `description`, `allowed-tools`, and `author`. The description field drives trigger matching — keep it keyword-rich and accurate.

## Conventions

- Author: Gustavo Adrián Salvini (`guspatagonico`)
- License: MIT
- Language for docs and triggers: Spanish (primary). English is used in code, template content, and for broad distribution.
- Spanish is the default for natural-language triggers and READMEs unless a skill targets an international audience.

## Adding a new skill

1. Create `my-skill/SKILL.md` with frontmatter (`name`, `author`, `description`, `allowed-tools`)
2. Add `README.md` (install, usage, triggers table, structure, author, license)
3. Add `references/` for progressive-disclosure docs and `scripts/` for standalone helpers
4. No specific build step — copy the folder into `.agents/skills/` of any target repo

## This repo itself

- No build, test, lint, or CI pipeline — content-only repository
- No `package.json`, no dependencies
- Skills are tested by running them from a real project that consumes them
