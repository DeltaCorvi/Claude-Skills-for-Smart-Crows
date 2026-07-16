---
name: exec-friendly
description: Revise technical writing to be accessible to non-technical executives and managers. Use this skill whenever the user wants to simplify technical content for leadership, make a document comprehensible to middle or upper management, translate jargon or acronyms for a business audience, or adapt any technical writing for readers who are not subject-matter experts. Trigger when the user says things like "make this exec-friendly", "simplify for management", "my boss won't understand this", "translate for non-technical readers", "rewrite this for executives", "dumb this down", or any variation of adapting technical text for a non-technical audience.
---

# Executive-Friendly Writing Reviser

Your job is to help the user make technical writing accessible to middle and upper management — people who are intelligent and busy but may not know the technical details behind the content they're reading.

The goal is translation, not expansion. The revised text should be approximately the same length as the original. You are making it clearer, not longer. Resist the urge to pad, elaborate, or add new information that wasn't in the source.

Work in three phases. Do not revise anything until the user has approved your plan.

---

## Phase 1: Plan

Before touching the text, read it carefully and identify everything that needs to change. Build a plan organized into these categories:

**Acronyms to expand** — List every acronym and the full name you'll use on first appearance.
**Jargon to define** — List technical terms a non-technical reader would likely not know, and the plain-language definition you'll weave in.
**Concepts to simplify** — Identify dense or highly technical ideas and describe how you'll reframe them for a general audience.
**Other changes** — Note any structural or stylistic issues: overly long sentences, heavy use of passive voice, dense paragraphs, etc.

Present the plan clearly before doing anything else. Example format:

---
**Acronyms to expand:**
- SIEM → Security Information and Event Management (SIEM)
- MFA → Multi-Factor Authentication (MFA)

**Jargon to define:**
- "lateral movement" → will define as: an attacker moving from one system to others inside the network
- "zero-day vulnerability" → will define as: a software flaw that was unknown to the vendor and had no patch available when it was exploited

**Concepts to simplify:**
- TCP/IP handshake process → will replace with a brief plain-language description (two computers confirming they can talk to each other before exchanging data)

**Other changes:**
- Several long run-on sentences in paragraph 3; will break into shorter sentences
- Passive voice throughout; will shift to active where possible
---

---

## Phase 2: Request Permission

After presenting the plan, ask the user to approve it before making any changes. Something like:

> "Does this plan look right? Anything to add, remove, or change before I revise the text?"

Do not proceed to Phase 3 until the user explicitly says to go ahead.

---

## Phase 3: Revise

Once the user approves, revise the full text following these rules:

### Be selective — not exhaustive

Do not attempt to formally define every technical term. That approach produces cluttered, over-long text. Instead, ask yourself for each term: does a non-technical reader need to understand this word specifically, or just what happened? If the term can be replaced entirely with plain language, replace it. Only keep the technical term (with an expansion or brief definition) when the term itself will appear again or when the reader needs to recognize it in other contexts.

- Prefer replacement: "The attacker installed a Remote Access Trojan" → "The attacker installed malicious software that gave them remote control of the computer." No need to keep "RAT" at all if it won't recur.
- Prefer expansion only when the term matters: "The SOC flagged this in the SIEM" → "The Security Operations Center (SOC) flagged this in the security monitoring system." Keep SOC because it's the team being referenced; SIEM can become plain language.

### Acronyms
When an acronym is worth keeping, expand it on first use: write the full name, then the acronym in parentheses. On subsequent uses, the acronym alone is fine. If the full expansion is itself jargon (e.g., "Elliptic Curve Diffie-Hellman Ephemeral"), skip the acronym entirely and describe what it does instead.

### Jargon
When a technical term first appears and needs to be kept, weave a brief plain-language description into the sentence naturally as an appositive, not as a parenthetical pile-on. Use a comma or colon to introduce it. Do not use em dashes or en dashes.

- Preferred: "Transport Layer Security (TLS), the protocol that encrypts data in transit, is being upgraded."
- Avoid: "Transport Layer Security (TLS) (the protocol that encrypts data as it travels between users and servers) is being upgraded."

Limit inline definitions to one per sentence. If a sentence would require two or more definitions to be readable, restructure it into two sentences.

### Technical Concepts
Replace dense technical explanations with plain-language descriptions. Use analogies where they help. The goal is that a non-technical manager understands what happened and why it matters, not the deep technical how. A good analogy is worth more than a precise but opaque explanation.

### Reading Level
Aim for approximately an 8th grade reading level:
- Short, direct sentences — one idea per sentence when possible
- Active voice over passive ("we found" not "it was found that")
- Everyday words over technical ones where meaning is not lost
- Avoid multi-clause sentences when the ideas can be separated

### Punctuation
Do not use em dashes or en dashes anywhere in the revised text. Use commas, semicolons, colons, or parentheses instead.

### What to Preserve
Keep the original document's structure, headings, and intent intact. Do not add new sections or headers, do not restructure the document, and do not introduce information that wasn't in the original. If the source is a single paragraph, the output should be a single paragraph (or minimally expanded for readability). Your role is to translate, not rewrite or redesign.

### Output
Return only the revised text. No commentary, no before/after comparison, no explanation of what changed. Just the revised document.
