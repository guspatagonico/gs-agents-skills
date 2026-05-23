# GS Agents Skills

Skills collection for [OpenCode](https://opencode.ai) agents — plug-and-play workflows that extend AI coding capabilities.

## Skills

| Skill | Description |
|---|---|
| [semver-release-automation](./semver-release-automation/) | Automates semantic releases from git tags. Decides patch/minor/major, generates changelogs, and optionally creates GitHub Releases. |

## Install

Copy a skill folder into `.agents/skills/` inside any target repository:

```bash
cp -r semver-release-automation/ path/to/your-project/.agents/skills/
```

The skill is loaded automatically when an agent matches its trigger phrases.

## Structure

Every skill follows this layout:

```
<skill-name>/
  SKILL.md          # Hub file — triggers, workflow, safety rules, output contract
  README.md         # Install, usage, and triggers table
  references/       # Progressive-disclosure docs (loaded on demand by SKILL.md)
  scripts/          # Standalone bash helpers, usable outside the skill too
```

## Creating a skill

1. Create `my-skill/SKILL.md` with YAML frontmatter (`name`, `author`, `description`, `allowed-tools`)
2. Add `README.md` with install instructions and trigger phrases
3. Add `references/` for detailed docs and `scripts/` for reusable helpers
4. Copy the folder into `.agents/skills/` of any repo to use it

> **Note:** This is a content-only repo — no build, tests, or dependencies. Skills are tested by running them from a real project.

## Author

Gustavo Adrián Salvini — [@guspatagonico](https://github.com/guspatagonico)
