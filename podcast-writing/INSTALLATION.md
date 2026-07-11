# Installation Instructions

This guide walks you through installing the podcast writing skill in your local Claude Code installation.

## Directory Structure

Claude Code automatically discovers skills placed in `~/.claude/skills/`. Each skill needs its own folder containing a `SKILL.md` file.

```
~/.claude/skills/
└── podcast-writing/
    └── SKILL.md
```

## Installation Steps

### Step 1: Create the Directory

Open your terminal (PowerShell on Windows, bash/zsh on macOS/Linux) and run:

**Windows (PowerShell):**
```powershell
mkdir "$env:USERPROFILE\.claude\skills\podcast-writing" -Force
```

**macOS/Linux:**
```bash
mkdir -p ~/.claude/skills/podcast-writing
```

### Step 2: Copy the SKILL.md File

Copy the `SKILL.md` file from this repository into the directory you just created.

**Option A: Manual copy**
- Copy `SKILL.md` from this repo
- Paste it into `~/.claude/skills/podcast-writing/`

**Option B: Command line**

**Windows (PowerShell):**
```powershell
Copy-Item "SKILL.md" "$env:USERPROFILE\.claude\skills\podcast-writing\SKILL.md"
```

**macOS/Linux:**
```bash
cp SKILL.md ~/.claude/skills/podcast-writing/SKILL.md
```

### Step 3: Verify Installation

Restart Claude Code completely, then verify the skill is recognized by running this command in Claude Code:

```
/skills
```

You should see `podcast-writing` in the list of available skills.

## Troubleshooting

If the skill doesn't appear after restarting:

**Verify the directory exists:**

Windows (PowerShell):
```powershell
Test-Path "$env:USERPROFILE\.claude\skills\podcast-writing"
```

macOS/Linux:
```bash
ls -la ~/.claude/skills/podcast-writing/
```

**Verify the file exists and is named correctly:**

Windows (PowerShell):
```powershell
Get-ChildItem "$env:USERPROFILE\.claude\skills\podcast-writing\"
```

macOS/Linux:
```bash
ls -la ~/.claude/skills/podcast-writing/SKILL.md
```

**Common issues:**

- File is not named exactly `SKILL.md` (case-sensitive on macOS/Linux)
- YAML frontmatter is malformed (must start and end with `---`)
- Claude Code has not been fully restarted (close all instances, then reopen)
- On Windows, check that the path uses backslashes: `C:\Users\YourUsername\.claude\skills\podcast-writing\`

## Using the Skill

Once installed, the skill will automatically activate when you ask Claude to help with:
- Podcast scripts or episodes
- Voiceover copy or narration
- Radio segments or spoken-word content
- Any writing intended to be heard rather than read

You can also explicitly invoke it:
```
Use the podcast-writing skill to help me write a 5-minute intro for my next episode.
```

## Uninstalling

To remove the skill, simply delete the `~/.claude/skills/podcast-writing/` directory:

Windows (PowerShell):
```powershell
Remove-Item "$env:USERPROFILE\.claude\skills\podcast-writing\" -Recurse -Force
```

macOS/Linux:
```bash
rm -rf ~/.claude/skills/podcast-writing/
```
