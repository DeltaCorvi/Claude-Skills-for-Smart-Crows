# Installation Instructions

This guide walks you through installing the `update-project-memory` skill in Cowork.

This skill is built for Cowork's auto-memory feature: a `MEMORY.md` index plus per-fact memory files typed `user`, `feedback`, `project`, or `reference`, described to Claude through system context. It has only been tested in Cowork. Claude Code doesn't have an equivalent "Projects" concept, and its own auto-memory system (`~/.claude/projects/<repo>/memory/`) uses a different, untyped schema, so there's no Claude Code installation path here: installing this skill there wouldn't have anything to meaningfully reconcile against.

## Installing in Cowork

Cowork doesn't use `~/.claude/skills/` or CLI commands; skills are managed in the app itself.

### Option A: Upload the skill package

1. Package this skill as a `.skill` file: a zip archive containing `update-project-memory/SKILL.md` (nothing else from this repo, not `README.md` or `INSTALLATION.md`).
2. In Cowork, go to Customize > Skills, click Add, and upload the `.skill` file.
3. The skill appears under Customize > Skills, enabled by default.

This requires a Pro, Max, Team, or Enterprise plan with Code execution turned on. Skills you upload this way are private to your account. On Team or Enterprise, an org Owner can instead provision it for everyone from Organization settings > Skills.

### Option B: Browse the skills directory

If this skill has been published to Anthropic's skills directory, it can be installed directly from Customize > Skills in Cowork, without a manual upload.

## Using the Skill

Once installed, the skill activates when you ask Claude to review, audit, sync, or reconcile memory for a project, or say that memory seems stale or out of date.

You can also explicitly invoke it:
```
Use the update-project-memory skill to check whether your memory of this project is still accurate.
```

## Uninstalling

Remove it from Customize > Skills in Cowork.
