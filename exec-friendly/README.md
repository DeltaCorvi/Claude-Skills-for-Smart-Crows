# Executive-Friendly Writing Skill

A skill for Claude Code and Cowork that revises technical writing so non-technical executives and managers can read it easily.

## What This Skill Does

This skill translates dense, jargon-heavy technical content into clear writing for intelligent but busy leaders who don't know the technical details. It expands or replaces acronyms, defines or drops jargon, and reframes complex concepts in plain language.

The core principle: this is translation, not expansion. The revised text stays roughly the same length as the original. The skill makes writing clearer, not longer.

## Who This Is For

This skill is useful if you:
- Need to make technical documents readable for middle or upper management
- Are handing a report, memo, or analysis up the chain to non-technical leaders
- Want to translate jargon and acronyms for a business audience
- Have been told your writing is too dense or too technical for its readers

## How It Works

The skill works in three phases, and it does not touch the text until you approve its plan:

1. **Plan:** It reads the source and lists everything to change, organized into acronyms to expand, jargon to define, concepts to simplify, and other structural or stylistic fixes.
2. **Request permission:** It presents the plan and waits for your explicit approval before revising anything.
3. **Revise:** Once approved, it rewrites the text, being selective rather than exhaustive: replacing terms with plain language where possible, and keeping a technical term only when it recurs or the reader needs to recognize it.

## Installation

See [INSTALLATION.md](INSTALLATION.md) for setup instructions for Claude Code and Cowork.

## Quick Start

Once installed, this skill activates when you ask Claude to adapt technical writing for a non-technical audience. Example prompts:
- "Make this exec-friendly."
- "Simplify this report for management."
- "My boss won't understand this. Can you translate it for a non-technical reader?"
- "Rewrite this section for executives."

## File Structure

- `SKILL.md` - The actual skill definition (copy this to your `~/.claude/skills/exec-friendly/` directory for Claude Code)
- `README.md` - This file
- `INSTALLATION.md` - Step-by-step installation instructions
