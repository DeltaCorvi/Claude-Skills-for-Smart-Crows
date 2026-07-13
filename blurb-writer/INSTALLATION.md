# Installation Instructions

This guide walks you through installing the blurb writer skill. It follows the open Agent Skills standard, so it works in either Claude Code or Cowork. Pick the section below for your platform.

Jump to: [Installing in Claude Code](#Installing%20in%20Claude%20Code) | [Installing in Cowork](#Installing%20in%20Cowork)

## Installing in Claude Code

### Directory Structure

Claude Code automatically discovers skills placed in `~/.claude/skills/`. Each skill needs its own folder containing a `SKILL.md` file.

```
~/.claude/skills/
└── blurb-writer/
    └── SKILL.md
```

### Installation Steps

#### Step 1: Create the Directory

Open your terminal (PowerShell on Windows, bash/zsh on macOS/Linux) and run:

**Windows (PowerShell):**
```powershell
mkdir "$env:USERPROFILE\.claude\skills\blurb-writer" -Force
```

**macOS/Linux:**
```bash
mkdir -p ~/.claude/skills/blurb-writer
```

#### Step 2: Copy the SKILL.md File

Copy the `SKILL.md` file from this repository into the directory you just created.

**Option A: Manual copy**
- Copy `SKILL.md` from this repo
- Paste it into `~/.claude/skills/blurb-writer/`

**Option B: Command line**

**Windows (PowerShell):**
```powershell
Copy-Item "SKILL.md" "$env:USERPROFILE\.claude\skills\blurb-writer\SKILL.md"
```

**macOS/Linux:**
```bash
cp SKILL.md ~/.claude/skills/blurb-writer/SKILL.md
```

#### Step 3: Verify Installation

Claude Code detects new skills under `~/.claude/skills/` automatically, so no restart is needed. Verify the skill is recognized by running this command in Claude Code:

```
/skills
```

You should see `blurb-writer` in the list of available skills. If it doesn't appear, run `/reload-skills` to force a rescan: this is a troubleshooting/reassurance step, not a required part of installation. A full restart is only necessary if `~/.claude/skills/` did not exist before this install.

### Troubleshooting

If the skill doesn't appear after running `/reload-skills`:

**Verify the directory exists:**

Windows (PowerShell):
```powershell
Test-Path "$env:USERPROFILE\.claude\skills\blurb-writer"
```

macOS/Linux:
```bash
ls -la ~/.claude/skills/blurb-writer/
```

**Verify the file exists and is named correctly:**

Windows (PowerShell):
```powershell
Get-ChildItem "$env:USERPROFILE\.claude\skills\blurb-writer\"
```

macOS/Linux:
```bash
ls -la ~/.claude/skills/blurb-writer/SKILL.md
```

**Common issues:**

- File is not named exactly `SKILL.md` (case-sensitive on macOS/Linux)
- YAML frontmatter is malformed (must start and end with `---`)
- Live detection hasn't caught the change yet: run `/reload-skills`, or restart Claude Code if `~/.claude/skills/` was just created for the first time
- On Windows, check that the path uses backslashes: `C:\Users\YourUsername\.claude\skills\blurb-writer\`

## Installing in Cowork

Cowork doesn't use `~/.claude/skills/` or CLI commands; skills are managed in the app itself.

### Option A: Upload the skill package

1. Package this skill as a `.skill` file: a zip archive containing `blurb-writer/SKILL.md` (nothing else from this repo, not `README.md` or `INSTALLATION.md`).
2. In Cowork, go to Settings > Capabilities > Upload skill and upload the `.skill` file.
3. The skill appears under Customize > Skills, enabled by default.

This requires a Pro, Max, Team, or Enterprise plan with Code execution turned on. Skills you upload this way are private to your account. On Team or Enterprise, an org Owner can instead provision it for everyone from Organization settings > Skills.

### Option B: Browse the skills directory

If this skill has been published to Anthropic's skills directory, it can be installed directly from Customize > Skills in Cowork, without a manual upload.

## Using the Skill

Once installed, the skill will automatically activate when you ask Claude to help with:
- Writing a promo blurb or teaser for a talk, session, or webcast
- Promoting or hyping up an upcoming speaker or presentation
- Producing an event description in the five-sentence promo blurb format

You can also explicitly invoke it:
```
Use the blurb-writer skill to write a promo blurb for my talk on zero-trust architecture.
```

## Uninstalling

### Claude Code

Delete the `~/.claude/skills/blurb-writer/` directory.

Windows (PowerShell):
```powershell
Remove-Item "$env:USERPROFILE\.claude\skills\blurb-writer\" -Recurse -Force
```

macOS/Linux:
```bash
rm -rf ~/.claude/skills/blurb-writer/
```

### Cowork

Remove it from Customize > Skills.
