---
name: humani-md
description: Creates short, readable companions for human review of specs and plans. Use before creating a technical specification or implementation plan for substantial work, or when a material change needs renewed approval. Small fixes that need neither document are outside this workflow.
---

# Humani-md

## Overview

Help the human understand and approve the work before expanding it into a technical spec or plan. Write separate readable companions at the specification and planning stages. Keep the technical documents for implementation detail.

## When to Use

- Automatically alongside [spec-driven-development](../spec-driven-development/SKILL.md) and [planning-and-task-breakdown](../planning-and-task-breakdown/SKILL.md) for substantial work.
- When technical planning or implementation reveals a material change to an approved direction.
- When explicitly asked for a readable spec or plan.

Do not add documents or approval steps to small, self-contained fixes that need neither a spec nor a plan. Do not create both companions up front. Create each when its stage is reached.

## Process

### 1. Establish the stage and file pair

Read the request, relevant project context, and existing approvals. Clarify decisions that prevent a useful review. Repository inspection and research may happen before approval; technical document creation and implementation must wait for the applicable approvals.

Use the project's existing technical document locations. Put each companion beside its counterpart, adding `.human` before the extension. For example, `SPEC.md` pairs with `SPEC.human.md`, and `tasks/plan.md` pairs with `tasks/plan.human.md`. Preserve module ids when specifications are split by module. Do not change technical paths or duplicate an existing companion for the same work. Do not overwrite files belonging to different or unfinished work.

Apply MD-Slayer when available. Existing authorization to use this workflow can cover companion creation; do not ask again when that authorization is already present. Otherwise, bundle any required file-creation request for the pair, giving concrete paths, purpose, and retention. Present the readable draft in conversation while file permission is unresolved. Permission to create files is separate from approval of their content.

### 2. Write for a human decision

Aim for a two-minute read, roughly 300–500 words per companion. Use fewer words for simple work. Include technical terms only when they affect a decision, and explain them in plain language. Keep important limits and uncertainty even when shortening the document.

Cover these questions with short paragraphs or a compact list. Choose headings that suit the work:

- What problem are we solving, and for whom?
- What will change, and what is out of scope?
- What are the main tradeoffs, risks, and unresolved decisions?
- What does done look like? Describe concrete delivered behavior or artifacts.
- How will we verify it worked? Describe the evidence or checks for that outcome.

A readable spec emphasizes what will be built and why. A readable plan uses the approved spec and adds the main steps, their order, important dependencies, and verification checkpoints. Keep code, command inventories, exhaustive file lists, and task-level mechanics in the technical counterpart.

Read and apply [unslop](../unslop/SKILL.md) to every new or revised readable companion before presenting it. Compare the edited version with the draft to preserve facts, qualifications, and confidence. Do not equate shorter writing with clearer writing.

### 3. Present and wait

Show the readable version or link its file, identify unresolved decisions, and ask the human to approve it or request changes. End the turn. Do not create the technical counterpart or start implementation while waiting. Silence or permission to create a file is not content approval.

After approval, expand the approved direction through the relevant spec or planning skill. Readable approval permits technical expansion; it does not replace that skill's technical review or authorize deployment or other external actions. Do not impose an extra approval of an unchanged readable version when its approval is already established.

### 4. Keep the pair aligned

Compare the technical document with its readable companion before presenting it. If planning or implementation changes scope, delivered behavior, material risks, or the definition of done, update the affected companion, apply unslop, explain the difference, and wait for renewed approval before continuing the affected work. Do not present a changed technical document as already approved. Update both companions if both are affected.

Routine implementation choices within the approved direction can proceed without another readable review. Do not invent material changes merely to trigger approval.

### 5. Retain or retire together

Follow the technical counterpart's retention policy. Keep readable companions with retained specs and plans. For temporary pairs, apply MD-Slayer's cleanup rules. If MD-Slayer is unavailable, remove current-task temporary pairs only after implementation and verification are complete, nobody still needs them, and lasting information is preserved. Preserve requested deliverables and permanent documents. For older files, obtain the user's explicit deletion selection. Approval of this workflow does not authorize an unrelated documentation purge.

## Common Rationalizations

| Rationalization | Response |
|---|---|
| A summary after the technical document is enough | The human must be able to redirect the work before technical expansion. |
| Readable approval means we can start coding | Existing technical spec and plan review gates still apply. |
| The risk makes the document too long | Cut implementation detail, not information needed for approval. |
| A different outcome is just an implementation choice | Update the companion and obtain approval for the changed outcome. |

## Red Flags

- Writing the technical counterpart before readable approval.
- Hiding material risks or unresolved decisions behind reassuring prose.
- Creating both readable stages before the spec has been reviewed.
- Treating routine implementation choices as new approval gates.
- Keeping or deleting companion files without considering their counterparts and remaining readers.

## Verification

- [ ] Each readable file is beside the intended counterpart, without overwriting unrelated work.
- [ ] The document explains scope, tradeoffs, risks, what done looks like, and verification in a roughly two-minute read.
- [ ] A readable plan includes the main steps and their order.
- [ ] Unslop was applied without changing facts or uncertainty.
- [ ] Readable approval preceded technical expansion, and existing technical review gates remain intact.
- [ ] Material changes received renewed approval; routine choices did not create unnecessary gates.
- [ ] Retention or cleanup follows the counterpart's policy and preserves required context.
