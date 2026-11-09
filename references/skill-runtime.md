# Flow runtime guidance

The imported pstack skills use this file instead of depending on poteto-mode, setup-pstack, generated model sheets, or pstack hooks. Their investigation and explanation workflows remain in the individual skills.

## Tools and delegation

Use tools exposed by the current host. Discover connected sources through its tool catalog or discovery API. A source is available only when configured, authenticated, and accessible to the agent that needs it. Record missing access as an evidence gap. Reading a connected source does not authorize sending messages or modifying it.

Use the host's general-purpose subagent mechanism when the workflow calls for delegation and the session permits it. Inherit the current model and reasoning settings by default. Honor explicit user choices. Do not pass Claude model aliases to another provider, silently substitute a requested model, or install a provider to satisfy a skill.

Batch independent investigations within the host's concurrency limit, then synthesize their results. Explorer and investigator tasks are read-only in intent. Give investigators access to connected tools where the host supports it. On hosts where a restricted mode removes connector access, use a mode with that access and explicitly prohibit writes in the task.

If delegation is unavailable or prohibited, perform the same evidence-gathering steps directly and disclose that the investigation was sequential. Never claim an independent or cross-model review that did not happen. For show-me-your-work, report an unavailable reviewer or transcript as a limitation in the Attention section.

## Invocation and composition

Resolve companion skills from this plugin's `skills/` directory. Use the host's skill loader when available, or read the companion's `SKILL.md`. If namespaced invocation is required, use the `flow` namespace, for example `/flow:how`.

Agent Skills remains responsible for the engineering lifecycle. `how`, `why`, and `teach` explain existing work; they do not authorize edits. `wizard` creates a script for human steps; generating that script does not authorize executing its external mutations. `unslop` preserves the uncertainty and factual meaning of investigation findings.

## Transcripts and local artifacts

Use only the active run's transcript and explicitly relevant artifacts. The Claude Code transcript-directory helper is bundled at `skills/show-me-your-work/scripts/claude-project-dir.mjs`; it is not a transcript locator for other hosts. When the host does not expose a transcript, audit the evidence available in the current conversation and state that limitation.

Keep decision trails local by default. Commit them only when the task calls for a reviewable trail in the repository. Follow the session's existing authorization for any external action.
