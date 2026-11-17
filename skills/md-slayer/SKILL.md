---
name: md-slayer
description: Prevents Markdown documentation bloat and cleans up temporary specs and plans. Use when creating .md files, deciding which docs to keep, finishing implementation, or reviewing older Markdown for deletion. Applies alongside spec, planning, and documentation workflows.
---

# MD-Slayer

## Overview

Keep a clean workspace with only necessary Markdown. Prefer maintained documentation over scattered files, and retire temporary implementation documents when their work is finished.

## When to Use

Apply before creating Markdown, during task completion, and when asked to review existing documentation clutter. This governs documentation lifecycle; it does not replace implementation planning or dictate the content of a requested deliverable.

## Process

### 1. Decide whether a file earns its place

Inspect relevant existing docs first. Update an appropriate section rather than creating another file covering the same material. Keep short-lived reasoning, status updates, summaries, and checklists in the conversation or planning tools by default.

The following permanent documentation may be created without asking when it serves a concrete ongoing need and no existing document is suitable:

| Category | Purpose |
|---|---|
| README | Project purpose, quick start, and navigation |
| Setup and environment | Installation, configuration names, and development setup; never secret values |
| Architecture and decision records | System structure and significant decisions with lasting rationale |
| AI instructions | Project-specific agent conventions, commands, and boundaries |
| API documentation | Interfaces, inputs, outputs, authentication, and examples |
| Runbooks and troubleshooting | Repeatable operations and recurring problem diagnosis |
| Contributing guidelines | Contribution, testing, and review conventions |
| Security policies | Vulnerability reporting and support policies |
| Changelogs | User-visible release changes under an established or justified release process |

These are allowances, not a bundle to generate. A thin new file is often better as a section in an existing doc. Do not relabel a task summary as architecture or a task checklist as a runbook to qualify.

Preserve required legal/license files, skill definitions such as `SKILL.md`, explicitly requested Markdown deliverables, and Markdown used as test fixtures or product content. Create or edit these when the task requires them without requesting redundant permission.

### 2. Ask before exceptions

Ask before creating temporary specs, plans, implementation notes, or any other new Markdown outside the justified permanent categories. This applies even when another skill normally writes a file: perform its planning or specification work in conversation until file creation is approved. A direct request for a particular file already supplies permission for that file, not unrelated companion files.

Make the request concrete: give the proposed path, why an existing doc or conversation is insufficient, and when the file will be removed or reviewed. Bundle related requests. If there is no answer, do not create the files; continue independent work using conversation or planning tools where possible.

Once a temporary file is approved, maintain it and clean it up under the following rules without asking again. Track its path and purpose in conversation or planning tools, rather than generating a tracking document. Do not evade these rules by putting the same clutter in another format.

### 3. Clean up current-task temporary files

Remove temporary documents created for the current task only when all of these are true:

- Implementation is complete and the relevant verification has passed.
- No unfinished work, active reviewer, or other agent still needs the document.
- Lasting requirements, decisions, operating guidance, and necessary evidence have been preserved in suitable maintained docs or the existing PR/issue as appropriate.

Clean up before the final commit or PR handoff. If no commit or PR is part of the task, clean up before the final response. A commit alone is not evidence of completion. Keep necessary context while work is paused, incomplete, or awaiting verification or review; clean up at the next eligible completion point. Do not create a commit, PR, or follow-up watcher just to trigger cleanup.

Permission to create a file does not make it disposable. Keep permanent docs and requested deliverables even if created during this task. Only treat files as current-task files when their provenance is known; classify uncertain ownership with older files. Do not remove another contributor's work added to a temporary file without resolving that dependency.

Before removal, inspect references and preserve any needed information. Update links and navigation affected by approved cleanup, then check for dangling references. Stage deletions normally if committing is in scope; do not rewrite history to hide earlier versions. Briefly report what was removed and what remains for unfinished work.

### 4. Propose changes to older files

For pre-existing files, inspect content, current behavior, references, and available history before judging usefulness. Filenames, age, and an apparent lack of links alone do not establish obsolescence. Stay within the task's scope; a normal implementation task is not permission for a repository-wide purge.

List every file under consideration in the conversation, including those you recommend keeping:

| File | Assessment | Evidence and reason | Proposed action |
|---|---|---|---|
| `docs/old-plan.md` | Obsolete | Completed scope; unique decisions already in maintained docs | Delete if selected |
| `docs/setup.md` | Still needed | Current onboarding instructions | Keep |
| `docs/notes.md` | Uncertain | Contains unresolved migration work; ownership unclear | Keep pending clarification |

Use the labels **Obsolete**, **Still needed**, and **Uncertain**. Explain any information or links that would need migration. Ask the user to select the exact files to delete, then delete only the selected files. Do not interpret silence or agreement with the assessment as permission to remove every candidate. An explicit instruction naming files to delete already authorizes those deletions; do not ask again.

## Common Rationalizations

| Rationalization | Rule |
|---|---|
| Another skill requires a spec file | Ask to create it; use conversation in the meantime |
| This document might be useful someday | Identify an ongoing reader and purpose or avoid creating it |
| The task was committed, so the plan is obsolete | Check completion, verification, and remaining dependencies |
| This old file looks generated | Inspect and present it for the user's decision |

## Red Flags

- Creating a standard docs bundle, cleanup report file, or approval log without need.
- Deleting by filename, age, wildcard, or arbitrary file-count limit.
- Removing unfinished work or permanent docs because they were created during the task.
- Calling removal complete while leaving needed information or broken links behind.

## Verification

- Every new Markdown file is a justified permanent doc, required/requested content, or an approved exception.
- Eligible current-task temporary files are removed; retained temporary files have a stated dependency.
- Older files under consideration are all listed with assessments and reasons; deletions match the user's selections.
- Lasting information is preserved and affected references resolve after cleanup.
- The final diff and brief completion report account for created, retained, and removed docs without generating another report file.
