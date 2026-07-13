# Update Project Memory

A skill for reconciling Claude's saved memory about a project against the actual state of that project's working files.

## What This Skill Does

`update-project-memory` compares what is currently recorded in memory for a project against the real content of its files, sorts every finding into "wrong," "missing," or "still accurate," and reports back before changing anything. Memory is only edited after the user approves the specific changes.

## Who This Is For

- You maintain a project across multiple sessions and want confirmation that memory of it hasn't drifted from the real files.
- You suspect memory is stale (a decision was reversed, a fact changed, or something was recorded incorrectly) and want it checked systematically rather than corrected piecemeal.
- You want new, non-obvious facts from a project's files captured into memory without duplicating what's already derivable by reading the files themselves.

## Key Principles

- **Read before writing.** Every memory file relevant to the project is read first, then the project's actual working files, before any comparison happens.
- **Three-way sort.** Every finding lands in exactly one bucket: wrong (memory contradicts the files), missing (the files establish something memory doesn't have), or still accurate (memory matches, flagged so it isn't second-guessed).
- **Report and hold.** Findings and recommendations are presented before any memory file is touched. A clarifying question is only asked when something identifying is genuinely ambiguous; otherwise the skill goes straight to the report and waits for approval.
- **Targeted edits only.** Approved changes are applied to the specific fields that are wrong or missing; accurate content is left alone rather than being regenerated from scratch.
- **No duplication.** Facts already recoverable from the project's files, code, or git history don't get written to memory: memory is reserved for what isn't derivable from the project's own materials.

## Installation

See [INSTALLATION.md](INSTALLATION.md) for setup instructions.

## Quick Start

Once installed, invoke this skill by asking Claude something like:
- "Review memory for this project."
- "Is your memory of this project up to date?"
- "Sync memory with the files. I think it's stale."

## File Structure

- `SKILL.md`: The actual skill definition (install per [INSTALLATION.md](INSTALLATION.md))
- `README.md`: This file
- `INSTALLATION.md`: Step-by-step installation instructions
