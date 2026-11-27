<img src="assets/icon.svg" width="64" height="64" alt="">

# Flow

Flow combines all 25 engineering workflows from Addy Osmani's **agent-skills** with six selected skills from Matt Pocock and **pstack-claude**. Agent Skills remains the primary workflow for defining, planning, building, verifying, reviewing, and shipping work.

## Added skills

Flow also includes [humani-md](skills/humani-md/SKILL.md), an original skill that creates short, plain-language companions before technical specs and plans. Each companion gets an Unslop pass and human approval before technical expansion. Small fixes need no extra documents.

| Skill | Source | Purpose |
| --- | --- | --- |
| [wizard](skills/wizard/SKILL.md) | Matt Pocock | Generate an interactive Bash wizard for manual human steps. Includes the original template. |
| [unslop](skills/unslop/SKILL.md) | pstack-claude | Remove AI writing patterns while preserving meaning and tone. |
| [show-me-your-work](skills/show-me-your-work/SKILL.md) | pstack-claude | Keep an append-only decision trail with evidence and outcomes. |
| [how](skills/how/SKILL.md) | pstack-claude | Explain code behavior, architecture, and ownership. |
| [why](skills/why/SKILL.md) | pstack-claude | Investigate design rationale with citations and explicit confidence. |
| [teach](skills/teach/SKILL.md) | pstack-claude | Combine how and why into a plain explanation at the reader's pace. |
| [md-slayer](skills/md-slayer/SKILL.md) | Flow | Prevent Markdown bloat, retire completed task docs, and review older files before deletion. |
| [short-and-simple](skills/short-and-simple/SKILL.md) | Flow | Explain a topic, or the last answer, in a short summary, plain bullets and a tiny example. |
| [icm-architect](skills/icm-architect/SKILL.md) | RinDig/icm-architect | Design a process or restructure a folder, repo, or vault into an ICM workspace where folder structure is the agent architecture. |

The [skill router](skills/using-agent-skills/SKILL.md) includes these additions. All skills are packaged together under the `flow` plugin name. Supporting references, scripts, personas, and commands are bundled locally; the original plugins do not need to be installed separately.

MD-Slayer applies alongside the engineering workflows. It allows justified permanent docs, asks before creating temporary specs or plans, and removes current-task temporary docs after verified completion and before the final commit, PR handoff, or final response. Older deletion candidates are listed with assessments and reasons for the user to select.

## Install

In Claude Code, add this repository as a marketplace and install Flow:

```text
/plugin marketplace add epriding/flow
/plugin install flow@flow
```

For a local checkout, use `/plugin marketplace add /absolute/path/to/flow`, then `/plugin install flow@flow`. Invoke skills with names such as `/flow:wizard`, `/flow:how`, or `/flow:teach`. Skills also retain their descriptions for automatic discovery.

The repository includes `.codex-plugin/plugin.json` and `.agents/plugins/marketplace.json` for compatible hosts. The pstack additions use [Flow runtime guidance](references/skill-runtime.md) for host tools, models, and delegation. No pstack session hooks are enabled.

## Validate

Run the bundled content, packaging, and regression checks with Node.js and Bash:

```bash
node scripts/validate-skills.js
node scripts/validate-versions.js
node scripts/validate-reference-links.js
node scripts/validate-commands.js
node scripts/validate-artifact-paths.js
node --test scripts/*-test.js scripts/lib/*-test.js
bash -n skills/wizard/template.sh
bash -n skills/show-me-your-work/scripts/log.sh
```

The original Agent Skills documentation lives in [docs/](docs/). Its upstream installation examples refer to the original plugin; use the installation instructions above for this combined bundle. [UPSTREAM.md](UPSTREAM.md) records source revisions and integration changes. Original MIT notices are retained in [licenses/](licenses/).
