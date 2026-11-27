# Upstream sources

Imported from the local checkouts on 2026-11-09. Original license notices are in `licenses/`.

| Source | Repository | Revision |
| --- | --- | --- |
| agent-skills | https://github.com/addyosmani/agent-skills.git | `301b02b12bff98e4688e6984af6556802322bbde` |
| skills | https://github.com/mattpocock/skills.git | `4ae2317ddb22b046e26455e4f9c9b3aaaf62212d` |
| pstack-claude | https://github.com/michael-denyer/pstack-claude.git | `7e89063099c5e0c9e7ec7e8f2e0ea8de7d7d189d` |
| icm-architect | https://github.com/RinDig/icm-architect.git | `8bc2f5610d3843b3ffa31a142effe6b6337fef3c` (imported 2026-11-24) |

Agent Skills supplies all 25 original skills, personas, commands, hooks, references, documentation, and validation tools. Repository-specific agent instructions and upstream GitHub automation are not imported.

Matt Pocock supplies `wizard`, including its template and UI metadata. pstack-claude supplies `unslop`, `show-me-your-work`, `how`, `why`, and `teach`, including their references and helpers.

Flow adapts pstack runtime and model routing to the current host through `references/skill-runtime.md`, relocates the transcript-directory helper alongside the decision-log helper, and adds discovery routing and validation sections for the imported skills. No pstack session hooks or unrelated skills are enabled.

`humani-md` is original to Flow. It adds readable review before technical specs and plans, uses `unslop` for prose, and follows MD-Slayer retention rules when that skill is available.

`short-and-simple` is original to Flow. It gives brief, plain explanations of a topic or the previous answer.

icm-architect (Jake Van Clief, MIT) supplies `icm-architect` with its references, templates, and standard-library Python scripts. Flow adds a "Use when" trigger and the Overview, When to Use, Common Rationalizations, Red Flags, and Verification sections, renames `CONTEXT.md` and `stage-CONTEXT.md` templates to `root-context.md` and `stage-context.md` for the naming lint, and converts one backticked reference path to a link.
