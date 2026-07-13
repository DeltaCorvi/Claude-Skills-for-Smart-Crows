---
name: update-project-memory
description: >
  Reconcile saved memory against a project's actual working files, report
  discrepancies, and update memory after approval. Use when the user asks to
  review, audit, sync, reconcile, or update memory for a project; to check
  whether memory matches the files; or says memory is stale or out of date.
---

# Sync Project Memory

Reconcile what is recorded in memory against the real state of a project's
files, surface the differences, and update memory only after the user approves.

## When to use

Trigger when the user wants memory checked against reality for an ongoing
project: "review memory for this project", "is my memory up to date", "sync
memory with the files", "audit what you remember about X", "memory is stale".

Do NOT trigger for general memory writes that have nothing to compare against
(just saving a new fact), or for editing files unrelated to memory.

## Inputs

- The project (named by the user, or the active workspace folder if obvious).
- The memory directory and its `MEMORY.md` index (paths are in system context).

If the project or its working folder is ambiguous, ask which one before
proceeding. Do not guess.

## Procedure

1. **Read memory.** Read `MEMORY.md` and every memory file that relates to the
   project. Note what each one currently claims.

2. **Read reality.** Enumerate the project's working folder (recursive
   listing), then read the key content files (outlines, drafts, notes,
   profiles, anything that states facts about the project). Do not rely on
   filenames alone; open the files.

3. **Diff.** Compare memory against the files and sort every finding into one
   of three buckets:
   - **Wrong**: memory says something the files contradict.
   - **Missing**: the files establish something memory does not record.
   - **Still accurate**: memory matches; call this out so it is kept, not
     re-litigated.

4. **Report and hold.** Present the three buckets plainly, then give concrete
   recommendations (which files to edit, add, or delete). Ask a clarifying
   question ONLY where there is genuine ambiguity that changes what you would
   write (for example an identity or name mismatch). Then stop and wait for
   approval. Do not write to memory in this step.

5. **Apply, on approval.** Once approved:
   - Edit existing memory files **in place** with targeted changes. Do not
     rebuild or regenerate a file from scratch.
   - Add new memory files following the memory schema, choosing the right
     type (`user`, `feedback`, `project`, `reference`).
   - Cross-link related memories with `[[name]]`.
   - Update `MEMORY.md`: one line per memory, no memory content in the index.
   - Convert relative dates to absolute. Confirm day-of-week or holiday
     constraints before committing a chosen date.

## Judgment rules

- **Ask before assuming.** When the files and memory disagree on something
  identifying (who the user is, which project this is, what a status means),
  ask rather than silently picking one. A wrong silent guess is the main
  failure mode this skill exists to prevent.
- **Targeted edits only.** Change the specific fields that are wrong or
  missing. Leave accurate content untouched.
- **Do not duplicate the repo.** Skip facts already recorded in the files
  themselves, code, or git history. Memory is for what is not derivable from
  the project's own materials.
- **Respect sensitive-info rules.** Do not persist protected attributes, gov
  IDs, financial account numbers, health details, home addresses, or secrets
  unless the user explicitly asks.

## Output

A short report (the three buckets plus recommendations) on review, and on
approval a confirmation of exactly which memory files changed and how.
