# Claude Skills for Smart Crows

A collection of reusable skills for Claude Code and Cowork. Each skill is self-contained with its own directory, documentation, and installation instructions.

> [!tip]
> Even if you don't use Claude as your main LLM, these "skills" can be copy/pasted or uploaded to other LLMs (ChatGPT, Copilot, Gemini, etc.) in order to leverage the context and instructions each skill contains. 

## Installation

Each skill includes an `INSTALLATION.md` file with step-by-step setup instructions for the platform(s) it supports, across Windows, macOS, and Linux where applicable. Platform scope is decided per skill, not assumed. Most skills here work in both Claude Code and Cowork, but some (like `update-project-memory`) are single-platform by design. Check the skill's own `INSTALLATION.md` for which sections apply.

### Claude Code

1. Navigate to the skill directory
2. Follow the "Installing in Claude Code" section in `INSTALLATION.md`, if present
3. Claude Code detects new skills automatically (no restart required unless `~/.claude/skills/` is brand new)
4. Verify the skill appears in `/skills` or run `/reload-skills`

### Claude Cowork

1. Navigate to the skill directory
2. Follow the "Installing in Cowork" section in `INSTALLATION.md`, if present
3. Skills are managed in the app under **Customize > Skills**
4. Upload as a `.skill` file or browse the skills directory if published

## What is a Claude Skill?

A skill is a reusable methodology or prompt packaged for Claude. When installed, skills help Claude apply a consistent approach to your requests. Skills work across both Claude Code and Cowork environments.

## Requirements

**For Claude Code:**
- Claude Code installed locally
- Access to your `~/.claude/` directory
- Basic terminal/command-line familiarity

**For Cowork:**
- Cowork Pro, Max, Team, or Enterprise plan (with Code execution enabled for uploaded skills)
- App access to Customize > Skills

## Contributing

Follow the structure of any existing skill:

```
skill-name/
├── README.md           (overview and principles)
├── SKILL.md            (the skill definition)
├── INSTALLATION.md     (setup for the platform(s) the skill supports)
└── examples/           (optional)
```

**Important:** Platform scope isn't a default: verify which platform(s) a skill's behavior actually supports before writing `INSTALLATION.md`. If it works in both Claude Code and Cowork, include separate sections for each, since they use different mechanisms and paths. If it's single-platform by design (e.g., `update-project-memory`, which depends on Cowork's Projects/auto-memory concept), document only that platform. See any existing skill for the expected structure.

## License

These skills are provided as-is for educational and professional use.
