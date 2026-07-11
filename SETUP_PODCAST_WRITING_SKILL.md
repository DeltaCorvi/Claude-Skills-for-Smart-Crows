# Setting Up the Podcast Writing Skill Locally

This guide will walk you through installing the podcast writing skill in your local Claude Code installation.

## What This Skill Does

The podcast writing skill provides guidance for writing content meant to be heard rather than read. Claude will invoke this skill when you ask for a podcast script, episode outline, audio narration, voiceover copy, radio segment, or any writing that will be spoken aloud to listeners.

## Directory Structure

Claude Code automatically discovers skills placed in `~/.claude/skills/`. Each skill needs its own folder containing a `SKILL.md` file.

```
~/.claude/skills/
└── podcast-writing/
    └── SKILL.md
```

## Installation Steps

### 1. Create the Directory

Open your terminal and run:

```bash
mkdir -p ~/.claude/skills/podcast-writing
```

### 2. Create the SKILL.md File

Create a file named `SKILL.md` inside the `podcast-writing` directory with the content below. On macOS and Linux, you can do this with:

```bash
cat > ~/.claude/skills/podcast-writing/SKILL.md << 'EOF'
---
name: podcast-writing
description: Guidance for writing content meant to be heard rather than read. Use this skill whenever the user asks for a podcast script, episode outline, audio narration, voiceover copy, radio segment, or any writing that will be spoken aloud to listeners, even if they don't use the word "podcast." Also use when reviewing or revising spoken-word content for clarity, pacing, or natural delivery.
---

# Writing for Podcasts

Podcast writing is fundamentally different from writing for the page. Readers can pause, reread, skim ahead, and absorb information at their own pace. Listeners get only one pass. Every sentence must be understandable the first time it is heard.

The goal is not to sound simpler. The goal is to sound natural, clear, and engaging when spoken aloud.

## Write for the Ear

This is the foundational principle. Sentences that look elegant on the page can sound awkward when spoken.

Prioritize clarity, rhythm, and flow over formal writing conventions. Use language that sounds natural in conversation. If a sentence feels uncomfortable to say out loud, rewrite it.

## Use Conversational Language

Write how an informed person would explain a topic to a curious colleague.

Use contractions. Favor plain language over unnecessarily complex wording. Avoid phrases that sound academic, corporate, or overly formal unless the audience expects them.

The goal is to sound knowledgeable, not scripted.

## Write for a Person, Not a Crowd

Podcasts are often most effective when they feel like a conversation rather than a presentation.

Address the listener directly when appropriate. Use "you" more often than "the audience" or "listeners." Imagine explaining the topic to one intelligent person rather than speaking to a room full of strangers.

## Favor Natural Speech Rhythms

Short sentences improve clarity, but too many in a row can make the script feel robotic or simplistic.

Mix short, medium, and occasional longer sentences. Let related ideas stay together when it improves the flow. Break sentences apart when comprehension would benefit, not simply to make them shorter.

Aim for the cadence of thoughtful conversation rather than a series of bullet points.

## Build in Signposting

Listeners cannot glance back at previous paragraphs or skim ahead to see where a discussion is going.

Help them navigate the content with clear transitions and structure.

Use phrases such as:

* "Let's start with..."
* "Now that we've covered that..."
* "The next piece is..."
* "This matters because..."

Good signposting reduces cognitive load and helps listeners stay oriented.

## Lead with the Interesting Part

Podcast audiences are quick to disengage if the payoff takes too long.

Start with the question, observation, story, or conclusion that makes the topic worth hearing. Provide supporting details and context afterward.

Avoid lengthy introductions that delay the point.

## Use Examples Generously

Listeners tend to retain stories, analogies, and examples more easily than abstract explanations.

When introducing a complex concept, follow it with a concrete example that illustrates the idea in practice.

If a listener can picture it, they are more likely to remember it.

## One Idea at a Time

Avoid stacking multiple concepts into a single explanation.

Introduce a concept, explain it, provide an example if needed, and then move on. This is especially important when discussing technical subjects.

Listeners need time to process information before adding more.

## Avoid Information Dumps

Dense blocks of facts, statistics, or terminology can overwhelm listeners.

Break complex information into smaller segments. Alternate explanation with examples, stories, questions, or observations that allow listeners to absorb what they have just heard.

## Embrace Repetition Strategically

Readers can revisit earlier sections. Listeners cannot.

Important concepts can and should be reinforced throughout an episode. Repeating key ideas, phrases, or themes helps retention and comprehension.

Use repetition intentionally, not accidentally.

## Write for the Host's Voice

A podcast script is performance material.

Consider the vocabulary, pacing, personality, and speaking style of the host. If a sentence sounds unnatural coming from their mouth, rewrite it.

The best podcast writing often feels as though the host is speaking spontaneously, even when every word was planned.

## Consider Production Elements

Think beyond the words on the page.

Pauses, music, sound effects, clips, and multiple speakers can all influence pacing and emphasis. Write with awareness of how production choices may support the story being told.

## Read Everything Aloud

Always read a script out loud before considering it finished.

This is the fastest way to identify awkward phrasing, unnatural transitions, tongue twisters, pacing problems, and sections that contain too much information.

If it sounds good when spoken, it will usually work well in a podcast.

## Cut Ruthlessly

Every sentence should contribute something valuable.

Remove unnecessary qualifiers, repetitive explanations, tangents, and details that do not support the story or discussion. Tight writing creates better pacing and makes episodes easier to follow.

## The Final Test

A well-written podcast script should sound like a knowledgeable person speaking naturally, not an essay being read aloud.

If the listener can follow the discussion without effort, stay engaged throughout the episode, and remember the key points afterward, the writing has done its job.
EOF
```

### 3. Verify Installation

Restart Claude Code, then verify the skill is recognized by running:

```
/skills
```

You should see `podcast-writing` in the list of available skills.

## Using the Skill

Once installed, the skill will automatically activate when you ask Claude to help with:
- Podcast scripts or episodes
- Voiceover copy or narration
- Radio segments or spoken-word content
- Any writing intended to be heard rather than read

You can also invoke it explicitly by saying "use the podcast writing skill" in your request.

## Troubleshooting

If the skill doesn't appear:
- Verify the directory exists: `ls -la ~/.claude/skills/podcast-writing/`
- Verify the file is named exactly `SKILL.md` (case-sensitive)
- Check that the YAML frontmatter is correctly formatted (starts and ends with `---`)
- Restart Claude Code completely
- On Windows, the path is typically `%USERPROFILE%\.claude\skills\podcast-writing\`
