# Skill Exporter

A Claude Code skill for packaging your other installed skills so they can be shared through this repo.

## What This Skill Does

`skill-exporter` reads an already-installed, working skill from `~/.claude/skills/<name>/SKILL.md` and generates the three-file bundle this repo expects for every skill folder: `SKILL.md`, `README.md`, `INSTALLATION.md`. It writes that bundle directly into a new subfolder in this repo, matching the pattern already established by `podcast-writing/`.

It does not modify or improve the source skill's behavior. The goal is faithful packaging, not a rewrite: the exported `SKILL.md` should behave identically to the one already installed on your machine.

## Who This Is For

- You've built a custom skill for your own workflow and want to add it to this repo
- You want a consistent README/INSTALLATION writeup for every skill without doing it by hand each time
- You're maintaining a growing collection of personal skills and want a repeatable way to publish new ones

## How It Works

Given the name of an installed skill, the skill:

1. Locates and reads the skill's installed `SKILL.md` (frontmatter and body), plus any bundled `scripts/`, `references/`, or `assets/`
2. Picks the target folder name from the skill's own `name` field, checking for collisions with existing folders in the repo
3. Copies the `SKILL.md` content into the new folder essentially unchanged, generalizing only machine-specific paths or private context
4. Writes a `README.md` following this repo's established structure, summarizing the skill's actual principles rather than inventing new ones
5. Writes an `INSTALLATION.md` adapted from an existing skill's template, with the name substituted throughout
6. Places all files directly in the repo folder; it does not run any git commands, so committing and pushing stay manual

## Installation

See [INSTALLATION.md](INSTALLATION.md) for setup instructions.

## Quick Start

Once installed, invoke this skill by asking Claude something like:
- "Export my `log-triage` skill to the Smart Crows repo."
- "Package the `incident-notes` skill so I can share it."
- "Use skill-exporter to add my custom skill to this repo."

## File Structure

- `SKILL.md`: The actual skill definition (copy this to your `~/.claude/skills/skill-exporter/` directory)
- `README.md`: This file
- `INSTALLATION.md`: Step-by-step installation instructions
