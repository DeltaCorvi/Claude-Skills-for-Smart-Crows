---
name: skill-exporter
description: Package an already-installed Claude Code skill from ~/.claude/skills/ into the folder structure required by a shared skills GitHub repo (README.md, SKILL.md, INSTALLATION.md), ready to commit and push. Use this skill whenever the user asks to export, publish, package, or share one of their existing custom skills, wants to "add this skill to my repo" or "make this skill shareable," or names a specific installed skill and asks to prep it for GitHub or hand it to someone else.
---

# Skill Exporter

This skill turns a working, installed Claude Code skill into the three-file bundle a shared skills repo expects: `SKILL.md`, `README.md`, `INSTALLATION.md`. The repo convention (see the target repo's own `README.md` "Contributing" section) is one subfolder per skill, self-contained, so anyone can copy just that folder and install it.

The goal is fidelity, not polish. The installed skill already works: the job here is packaging it so someone else can install and understand it, not rewriting its behavior.

## Step 1: Identify the source skill

If the user names a skill, look for it at `~/.claude/skills/<name>/SKILL.md` (check plugin-scoped paths too if the skill was installed via a plugin). Read the whole file: frontmatter and body.

If the user hasn't named a skill, or the file can't be found in this environment, ask them to point you at it or paste the `SKILL.md` content directly. Don't guess at a skill's behavior from memory: the exported copy needs to match what's actually installed, not a paraphrase.

Check the skill's directory for bundled resources (`scripts/`, `references/`, `assets/`) alongside `SKILL.md`. Note anything found: a skill with bundled scripts needs those files copied into the exported folder too (e.g. under a matching `scripts/` subfolder), not just the prose.

## Step 2: Determine the target folder name

Use the skill's `name` field from its own frontmatter as the folder name, kebab-case, matching the convention already used in the repo (e.g. `podcast-writing`). Check whether a folder with that name already exists in the repo and flag the collision to the user rather than overwriting silently.

## Step 3: Write SKILL.md

Copy the source skill's frontmatter and body into the new folder essentially unchanged. This file is what Claude actually reads to run the skill: paraphrasing or "cleaning up" the instructions risks changing its behavior, so preserve it faithfully.

The one thing worth editing: if the description or body references machine-specific paths, private context, or anything that only makes sense on the original author's machine, generalize that language so it reads sensibly for someone who's never seen the setup it was built in.

## Step 4: Write README.md

Follow the structure already established in the repo (use an existing skill's `README.md` as the template if one is present):

- Title and one-paragraph "What This Skill Does"
- "Who This Is For": a short bulleted list of use cases
- A summary of the skill's core approach or principles, drawn from the SKILL.md body. Don't invent principles that aren't actually in the source. If the skill doesn't have a clean numbered list of principles, summarize its approach in a paragraph instead of forcing one.
- "Installation": pointer to INSTALLATION.md
- "Quick Start": a couple of example prompts that would trigger the skill
- "File Structure": what's in the folder and what each file is for

## Step 5: Verify platform portability

Before writing INSTALLATION.md, check whether the skill's actual behavior (not just the mechanical install steps) works on both Claude Code and Cowork. Don't default to writing dual-platform docs; confirm it first.

Check for:

- **Platform-specific paths.** Does the skill's logic depend on a filesystem location only one platform has (e.g. `~/.claude/skills/`, which only Claude Code exposes)?
- **Platform-specific features.** Does it depend on a mechanism only one platform provides (e.g. Cowork's typed auto-memory schema, which Claude Code's own memory system doesn't match)?
- **Platform-specific concepts.** Does it depend on a product concept the other platform doesn't have at all (e.g. Cowork's "Projects," which Claude Code has no equivalent for)?

If the answer is yes for one platform, write installation instructions only for the platform(s) where the skill actually works, and say plainly in INSTALLATION.md why the other is excluded. Don't offer a full "Installing in X" section for a platform where the skill wouldn't function: a technically-installable-but-broken option is worse than no option.

If genuinely unsure after checking, note the uncertainty explicitly in INSTALLATION.md rather than asserting either way.

## Step 6: Write INSTALLATION.md

Adapt the repo's existing installation template (again, base it on an existing skill's `INSTALLATION.md` if the repo has one), substituting this skill's name throughout: directory structure, mkdir/copy commands for Windows PowerShell and macOS/Linux, verification via `/skills`, a troubleshooting section, and uninstall instructions, scoped to whichever platform(s) Step 5 confirmed. If the skill has bundled resources beyond `SKILL.md`, make sure the copy instructions cover those too.

## Step 7: Place the files

Write the finished folder directly into the connected skills repo directory as `<skill-name>/README.md`, `<skill-name>/SKILL.md`, `<skill-name>/INSTALLATION.md` (plus any bundled resources from Step 1). Leave git alone: committing and pushing stay a manual, deliberate step for the user, not something this skill does on its own.

## Step 8: Summarize for the user

Report what was created and flag anything they should double check before pushing: content that got generalized away from machine-specific paths, bundled scripts that need review, a folder-name collision that needs resolving, or a platform section that was omitted (or included despite uncertainty) due to the Step 5 portability check.
