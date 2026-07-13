# Claude Skills for Smart Crows

A collection of reusable skills for Claude Code and Cowork. Each skill is self-contained with its own directory, documentation, and installation instructions.

## Installation

Each skill includes an `INSTALLATION.md` file with step-by-step setup instructions for both Claude Code and Cowork, across Windows, macOS, and Linux.

### Claude Code

1. Navigate to the skill directory
2. Follow the "Installing in Claude Code" section in `INSTALLATION.md`
3. Claude Code detects new skills automatically (no restart required unless `~/.claude/skills/` is brand new)
4. Verify the skill appears in `/skills` or run `/reload-skills`

### Cowork

1. Navigate to the skill directory
2. Follow the "Installing in Cowork" section in `INSTALLATION.md`
3. Skills are managed in the app under Customize > Skills
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
├── INSTALLATION.md     (setup for both Claude Code and Cowork)
└── examples/           (optional)
```

**Important:** `INSTALLATION.md` must include separate sections for Claude Code and Cowork installation, since they use different mechanisms and paths. See any existing skill for the expected structure.

## License

These skills are provided as-is for educational and professional use.
