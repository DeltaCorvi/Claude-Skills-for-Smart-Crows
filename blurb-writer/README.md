# Blurb Writer

A Claude Code skill for writing promotional blurbs for talks, presentations, and webcasts.

## What This Skill Does

This skill writes promotional blurbs that entice an audience to attend a live talk, presentation, or webcast. It follows a fixed, five-sentence hook/beginning/middle/climax/end structure and enforces a set of hard constraints (no repeated ideas, no repeated sentence openers, no overused nouns, no hype words like "journey" or "discovery") so every blurb comes out tight and jargon-free.

## Who This Is For

- You're promoting a conference talk, webinar, or panel and need a short description that builds excitement
- You organize or speak at events and want consistent, punchy promo copy without reinventing the format each time
- You want a blurb accessible to a broad, non-expert audience rather than one written for insiders

## Key Principles

- **Five sentences, one paragraph, no exceptions.** Each sentence has a specific job: hook, beginning, middle, climax, end.
- **Gather real input first.** The skill asks for the topic, speaker, and what makes the talk worth attending rather than inventing details from nothing.
- **Enforce hard constraints before delivering.** Every draft is checked against a fixed list: no repeated ideas across sentences, no two sentences starting the same way, no noun used more than twice, and banned words ("journey," "quest," "discovery," and variants) are never used.
- **Accessible over impressive.** The blurb should read clearly to a broad audience, not just domain experts.

## Credits

The five-sentence formula this skill is built on was shared with me year ago by [Jason Blanchard](https://www.linkedin.com/in/jasonsblanchard/). If the formula works for you, too, he should get the credit. 🙂

## Installation

See [INSTALLATION.md](INSTALLATION.md) for setup instructions.

## Quick Start

Once installed, invoke this skill by asking Claude to:
- "Write a promo blurb for my talk on [topic]."
- "I need a teaser for our upcoming webinar. Here's the abstract."
- "Create a promotional description for this conference session."

## File Structure

- `SKILL.md` - The actual skill definition (copy this to your `~/.claude/skills/blurb-writer/` directory)
- `README.md` - This file
- `INSTALLATION.md` - Step-by-step installation instructions
